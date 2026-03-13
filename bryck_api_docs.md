# Bryck API — Complete Reference Documentation

> **Version:** 1.0.0  
> **Base URL:** `http://<bryck-host>:<port>/api`  
> **Content-Type:** `application/json`  
> **Authentication:** JWT Bearer Token  
> **License:** MIT — Copyright (c) 2018 Tsecond

---

## Table of Contents

1. [Overview](#1-overview)
2. [Authentication](#2-authentication)
3. [Standard Response Envelope](#3-standard-response-envelope)
4. [Error Handling](#4-error-handling)
5. [Endpoints](#5-endpoints)
   - [Auth](#51-auth)
   - [Config](#52-config)
   - [Hardware — Brycks](#53-hardware--brycks)
   - [Hardware — Logical Cards](#54-hardware--logical-cards)
   - [Hardware — Trays](#55-hardware--trays)
   - [Network](#56-network)
   - [Tasks](#57-tasks)
   - [Download](#58-download)
   - [External Storage](#59-external-storage)
   - [Version](#510-version)
6. [Data Models & Schemas](#6-data-models--schemas)
7. [OpenAPI 3.1 Specification](#7-openapi-31-specification)

---

## 1. Overview

The Bryck API is a RESTful backend that manages Bryck hardware storage appliances. It provides endpoints for:

- **Authentication** — JWT-based token issuance, refresh, and password management.
- **Configuration** — Store creation, mounting, ejection, shutdown, upgrade, and system info.
- **Hardware** — Querying status for Brycks, Logical Cards, and Trays.
- **Network** — Viewing and configuring network interfaces and NTP.
- **Tasks** — Data transfer, verification, task monitoring, and dismissal.
- **Downloads** — Serving client software, user guides, and diagnostic reports.
- **External Storage** — Mounting/unmounting remote NFS exports.
- **Version** — Product version retrieval.

**Key design principles:**

| Aspect | Detail |
|---|---|
| Framework | Flask + Flask-JWT-Extended |
| Database | SQLAlchemy (SQLite / Postgres) |
| Auth | JWT tokens in `Authorization` header or cookies |
| Response format | Uniform JSON envelope (see §3) |
| CORS | Enabled for all origins, credentials supported |
| Session timeout | Configurable via `MAX_SESSION_DURATION` (default 600 s) |

---

## 2. Authentication

All endpoints except `POST /api/auth` and `GET /api/version` require a valid JWT token.

### Obtaining a Token

Send credentials to `POST /api/auth`. On success you receive an `access_token` and its Unix `expires` timestamp.

### Using the Token

Include the token in every subsequent request using **one** of:

| Method | Header / Cookie |
|---|---|
| **Authorization header** | `Authorization: JWT <access_token>` |
| **Cookie** | `access_token_cookie=<access_token>` |

### Token Validation

Tokens are bound to the originating client IP address. If a request arrives from a different IP than the one encoded in the token, the API returns `401 Invalid token`.

### Security Scheme (OpenAPI)

```yaml
securitySchemes:
  BearerAuth:
    type: http
    scheme: bearer
    bearerFormat: JWT
    description: >
      Pass the token returned by POST /api/auth.
      Header format:  Authorization: JWT <token>
```

---

## 3. Standard Response Envelope

Every response follows the same JSON envelope:

### Success (HTTP 200)

```json
{
    "success": true,
    "error": {},
    "result": { /* endpoint-specific payload */ }
}
```

### Error (HTTP 4xx / 5xx)

```json
{
    "success": false,
    "error": {
        "message": "Human-readable error description"
    },
    "result": {}
}
```

| Field | Type | Description |
|---|---|---|
| `success` | boolean | `true` when HTTP status is 200, `false` otherwise |
| `error` | object | Empty on success; contains `message` on failure |
| `result` | object / array | Payload on success; empty on failure |

---

## 4. Error Handling

### Standard Error Codes

| HTTP Status | Meaning | When |
|---|---|---|
| 400 | Bad Request | Missing/invalid parameters, malformed JSON |
| 401 | Unauthorized | Invalid credentials, expired/invalid token, IP mismatch |
| 404 | Not Found | Requested resource does not exist |
| 405 | Method Not Allowed | Wrong HTTP method for the endpoint |
| 409 | Conflict | Resource conflict (e.g., task already running) |
| 500 | Internal Server Error | Unhandled exception |

### Error Response Model

```json
{
    "success": false,
    "error": {
        "message": "string — describes the error"
    },
    "result": {}
}
```

---

## 5. Endpoints

---

### 5.1 Auth

Blueprint prefix: `/api/auth`

---

#### `POST /api/auth` — Obtain JWT Token

**Summary:** Authenticates a user and returns a JWT access token.

**When to use:** Call this first to obtain a token before calling any protected endpoint.

**Authentication:** None required.

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `username` | string | **Yes** | The user's login name (e.g., `"admin"`). |
| `password` | string | **Yes** | The user's plaintext password. |

**Response (200):**

| Field | Type | Description |
|---|---|---|
| `access_token` | string | Signed JWT token to use in subsequent requests. |
| `expires` | integer | Unix timestamp (seconds) when the token expires. |

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing or empty `username` or `password` |
| 401 | Invalid credentials |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/auth \
  -H "Content-Type: application/json" \
  -d '{
    "username": "admin",
    "password": "S3cureP@ss1"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
import requests

resp = requests.post(
    "http://BRYCK_HOST/api/auth",
    json={"username": "admin", "password": "S3cureP@ss1"}
)
data = resp.json()
token = data["result"]["access_token"]
print(f"Token expires at: {data['result']['expires']}")
```
</details>

**Example Response:**

```json
{
    "success": true,
    "error": {},
    "result": {
        "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
        "expires": 1711540800
    }
}
```

---

#### `POST /api/auth/refresh` — Refresh JWT Token

**Summary:** Returns a fresh JWT token with an extended expiration.

**When to use:** Call before the current token expires to avoid re-authenticating.

**Authentication:** Required (JWT).

**Request Body:** None.

**Response (200):** Same schema as `POST /api/auth`.

**Error Responses:**

| Status | Condition |
|---|---|
| 401 | Token invalid or client IP mismatch |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/auth/refresh \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/auth/refresh",
    headers={"Authorization": f"JWT {token}"}
)
new_token = resp.json()["result"]["access_token"]
```
</details>

---

#### `POST /api/auth/change_password` — Change User Password

**Summary:** Changes the password for the `admin` user.

**When to use:** When the admin needs to update their password. Only the `admin` user may change their own password.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `username` | string | **Yes** | Must be `"admin"`. |
| `old_password` | string | **Yes** | Current password for verification. |
| `new_password` | string | **Yes** | New password. Must meet complexity requirements. |

**Password Complexity Requirements:**

| Rule | Description |
|---|---|
| Length | ≥ 8 characters |
| Digit | At least 1 digit |
| Uppercase | At least 1 uppercase letter |
| Lowercase | At least 1 lowercase letter |
| Symbol | At least 1 special character |
| Unique | Must differ from old password |

**Response (200):**

```json
{
    "success": true,
    "error": {},
    "result": {
        "message": "Password for user admin successfully changed"
    }
}
```

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing fields, old = new, wrong old password, weak new password |
| 401 | Username is not `admin`, or changing another user's password |

**Complexity check failure response (400):**

```json
{
    "success": false,
    "error": {
        "message": {
            "password_ok": false,
            "length_error": false,
            "digit_error": true,
            "uppercase_error": false,
            "lowercase_error": false,
            "symbol_error": true
        }
    },
    "result": {}
}
```

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/auth/change_password \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "username": "admin",
    "old_password": "OldP@ss1",
    "new_password": "NewP@ss2!"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/auth/change_password",
    headers={"Authorization": f"JWT {token}"},
    json={
        "username": "admin",
        "old_password": "OldP@ss1",
        "new_password": "NewP@ss2!"
    }
)
print(resp.json())
```
</details>

---

### 5.2 Config

Blueprint prefix: `/api/config`

---

#### `GET /api/config/info` — Get System Configuration & Status

**Summary:** Returns complete Bryck system info including hardware status, logical cards, server info, build version, and upgrade status.

**When to use:** To render a dashboard or gather the full system state in a single call.

**Authentication:** Required (JWT).

**Query Parameters:** None.

**Response (200):**

| Field | Type | Description |
|---|---|---|
| `bryck_info` | object | Bryck hardware details (drives, state, model, serial, etc.) |
| `server_info` | object | Host server details (CPU, RAM, OS, hostname) |
| `tray_info` | object | Tray connection and status data |
| `logical_cards` | object | Map of logical card UUID → properties, conditions, drives |
| `properties` | object | Top-level system properties |
| `build_info` | object | Contains `version` and `install_date` |
| `upgrade` | boolean | Whether an upgrade process is currently running |
| `upgrade_info` | object | Upgrade state details (filename, progress) |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/config/info \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/config/info",
    headers={"Authorization": f"JWT {token}"}
)
info = resp.json()["result"]
print(f"Version: {info['build_info']['version']}")
```
</details>

---

#### `POST /api/config/update` — Configure Store

**Summary:** Creates or reconfigures a storage volume (FILE_STORE or BLOCK_STORE) on the specified logical cards.

**When to use:** After initial setup or when changing the storage configuration on one or more logical cards.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `store_type` | string | **Yes** | `"FILE_STORE"`, `"BLOCK_STORE"`, or other valid `StoreType` member. |
| `uuids` | array\<string\> | **Yes** | List of logical card UUIDs to configure. |
| `raid_level` | integer | Conditional | RAID level (`0`, `5`, `6`, `7`). Required for FILE_STORE and BLOCK_STORE. |
| `mount_point` | string | No | Filesystem mount path (FILE_STORE only). |
| `export_options` | string | No | NFS export options (FILE_STORE only). |
| `acl` | array\<string\> | No | iSCSI initiator ACL list (BLOCK_STORE only, max 100 entries). |
| `iqn` | string | No | iSCSI Qualified Name (BLOCK_STORE only). |
| `suffix` | string | No | Target suffix (BLOCK_STORE only). |
| `description` | string | No | Human-readable description for the store. |
| `encryption_check` | boolean | No | Enable encryption with a key file. |
| `encryption_option` | string | No | `"AWS_KMS"` to use AWS KMS key management. |
| `mountonreboot` | boolean | No | Auto-mount on reboot. |
| `IoSize` | string | No | I/O block size (default `"2048"`). |
| `DataSync` | string | No | Sync mode (default `"application sync"`). |
| `dedup` | boolean | No | Enable deduplication. |
| `compress` | boolean | No | Enable compression. |

**Validation Rules:**

- `raid_level` must be `0`, `5`, `6`, or `7` for FILE_STORE / BLOCK_STORE.
- Cannot create a store on a UUID that already has an existing store (must reinitialize first).
- FILE_STORE cannot include `acl`, `iqn`, or `suffix`.
- BLOCK_STORE cannot include `mount_point` or `export_options`.
- BLOCK_STORE `acl` is limited to 100 entries.

**Response (200):** Standard success envelope `{ "success": true, "error": {}, "result": {} }`.

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Invalid store_type, raid_level, missing uuids, parameter conflicts, stores not yet initialized |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/update \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "store_type": "FILE_STORE",
    "uuids": ["uuid-1111-2222-3333"],
    "raid_level": 5,
    "mount_point": "/mnt/data",
    "description": "Primary file store"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/config/update",
    headers={"Authorization": f"JWT {token}"},
    json={
        "store_type": "FILE_STORE",
        "uuids": ["uuid-1111-2222-3333"],
        "raid_level": 5,
        "mount_point": "/mnt/data",
        "description": "Primary file store"
    }
)
print(resp.json())
```
</details>

---

#### `POST /api/config/reset_store` — Reinitialize Store

**Summary:** Resets a store back to its raw/unconfigured state.

**When to use:** Before reconfiguring a store with a different type, or to wipe the existing configuration.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs whose stores to reinitialize. |
| `reinit_type` | string | No | Reinitialization type. Must be a valid `ReInitType` value (case-insensitive). |

**Response (200):** Standard success envelope.

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing `uuids`, invalid `reinit_type` |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/reset_store \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "uuids": ["uuid-1111-2222-3333"],
    "reinit_type": "full"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/config/reset_store",
    headers={"Authorization": f"JWT {token}"},
    json={"uuids": ["uuid-1111-2222-3333"], "reinit_type": "full"}
)
```
</details>

---

#### `POST /api/config/mount` — Mount Bryck Store

**Summary:** Mounts an existing but unmounted Bryck store on the specified logical cards.

**When to use:** After a reboot, or when a configured store needs to be brought online.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs to mount. |
| `mount_point` | string | No | Target mount path. |
| `encryption_check` | boolean | No | Use encryption key file for mounting. |
| `encryption_option` | string | No | `"AWS_KMS"` for AWS key management. |
| `force_mount` | boolean | No | Force mount even if filesystem checks suggest caution. |
| `mountonreboot` | boolean | No | Persist mount across reboots. |
| `IoSize` | string | No | I/O block size. |
| `DataSync` | string | No | Sync mode. |

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing `uuids`, stores don't exist, store already mounted |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/mount \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "uuids": ["uuid-1111-2222-3333"],
    "mount_point": "/mnt/data"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/config/mount",
    headers={"Authorization": f"JWT {token}"},
    json={"uuids": ["uuid-1111-2222-3333"], "mount_point": "/mnt/data"}
)
```
</details>

---

#### `POST /api/config/eject` — Eject Bryck

**Summary:** Safely ejects the Bryck, unmounting stores and preparing the device for physical removal.

**When to use:** Before physically disconnecting the Bryck hardware.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | UUIDs of the Bryck(s) to eject. |
| `no_fs_check` | boolean | No | Skip filesystem integrity checks before ejecting. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/eject \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "uuids": ["uuid-1111-2222-3333"] }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/config/eject",
    headers={"Authorization": f"JWT {token}"},
    json={"uuids": ["uuid-1111-2222-3333"]}
)
```
</details>

---

#### `POST /api/config/armageddon` — Factory Reset

**Summary:** Triggers a complete factory reset of the Bryck system (destroys all data and configuration).

**When to use:** Only as a last resort. This is a destructive, irreversible operation.

**Authentication:** Required (JWT).

**Request Body:** None (empty JSON body `{}`).

**Response (200):** Standard success envelope.

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/armageddon \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```
</details>

---

#### `POST /api/config/shutdown` — Shutdown Bryck

**Summary:** Initiates a graceful shutdown of the Bryck system.

**When to use:** Before powering off the hardware. Ensures all stores are cleanly unmounted.

**Authentication:** Required (JWT).

**Request Body:** None (empty JSON body `{}`).

**Response (200):** Standard success envelope.

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/shutdown \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```
</details>

---

#### `POST /api/config/upgrade` — Start System Upgrade

**Summary:** Triggers a firmware/software upgrade using a previously uploaded build package.

**When to use:** After uploading a new build package via `POST /api/config/upload`.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `build_filename` | string | **Yes** | Name of the previously uploaded build file (e.g., `"tsecond-bryck-1.2.3.4.deb"`). |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/upgrade \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "build_filename": "tsecond-bryck-1.2.3.4.deb" }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/config/upgrade",
    headers={"Authorization": f"JWT {token}"},
    json={"build_filename": "tsecond-bryck-1.2.3.4.deb"}
)
```
</details>

---

#### `POST /api/config/upload` — Upload File / Upgrade Package

**Summary:** Uploads a file to the Bryck system. Used for encryption key files or upgrade packages.

**When to use:** Before running `POST /api/config/upgrade` (for upgrade packages) or before configuring encrypted stores.

**Authentication:** Required (JWT).

**Content-Type:** `multipart/form-data`

**Form Fields:**

| Field | Type | Required | Description |
|---|---|---|---|
| `type` | string | No | Set to `"upgrade"` when uploading a software package. |
| `file` | file | **Yes** | The binary file to upload. |

**Validation (when `type` = `"upgrade"`):**

- Filename must start with `tsecond-bryck-` followed by a version number (e.g., `tsecond-bryck-1.2.3.4.deb`).

**Response (200):** Standard success envelope.

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/upload \
  -H "Authorization: JWT <access_token>" \
  -F "type=upgrade" \
  -F "file=@tsecond-bryck-1.2.3.4.deb"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
with open("tsecond-bryck-1.2.3.4.deb", "rb") as f:
    resp = requests.post(
        "http://BRYCK_HOST/api/config/upload",
        headers={"Authorization": f"JWT {token}"},
        data={"type": "upgrade"},
        files={"file": f}
    )
```
</details>

---

#### `GET /api/config/getlogs` — Retrieve System Logs

**Summary:** Fetches system log entries from the database or journald, filtered by time period.

**When to use:** To display recent system events, errors, and warnings in a management UI or for troubleshooting.

**Authentication:** Required (JWT).

**Query Parameters:**

| Param | Type | Required | Description |
|---|---|---|---|
| `cursor` | string | No | Time filter. Values: `"Today"`, `"This week"`, `"Last 30 days"`, or a journald cursor string. Defaults to today. |

**Response (200):**

Array of log entries (newest first):

| Field | Type | Description |
|---|---|---|
| `id` | integer | Log entry ID (database source). |
| `timestamp` | string | Unix timestamp of the event. |
| `priority` | string | Severity: `"Alert"`, `"Critical"`, `"Error"`, `"Warning"`, `"Notice"`, `"Informational"`, `"Debug"`. |
| `message` | string | Log message text. |
| `read_status` | boolean | Whether the log has been marked as read (database source). |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET "http://BRYCK_HOST/api/config/getlogs?cursor=This%20week" \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/config/getlogs",
    headers={"Authorization": f"JWT {token}"},
    params={"cursor": "This week"}
)
logs = resp.json()["result"]
for log in logs:
    print(f"[{log['priority']}] {log['message']}")
```
</details>

---

#### `POST /api/config/marklog` — Mark Log(s) as Read

**Summary:** Marks one or all log entries as read in the database.

**When to use:** When a user acknowledges a log entry in the UI.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | integer | No | Specific log entry ID to mark as read. |
| `all` | any | No | If truthy, marks **all** logs as read. Takes precedence when both provided. |

<details>
<summary><b>curl example</b></summary>

```bash
# Mark single log
curl -X POST http://BRYCK_HOST/api/config/marklog \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "id": 42 }'

# Mark all logs as read
curl -X POST http://BRYCK_HOST/api/config/marklog \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "all": true }'
```
</details>

---

#### `GET /api/config/bryck_info` — Get Bryck Hardware Info

**Summary:** Returns detailed hardware information about the Bryck device.

**When to use:** To display Bryck hardware details (drives, state, model, serial number).

**Authentication:** Required (JWT).

**Response (200):** Bryck info object (structure depends on BryckInfoJob output).

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/config/bryck_info \
  -H "Authorization: JWT <access_token>"
```
</details>

---

#### `GET /api/config/tray_info` — Get Tray Info

**Summary:** Returns information about the Bryck tray.

**Authentication:** Required (JWT).

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/config/tray_info \
  -H "Authorization: JWT <access_token>"
```
</details>

---

#### `GET /api/config/server_info` — Get Server Info

**Summary:** Returns information about the host server (CPU, memory, OS, etc.).

**Authentication:** Required (JWT).

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/config/server_info \
  -H "Authorization: JWT <access_token>"
```
</details>

---

#### `GET /api/config/aws_connect` — Check AWS Configuration

**Summary:** Verifies that AWS CLI is installed and configured with valid credentials.

**When to use:** Before configuring AWS KMS encryption to ensure connectivity.

**Authentication:** Required (JWT).

**Response (200):**

```json
{
    "success": true,
    "error": {},
    "result": "Configured"
}
```

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | AWS CLI not installed or not configured |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/config/aws_connect \
  -H "Authorization: JWT <access_token>"
```
</details>

---

#### `POST /api/config/scan` — Scan Drives

**Summary:** Initiates a drive scan on the specified logical cards to detect new or changed drives.

**When to use:** After physically inserting new drives or if drives are not appearing.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs to scan. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/scan \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "uuids": ["uuid-1111-2222-3333"] }'
```
</details>

---

#### `POST /api/config/remove` — Remove Drives

**Summary:** Removes the specified drives from the system configuration.

**When to use:** Before physically removing drives from the Bryck.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | UUIDs of drives to remove. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/remove \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "uuids": ["uuid-1111-2222-3333"] }'
```
</details>

---

#### `POST /api/config/alert_user` — Subscribe to Alerts

**Summary:** Registers a user email to receive system alerts of the specified priority levels.

**When to use:** To set up email notifications for system events.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `user` | string | No | Display name for the subscriber. |
| `mailid` | string | No | Email address to receive alerts. Must be a valid email. |
| `alert_type` | string | No | Comma-separated alert levels: `"Alert"`, `"Critical"`, `"Error"`, `"Warning"`, `"Notice"`, `"Info"`. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/alert_user \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "user": "admin",
    "mailid": "admin@example.com",
    "alert_type": "Alert,Critical,Error"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/config/alert_user",
    headers={"Authorization": f"JWT {token}"},
    json={
        "user": "admin",
        "mailid": "admin@example.com",
        "alert_type": "Alert,Critical,Error"
    }
)
```
</details>

---

#### `POST /api/config/alert_user_update` — Update Alert Subscription

**Summary:** Updates the alert preferences for an existing subscriber.

**When to use:** To change which alert levels are sent to an already-subscribed email address.

**Authentication:** Required (JWT).

**Request Body:** Same as `POST /api/config/alert_user`.

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Email not already subscribed, invalid email, database unreachable |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/alert_user_update \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "user": "admin",
    "mailid": "admin@example.com",
    "alert_type": "Alert,Critical"
  }'
```
</details>

---

#### `POST /api/config/alert_user_delete` — Delete Alert Subscription

**Summary:** Removes an email from the alert subscription list.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `mailid` | string | **Yes** | Email address to unsubscribe. |

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Invalid email format, database unreachable |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/config/alert_user_delete \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{ "mailid": "admin@example.com" }'
```
</details>

---

#### `GET /api/config/alert_user_list` — List Alert Subscribers

**Summary:** Returns all registered alert subscribers and their alert preferences.

**Authentication:** Required (JWT).

**Response (200):**

Array of subscriber objects:

| Field | Type | Description |
|---|---|---|
| `username` | string | Display name of the subscriber. |
| `mailid` | string | Subscriber's email address. |
| `alerts` | string | Comma-separated list of alert levels (e.g., `"Alert,Critical,Error"`). |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/config/alert_user_list \
  -H "Authorization: JWT <access_token>"
```
</details>

**Example Response:**

```json
{
    "success": true,
    "error": {},
    "result": [
        {
            "username": "admin",
            "mailid": "admin@example.com",
            "alerts": "Alert,Critical,Error"
        }
    ]
}
```

---

### 5.3 Hardware — Brycks

Blueprint prefix: `/api/hardware/brycks`

---

#### `GET /api/hardware/brycks` — List Brycks

**Summary:** Returns a list of all Bryck devices with their status, linked tray ID, and logical card membership.

**When to use:** To enumerate physical Bryck devices and their operational status.

**Authentication:** Required (JWT).

**Response (200):**

```json
{
    "success": true,
    "error": {},
    "result": {
        "brycks": [
            {
                "id": "bryck-uuid-string",
                "name": "bryck0",
                "tray_id": "dde21e1c-f74f-4a19-8c6e-984e1e37de3a",
                "status": "running",
                "logical_card_ids": ["lc-uuid-1", "lc-uuid-2"]
            }
        ]
    }
}
```

**Response Fields:**

| Field | Type | Description |
|---|---|---|
| `id` | string | Unique identifier for the Bryck device. |
| `name` | string | Display name (e.g., `"bryck0"`). |
| `tray_id` | string | UUID of the tray this Bryck is installed in. |
| `status` | string | Process status of the bryckagent. |
| `logical_card_ids` | array\<string\> | Sorted list of logical card UUIDs belonging to this Bryck. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/hardware/brycks \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/hardware/brycks",
    headers={"Authorization": f"JWT {token}"}
)
brycks = resp.json()["result"]["brycks"]
for b in brycks:
    print(f"{b['name']}: {b['status']} — {len(b['logical_card_ids'])} logical cards")
```
</details>

---

### 5.4 Hardware — Logical Cards

Blueprint prefix: `/api/hardware/logical_cards`

---

#### `GET /api/hardware/logical_cards` — List Logical Cards

**Summary:** Returns all logical cards with their store status, network status, and drive inventory.

**When to use:** To display the state of individual compute/storage nodes within a Bryck.

**Authentication:** Required (JWT).

**Response (200):**

```json
{
    "success": true,
    "error": {},
    "result": {
        "logical_cards": [
            {
                "id": "lc-uuid-string",
                "name": "hostname-of-card",
                "status": {
                    "store": 1,
                    "network": 1
                },
                "drives": [
                    { "serial": "WD-ABC123", "model": "WD10EZEX", "size": "1TB" }
                ]
            }
        ]
    }
}
```

**Response Fields:**

| Field | Type | Description |
|---|---|---|
| `id` | string | UUID of the logical card. |
| `name` | string | Hostname of the logical card. |
| `status.store` | integer | `1` = UP, `0` = DOWN. Store health status. |
| `status.network` | integer | `1` = UP, `0` = DOWN. Network connectivity status. |
| `drives` | array | List of physical drives attached to this logical card. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/hardware/logical_cards \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/hardware/logical_cards",
    headers={"Authorization": f"JWT {token}"}
)
cards = resp.json()["result"]["logical_cards"]
for card in cards:
    store_ok = "UP" if card["status"]["store"] else "DOWN"
    net_ok = "UP" if card["status"]["network"] else "DOWN"
    print(f"{card['name']}: store={store_ok}, network={net_ok}, drives={len(card['drives'])}")
```
</details>

---

### 5.5 Hardware — Trays

Blueprint prefix: `/api/hardware/trays`

---

#### `GET /api/hardware/trays` — List Trays

**Summary:** Returns information about physical trays and their Bryck membership.

**When to use:** To display tray hardware status and which Brycks are installed.

**Authentication:** Required (JWT).

**Response (200):**

```json
{
    "success": true,
    "error": {},
    "result": {
        "trays": [
            {
                "id": "dde21e1c-f74f-4a19-8c6e-984e1e37de3a",
                "name": "tray0",
                "status": 1,
                "connections": 1,
                "bryck_ids": ["bryck-uuid-string"]
            }
        ]
    }
}
```

**Response Fields:**

| Field | Type | Description |
|---|---|---|
| `id` | string | UUID of the tray. |
| `name` | string | Display name (e.g., `"tray0"`). |
| `status` | integer | `1` = operational. |
| `connections` | integer | Number of active connections. |
| `bryck_ids` | array\<string\> | UUIDs of Brycks installed in this tray. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/hardware/trays \
  -H "Authorization: JWT <access_token>"
```
</details>

---

### 5.6 Network

Blueprint prefix: `/api/network`

---

#### `GET /api/network/info` — Get Network Configuration

**Summary:** Returns network interface details for all or specific logical cards plus the Bryck itself.

**When to use:** To display IP addresses, interfaces, and network status of the system.

**Authentication:** Required (JWT).

**Query Parameters:**

| Param | Type | Required | Description |
|---|---|---|---|
| `uuids` | string | No | Comma-separated list of UUIDs to filter. Returns all if omitted. |

**Response (200):**

Map of UUID → network info:

```json
{
    "success": true,
    "error": {},
    "result": {
        "lc-uuid-1": {
            "ip": "192.168.1.10",
            "netmask": "255.255.255.0",
            "gateway": "192.168.1.1",
            "interface": "eth0"
        },
        "bryck-uuid": {
            "ip": "192.168.1.5",
            "netmask": "255.255.255.0",
            "gateway": "192.168.1.1"
        }
    }
}
```

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET "http://BRYCK_HOST/api/network/info?uuids=lc-uuid-1" \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/network/info",
    headers={"Authorization": f"JWT {token}"},
    params={"uuids": "lc-uuid-1"}
)
net_info = resp.json()["result"]
```
</details>

---

#### `POST /api/network/configure` — Configure Network Interface

**Summary:** Configures network settings (IP, DHCP, gateway, DNS, NTP, MTU) on specified logical cards.

**When to use:** During initial setup or when changing network configuration.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs to configure. |
| `interface_name` | string | No | Network interface name (e.g., `"eth0"`). |
| `dhcp` | boolean | No | Enable DHCP. When true, static fields are ignored. |
| `ip` | string | No | Static IPv4 address. |
| `netmask` | string | No | Subnet mask (e.g., `"255.255.255.0"`). |
| `gateway` | string | No | Default gateway IP. |
| `nameservers` | array\<string\> | No | DNS server addresses. |
| `ntp_server` | string | No | NTP server address. |
| `mtu` | integer | No | Maximum Transmission Unit size. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/network/configure \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "uuids": ["lc-uuid-1"],
    "interface_name": "eth0",
    "dhcp": false,
    "ip": "192.168.1.100",
    "netmask": "255.255.255.0",
    "gateway": "192.168.1.1",
    "nameservers": ["8.8.8.8", "8.8.4.4"],
    "mtu": 1500
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/network/configure",
    headers={"Authorization": f"JWT {token}"},
    json={
        "uuids": ["lc-uuid-1"],
        "interface_name": "eth0",
        "ip": "192.168.1.100",
        "netmask": "255.255.255.0",
        "gateway": "192.168.1.1",
        "nameservers": ["8.8.8.8"],
        "mtu": 1500
    }
)
```
</details>

---

#### `POST /api/network/configure_ntp` — Configure NTP Server

**Summary:** Sets the NTP server for the specified logical cards.

**When to use:** When the time source needs to be changed independently of other network settings.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs. |
| `ntp_server` | string | **Yes** | NTP server address or hostname. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/network/configure_ntp \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "uuids": ["lc-uuid-1"],
    "ntp_server": "pool.ntp.org"
  }'
```
</details>

---

### 5.7 Tasks

Blueprint prefix: `/api/tasks`

---

#### `GET /api/tasks/list` — List Tasks

**Summary:** Returns all tracked tasks (data transfers, verifications, state captures) with their progress.

**When to use:** To display a task dashboard or poll for transfer completion.

**Authentication:** Required (JWT).

**Query Parameters:**

| Param | Type | Required | Description |
|---|---|---|---|
| `task_type` | string | No | Filter by type: `"TRANSFER"`, `"VERIFICATION"`, `"CAPTURE_BRYCK_STATE"`. Returns all if omitted. |

**Response (200):**

Array of task objects:

| Field | Type | Description |
|---|---|---|
| `task_id` | string | Unique task identifier. |
| `task_type` | string | `"TRANSFER"`, `"VERIFICATION"`, or `"CAPTURE_BRYCK_STATE"`. |
| `state` | string | `"ACTIVE"`, `"COMPLETED"`, `"FAILED"`, `"STALE"`. |
| `started_at` | integer | Unix timestamp when the task started. |
| `last_updated` | integer | Unix timestamp of last progress update. |
| `percent_completed` | integer | 0–100 progress (transfer/verification). |
| `total_bytes` | integer | Total data size in bytes (transfer/verification). |
| `copied_bytes` | integer | Bytes copied so far (transfer only). |
| `throughput` | integer | Current throughput in bytes/sec (transfer only). |
| `src` | string | Source path (transfer only). |
| `dst` | string | Destination path (transfer only). |
| `path` | string | Verification path (verification only). |
| `file_name` | string | Output file name (capture_bryck_state only). |
| `errors` | array | List of error objects `{ timestamp, error_level, error_msg }`. |

<details>
<summary><b>curl example</b></summary>

```bash
# All tasks
curl -X GET http://BRYCK_HOST/api/tasks/list \
  -H "Authorization: JWT <access_token>"

# Only transfers
curl -X GET "http://BRYCK_HOST/api/tasks/list?task_type=TRANSFER" \
  -H "Authorization: JWT <access_token>"
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/tasks/list",
    headers={"Authorization": f"JWT {token}"},
    params={"task_type": "TRANSFER"}
)
tasks = resp.json()["result"]
for task in tasks:
    print(f"[{task['state']}] {task['task_type']} — {task.get('percent_completed', 'N/A')}%")
```
</details>

**Example Response:**

```json
{
    "success": true,
    "error": {},
    "result": [
        {
            "task_id": "abc-123",
            "task_type": "TRANSFER",
            "state": "ACTIVE",
            "started_at": 1711540000,
            "last_updated": 1711540060,
            "src": "/data/source/",
            "dst": "/bryck/backup/",
            "total_bytes": 1073741824,
            "copied_bytes": 536870912,
            "percent_completed": 50,
            "throughput": 104857600
        }
    ]
}
```

---

#### `POST /api/tasks/transfer` — Start Data Transfer

**Summary:** Initiates a data copy operation between a source and destination path on a logical card.

**When to use:** To copy data to or from the Bryck. Either `src` or `dst` must start with `/bryck`.

**Prerequisites:** The Bryck must be in `"Mounted"` state.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `logical_card` | string | **Yes** | Logical card identifier to run the transfer on. |
| `src` | string | **Yes** | Source path. Must start with `/bryck` if dst does not. |
| `dst` | string | **Yes** | Destination path. Must start with `/bryck` if src does not. |
| `generate_crc` | boolean | No | Generate CRC checksums during transfer (default `false`). |

**Validation:**

- Bryck must be mounted.
- Either `src` or `dst` must start with `/bryck`.

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing fields, Bryck not mounted, neither path starts with `/bryck` |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/tasks/transfer \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "logical_card": "le0",
    "src": "/data/important-files/",
    "dst": "/bryck/backup/important-files/",
    "generate_crc": true
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/tasks/transfer",
    headers={"Authorization": f"JWT {token}"},
    json={
        "logical_card": "le0",
        "src": "/data/important-files/",
        "dst": "/bryck/backup/important-files/",
        "generate_crc": True
    }
)
```
</details>

---

#### `POST /api/tasks/verify` — Start Data Verification

**Summary:** Initiates CRC verification of data at the specified path on a logical card.

**When to use:** After a transfer completes to verify data integrity.

**Prerequisites:** The Bryck must be in `"Mounted"` state.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `logical_card` | string | **Yes** | Logical card identifier. |
| `path` | string | **Yes** | Path to verify. |

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing fields, Bryck not mounted |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/tasks/verify \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "logical_card": "le0",
    "path": "/bryck/backup/important-files/"
  }'
```
</details>

---

#### `POST /api/tasks/dismiss` — Dismiss Tasks

**Summary:** Removes completed, failed, or stale tasks from the tracked task list.

**When to use:** To clear finished or errored tasks from the task dashboard.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `logical_card` | string | **Yes** | Logical card ID, or `"*"` for all cards (only with `states`). |
| `task_id` | string | No | Specific task ID to dismiss (higher priority than `states`). |
| `task_type` | string | No | Filter: `"TRANSFER"`, `"VERIFICATION"`, `"CAPTURE_BRYCK_STATE"`. |
| `states` | array\<string\> | No | States to dismiss: `"STALE"`, `"FAILED"`, `"COMPLETED"`. |

**Note:** Either `task_id` or `states` must be provided.

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing `logical_card`, invalid `task_type`, invalid states, task not in dismissible state |

<details>
<summary><b>curl example</b></summary>

```bash
# Dismiss a specific task
curl -X POST http://BRYCK_HOST/api/tasks/dismiss \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "logical_card": "le0",
    "task_id": "abc-123"
  }'

# Dismiss all completed transfers
curl -X POST http://BRYCK_HOST/api/tasks/dismiss \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "logical_card": "*",
    "task_type": "TRANSFER",
    "states": ["COMPLETED", "FAILED"]
  }'
```
</details>

---

#### `POST /api/tasks/capture_bryck_state` — Capture Diagnostic State

**Summary:** Initiates a system diagnostic data collection, producing a downloadable `bryck_state.tgz` file.

**When to use:** For troubleshooting — generates a diagnostic bundle that can be downloaded via `/api/download?name=bryck_report`.

**Authentication:** Required (JWT).

**Request Body:** None (empty JSON body `{}`).

**Error Responses:**

| Status | Condition |
|---|---|
| 409 | Another capture task is already in progress |
| 400 | Invalid state |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/tasks/capture_bryck_state \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{}'
```
</details>

---

### 5.8 Download

Blueprint prefix: `/api/download`

---

#### `GET /api/download` — Download File

**Summary:** Downloads a named file from the server's downloads directory.

**When to use:** To retrieve client software, user guides, or diagnostic reports.

**Authentication:** Required (JWT).

**Query Parameters:**

| Param | Type | Required | Description |
|---|---|---|---|
| `name` | string | **Yes** | File identifier. One of: `"bryckcp_client"`, `"user_guide"`, `"bryck_report"`. |
| `type` | string | No | File extension filter (e.g., `"exe"`, `"pdf"`, `"tgz"`). |

**Supported Names:**

| Name | Pattern Matched | Description |
|---|---|---|
| `bryckcp_client` | `bryckcp*` | Bryck copy client software |
| `user_guide` | `*User's Guide*` | Product user guide |
| `bryck_report` | `bryck_state.tgz` | Diagnostic state bundle |

**Response:** Binary file as attachment (not JSON envelope).

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Unsupported `name`, ambiguous match (multiple files) |
| 404 | File not found or not readable |

<details>
<summary><b>curl example</b></summary>

```bash
# Download client software
curl -X GET "http://BRYCK_HOST/api/download?name=bryckcp_client&type=exe" \
  -H "Authorization: JWT <access_token>" \
  -o bryckcp_client.exe

# Download diagnostic report
curl -X GET "http://BRYCK_HOST/api/download?name=bryck_report" \
  -H "Authorization: JWT <access_token>" \
  -o bryck_state.tgz
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get(
    "http://BRYCK_HOST/api/download",
    headers={"Authorization": f"JWT {token}"},
    params={"name": "bryck_report"}
)
with open("bryck_state.tgz", "wb") as f:
    f.write(resp.content)
```
</details>

---

### 5.9 External Storage

Blueprint prefix: `/api/external_storage`

---

#### `POST /api/external_storage/mount` — Mount Remote Storage

**Summary:** Mounts a remote NFS export on the Bryck's logical cards.

**When to use:** To access data from a remote NFS server for ingest or backup.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs to mount the remote storage on. |
| `mount_point` | string | **Yes** | Local mount path (must start with `/`). |
| `remote_address` | string | **Yes** | IP or hostname of the remote NFS server. |
| `export_path` | string | **Yes** | Remote export path (must start with `/`). |

**Validation:**

- `mount_point` must start with `/`.
- `export_path` must start with `/`.

**Error Responses:**

| Status | Condition |
|---|---|
| 400 | Missing fields, paths not starting with `/` |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/external_storage/mount \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "uuids": ["lc-uuid-1"],
    "mount_point": "/mnt/remote",
    "remote_address": "192.168.1.200",
    "export_path": "/exports/data"
  }'
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.post(
    "http://BRYCK_HOST/api/external_storage/mount",
    headers={"Authorization": f"JWT {token}"},
    json={
        "uuids": ["lc-uuid-1"],
        "mount_point": "/mnt/remote",
        "remote_address": "192.168.1.200",
        "export_path": "/exports/data"
    }
)
```
</details>

---

#### `POST /api/external_storage/unmount` — Unmount Remote Storage

**Summary:** Unmounts a previously mounted remote NFS export.

**When to use:** When remote storage access is no longer needed.

**Authentication:** Required (JWT).

**Request Body:**

| Field | Type | Required | Description |
|---|---|---|---|
| `uuids` | array\<string\> | **Yes** | Logical card UUIDs. |
| `mount_point` | string | **Yes** | The mount point to unmount (must start with `/`). |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X POST http://BRYCK_HOST/api/external_storage/unmount \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{
    "uuids": ["lc-uuid-1"],
    "mount_point": "/mnt/remote"
  }'
```
</details>

---

### 5.10 Version

Blueprint prefix: `/api/version`

---

#### `GET /api/version` — Get Product Version

**Summary:** Returns the product version from the manifest file.

**When to use:** To display the API/product version in a UI or for compatibility checks.

**Authentication:** **Not required** — this is a public endpoint.

**Response (200):**

```json
{
    "success": true,
    "error": {},
    "result": {
        "version": "1.2.3.4"
    }
}
```

| Field | Type | Description |
|---|---|---|
| `version` | string | Product version string read from the manifest. |

<details>
<summary><b>curl example</b></summary>

```bash
curl -X GET http://BRYCK_HOST/api/version
```
</details>

<details>
<summary><b>Python example</b></summary>

```python
resp = requests.get("http://BRYCK_HOST/api/version")
print(resp.json()["result"]["version"])
```
</details>

---

## 6. Data Models & Schemas

### User

The `User` model manages authentication credentials. Users are stored in the application's configuration file (not in the database).

| Property | Type | Description |
|---|---|---|
| `username` | string | Login identifier (e.g., `"admin"`). |
| `password_hash` | string | PBKDF2-SHA512 hash of the user's password. |
| `id` | string | Unique user identifier. |

**Methods:**

| Method | Description |
|---|---|
| `authenticate(username, password)` | Validates credentials and returns User on success. |
| `verify_password(password)` | Checks plaintext password against stored hash. |
| `change_password(new_password)` | Hashes and persists a new password. |
| `password_complexity_check(password)` | Returns a dict of (rule → bool) for strength validation. |

---

### Configuration

Reads store configuration from disk (BryckStore or TrayStore) via the bryck agent library.

| Property | Type | Description |
|---|---|---|
| `logical_cards` | object | Map of UUID → logical card config (properties, drives, conditions). |
| `properties` | object | System-level properties (network_info, etc.). |
| `uuid` | string | System/Bryck UUID. |

---

### Task

Tasks represent asynchronous operations tracked in memory via `TaskMonitor`.

| Property | Type | Applies To | Description |
|---|---|---|---|
| `task_id` | string | All | Unique task identifier. |
| `task_type` | string | All | `TRANSFER`, `VERIFICATION`, `CAPTURE_BRYCK_STATE`. |
| `state` | string | All | `ACTIVE`, `COMPLETED`, `FAILED`, `STALE`. |
| `started_at` | integer | All | Unix timestamp when the task was created. |
| `last_updated` | integer | All | Unix timestamp of the last update. |
| `store` | string | Transfer, Verification | Logical card identifier. |
| `src` | string | Transfer | Source path. |
| `dst` | string | Transfer | Destination path. |
| `path` | string | Verification | Path being verified. |
| `total_bytes` | integer | Transfer, Verification | Total data size. |
| `copied_bytes` | integer | Transfer | Bytes transferred so far. |
| `verified_bytes` | integer | Verification | Bytes verified so far. |
| `percent_completed` | integer | Transfer, Verification | 0–100 progress indicator. |
| `throughput` | integer | Transfer | Bytes per second. |
| `file_name` | string | Capture | Output archive filename. |
| `errors` | array | Transfer, Verification | `[{ timestamp, error_level, error_msg }]`. |

**State Lifecycle:**

```
ACTIVE  ──(progress 100%)──▶  COMPLETED
   │                               │
   ├──(error)──▶  FAILED           │ (can be dismissed)
   │                               │
   └──(no update for 60s)──▶  STALE ──▶ (can be dismissed)
```

---

### Log Entry

| Property | Type | Description |
|---|---|---|
| `id` | integer | Database row ID. |
| `timestamp` | string | Unix timestamp of the event. |
| `priority` | string | `Alert`, `Critical`, `Error`, `Warning`, `Notice`, `Informational`, `Debug`. |
| `message` | string | Log message content. |
| `read_status` | boolean | Whether the entry has been acknowledged. |

---

### Alert Subscriber

| Property | Type | Description |
|---|---|---|
| `username` | string | Display name. |
| `mailid` | string | Subscriber email address. |
| `alerts` | string | Comma-separated alert levels. |

---

### Standard Error Response

```yaml
ErrorResponse:
  type: object
  properties:
    success:
      type: boolean
      example: false
    error:
      type: object
      properties:
        message:
          type: string
    result:
      type: object
```

### Standard Success Response

```yaml
SuccessResponse:
  type: object
  properties:
    success:
      type: boolean
      example: true
    error:
      type: object
    result:
      type: object
      description: Endpoint-specific payload
```

---

## 7. OpenAPI 3.1 Specification

```yaml
openapi: "3.1.0"

info:
  title: Bryck API
  description: >
    RESTful API for managing Bryck hardware storage appliances.
    Provides endpoints for authentication, storage configuration,
    hardware monitoring, data transfer, network management, and system administration.
  version: "1.0.0"
  contact:
    name: Tsecond
  license:
    name: MIT

servers:
  - url: http://localhost:8080/api
    description: Local development
  - url: http://{host}:{port}/api
    description: Bryck appliance
    variables:
      host:
        default: "192.168.1.1"
      port:
        default: "8080"

security:
  - BearerAuth: []

components:

  securitySchemes:
    BearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
      description: "Pass token from POST /api/auth. Header: Authorization: JWT <token>"

  schemas:

    SuccessEnvelope:
      type: object
      properties:
        success:
          type: boolean
          example: true
        error:
          type: object
        result:
          type: object

    ErrorEnvelope:
      type: object
      properties:
        success:
          type: boolean
          example: false
        error:
          type: object
          properties:
            message:
              type: string
        result:
          type: object

    TokenResponse:
      type: object
      properties:
        access_token:
          type: string
          example: "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
        expires:
          type: integer
          example: 1711540800

    PasswordComplexity:
      type: object
      properties:
        password_ok:
          type: boolean
        length_error:
          type: boolean
        digit_error:
          type: boolean
        uppercase_error:
          type: boolean
        lowercase_error:
          type: boolean
        symbol_error:
          type: boolean

    Bryck:
      type: object
      properties:
        id:
          type: string
        name:
          type: string
          example: "bryck0"
        tray_id:
          type: string
          format: uuid
        status:
          type: string
        logical_card_ids:
          type: array
          items:
            type: string

    LogicalCard:
      type: object
      properties:
        id:
          type: string
        name:
          type: string
        status:
          type: object
          properties:
            store:
              type: integer
              enum: [0, 1]
            network:
              type: integer
              enum: [0, 1]
        drives:
          type: array
          items:
            type: object

    Tray:
      type: object
      properties:
        id:
          type: string
          format: uuid
        name:
          type: string
          example: "tray0"
        status:
          type: integer
          enum: [0, 1]
        connections:
          type: integer
        bryck_ids:
          type: array
          items:
            type: string

    Task:
      type: object
      properties:
        task_id:
          type: string
        task_type:
          type: string
          enum: [TRANSFER, VERIFICATION, CAPTURE_BRYCK_STATE]
        state:
          type: string
          enum: [ACTIVE, COMPLETED, FAILED, STALE]
        started_at:
          type: integer
        last_updated:
          type: integer
        percent_completed:
          type: integer
        total_bytes:
          type: integer
        copied_bytes:
          type: integer
        throughput:
          type: integer
        src:
          type: string
        dst:
          type: string
        path:
          type: string
        file_name:
          type: string
        errors:
          type: array
          items:
            type: object
            properties:
              timestamp:
                type: integer
              error_level:
                type: string
              error_msg:
                type: string

    LogEntry:
      type: object
      properties:
        id:
          type: integer
        timestamp:
          type: string
        priority:
          type: string
          enum: [Alert, Critical, Error, Warning, Notice, Informational, Debug]
        message:
          type: string
        read_status:
          type: boolean

    AlertSubscriber:
      type: object
      properties:
        username:
          type: string
        mailid:
          type: string
          format: email
        alerts:
          type: string
          example: "Alert,Critical,Error"

    Version:
      type: object
      properties:
        version:
          type: string
          example: "1.2.3.4"

paths:

  /auth:
    post:
      tags: [Authentication]
      summary: Obtain JWT Token
      description: Authenticates a user with username and password, returns a JWT token.
      security: []
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [username, password]
              properties:
                username:
                  type: string
                password:
                  type: string
      responses:
        "200":
          description: Authentication successful
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        $ref: "#/components/schemas/TokenResponse"
        "400":
          description: Missing or empty credentials
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/ErrorEnvelope"
        "401":
          description: Invalid credentials
          content:
            application/json:
              schema:
                $ref: "#/components/schemas/ErrorEnvelope"

  /auth/refresh:
    post:
      tags: [Authentication]
      summary: Refresh JWT Token
      description: Returns a fresh JWT token with extended expiration.
      responses:
        "200":
          description: Token refreshed
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        $ref: "#/components/schemas/TokenResponse"
        "401":
          description: Invalid or expired token

  /auth/change_password:
    post:
      tags: [Authentication]
      summary: Change admin password
      description: Changes the admin user's password with complexity validation.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [username, old_password, new_password]
              properties:
                username:
                  type: string
                  example: "admin"
                old_password:
                  type: string
                new_password:
                  type: string
      responses:
        "200":
          description: Password changed
        "400":
          description: Validation error (weak password, same as old, etc.)
        "401":
          description: Unauthorized

  /config/info:
    get:
      tags: [Configuration]
      summary: Get system configuration and status
      description: Returns complete system info including hardware, logical cards, build version, and upgrade status.
      responses:
        "200":
          description: System info returned

  /config/update:
    post:
      tags: [Configuration]
      summary: Configure store
      description: Creates or reconfigures a FILE_STORE or BLOCK_STORE on specified logical cards.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [store_type, uuids]
              properties:
                store_type:
                  type: string
                  enum: [FILE_STORE, BLOCK_STORE, STORE]
                uuids:
                  type: array
                  items:
                    type: string
                raid_level:
                  type: integer
                  enum: [0, 5, 6, 7]
                mount_point:
                  type: string
                export_options:
                  type: string
                acl:
                  type: array
                  items:
                    type: string
                  maxItems: 100
                iqn:
                  type: string
                suffix:
                  type: string
                description:
                  type: string
                encryption_check:
                  type: boolean
                encryption_option:
                  type: string
                  enum: [AWS_KMS]
                mountonreboot:
                  type: boolean
                IoSize:
                  type: string
                  default: "2048"
                DataSync:
                  type: string
                  default: "application sync"
                dedup:
                  type: boolean
                compress:
                  type: boolean
      responses:
        "200":
          description: Store configured
        "400":
          description: Validation error

  /config/reset_store:
    post:
      tags: [Configuration]
      summary: Reinitialize store
      description: Resets a store to unconfigured state.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                reinit_type:
                  type: string
      responses:
        "200":
          description: Store reinitialized
        "400":
          description: Validation error

  /config/mount:
    post:
      tags: [Configuration]
      summary: Mount Bryck store
      description: Mounts a configured but unmounted store.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                mount_point:
                  type: string
                encryption_check:
                  type: boolean
                encryption_option:
                  type: string
                force_mount:
                  type: boolean
                mountonreboot:
                  type: boolean
                IoSize:
                  type: string
                DataSync:
                  type: string
      responses:
        "200":
          description: Store mounted
        "400":
          description: Validation error

  /config/eject:
    post:
      tags: [Configuration]
      summary: Eject Bryck
      description: Safely unmounts and ejects the Bryck for physical removal.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                no_fs_check:
                  type: boolean
      responses:
        "200":
          description: Bryck ejected

  /config/armageddon:
    post:
      tags: [Configuration]
      summary: Factory reset
      description: Destroys all data and configuration (irreversible).
      responses:
        "200":
          description: Factory reset initiated

  /config/shutdown:
    post:
      tags: [Configuration]
      summary: Shutdown Bryck
      description: Gracefully shuts down the Bryck system.
      responses:
        "200":
          description: Shutdown initiated

  /config/upgrade:
    post:
      tags: [Configuration]
      summary: Start system upgrade
      description: Applies a previously uploaded software package.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [build_filename]
              properties:
                build_filename:
                  type: string
      responses:
        "200":
          description: Upgrade started

  /config/upload:
    post:
      tags: [Configuration]
      summary: Upload file or upgrade package
      description: Uploads a binary file (key file or upgrade package).
      requestBody:
        required: true
        content:
          multipart/form-data:
            schema:
              type: object
              required: [file]
              properties:
                type:
                  type: string
                  enum: [upgrade]
                file:
                  type: string
                  format: binary
      responses:
        "200":
          description: File uploaded

  /config/getlogs:
    get:
      tags: [Configuration]
      summary: Retrieve system logs
      description: Fetches log entries filtered by time period.
      parameters:
        - name: cursor
          in: query
          schema:
            type: string
            enum: [Today, This week, Last 30 days]
      responses:
        "200":
          description: Logs retrieved
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        type: array
                        items:
                          $ref: "#/components/schemas/LogEntry"

  /config/marklog:
    post:
      tags: [Configuration]
      summary: Mark log(s) as read
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                id:
                  type: integer
                all:
                  type: boolean
      responses:
        "200":
          description: Logs marked as read
        "400":
          description: Database unreachable

  /config/bryck_info:
    get:
      tags: [Configuration]
      summary: Get Bryck hardware info
      responses:
        "200":
          description: Bryck info returned

  /config/tray_info:
    get:
      tags: [Configuration]
      summary: Get tray info
      responses:
        "200":
          description: Tray info returned

  /config/server_info:
    get:
      tags: [Configuration]
      summary: Get server info
      responses:
        "200":
          description: Server info returned

  /config/aws_connect:
    get:
      tags: [Configuration]
      summary: Check AWS configuration
      responses:
        "200":
          description: AWS is configured
        "400":
          description: AWS not configured

  /config/scan:
    post:
      tags: [Configuration]
      summary: Scan drives
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
      responses:
        "200":
          description: Scan initiated

  /config/remove:
    post:
      tags: [Configuration]
      summary: Remove drives
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
      responses:
        "200":
          description: Drives removed

  /config/alert_user:
    post:
      tags: [Alerts]
      summary: Subscribe to alerts
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                user:
                  type: string
                mailid:
                  type: string
                  format: email
                alert_type:
                  type: string
                  example: "Alert,Critical,Error"
      responses:
        "200":
          description: Subscription created
        "400":
          description: Invalid email or DB unreachable

  /config/alert_user_update:
    post:
      tags: [Alerts]
      summary: Update alert subscription
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                user:
                  type: string
                mailid:
                  type: string
                  format: email
                alert_type:
                  type: string
      responses:
        "200":
          description: Subscription updated
        "400":
          description: Email not subscribed

  /config/alert_user_delete:
    post:
      tags: [Alerts]
      summary: Delete alert subscription
      requestBody:
        content:
          application/json:
            schema:
              type: object
              required: [mailid]
              properties:
                mailid:
                  type: string
                  format: email
      responses:
        "200":
          description: Subscription deleted
        "400":
          description: Invalid email

  /config/alert_user_list:
    get:
      tags: [Alerts]
      summary: List alert subscribers
      responses:
        "200":
          description: Subscribers returned
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        type: array
                        items:
                          $ref: "#/components/schemas/AlertSubscriber"

  /hardware/brycks:
    get:
      tags: [Hardware]
      summary: List Brycks
      description: Returns all Bryck devices with status and logical card membership.
      responses:
        "200":
          description: Brycks listed
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        type: object
                        properties:
                          brycks:
                            type: array
                            items:
                              $ref: "#/components/schemas/Bryck"

  /hardware/logical_cards:
    get:
      tags: [Hardware]
      summary: List Logical Cards
      description: Returns all logical cards with store/network status and drives.
      responses:
        "200":
          description: Logical cards listed
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        type: object
                        properties:
                          logical_cards:
                            type: array
                            items:
                              $ref: "#/components/schemas/LogicalCard"

  /hardware/trays:
    get:
      tags: [Hardware]
      summary: List Trays
      description: Returns physical tray info and Bryck membership.
      responses:
        "200":
          description: Trays listed
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        type: object
                        properties:
                          trays:
                            type: array
                            items:
                              $ref: "#/components/schemas/Tray"

  /network/info:
    get:
      tags: [Network]
      summary: Get network configuration
      parameters:
        - name: uuids
          in: query
          schema:
            type: string
          description: Comma-separated UUIDs to filter
      responses:
        "200":
          description: Network info returned

  /network/configure:
    post:
      tags: [Network]
      summary: Configure network interface
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                interface_name:
                  type: string
                dhcp:
                  type: boolean
                ip:
                  type: string
                  format: ipv4
                netmask:
                  type: string
                gateway:
                  type: string
                  format: ipv4
                nameservers:
                  type: array
                  items:
                    type: string
                ntp_server:
                  type: string
                mtu:
                  type: integer
      responses:
        "200":
          description: Network configured

  /network/configure_ntp:
    post:
      tags: [Network]
      summary: Configure NTP server
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids, ntp_server]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                ntp_server:
                  type: string
      responses:
        "200":
          description: NTP configured

  /tasks/list:
    get:
      tags: [Tasks]
      summary: List tasks
      parameters:
        - name: task_type
          in: query
          schema:
            type: string
            enum: [TRANSFER, VERIFICATION, CAPTURE_BRYCK_STATE]
      responses:
        "200":
          description: Tasks listed
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        type: array
                        items:
                          $ref: "#/components/schemas/Task"

  /tasks/transfer:
    post:
      tags: [Tasks]
      summary: Start data transfer
      description: Initiates a copy from src to dst. One path must start with /bryck.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [logical_card, src, dst]
              properties:
                logical_card:
                  type: string
                src:
                  type: string
                dst:
                  type: string
                generate_crc:
                  type: boolean
                  default: false
      responses:
        "200":
          description: Transfer initiated
        "400":
          description: Validation error (not mounted, invalid paths)

  /tasks/verify:
    post:
      tags: [Tasks]
      summary: Start data verification
      description: Initiates CRC verification at the specified path.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [logical_card, path]
              properties:
                logical_card:
                  type: string
                path:
                  type: string
      responses:
        "200":
          description: Verification initiated
        "400":
          description: Validation error

  /tasks/dismiss:
    post:
      tags: [Tasks]
      summary: Dismiss tasks
      description: Removes completed, failed or stale tasks from tracking.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [logical_card]
              properties:
                logical_card:
                  type: string
                task_id:
                  type: string
                task_type:
                  type: string
                  enum: [TRANSFER, VERIFICATION, CAPTURE_BRYCK_STATE]
                states:
                  type: array
                  items:
                    type: string
                    enum: [STALE, FAILED, COMPLETED]
      responses:
        "200":
          description: Tasks dismissed
        "400":
          description: Validation error

  /tasks/capture_bryck_state:
    post:
      tags: [Tasks]
      summary: Capture diagnostic state
      description: Collects system diagnostics into a downloadable archive.
      responses:
        "200":
          description: Capture initiated
        "409":
          description: Another capture already in progress

  /download:
    get:
      tags: [Download]
      summary: Download file
      parameters:
        - name: name
          in: query
          required: true
          schema:
            type: string
            enum: [bryckcp_client, user_guide, bryck_report]
        - name: type
          in: query
          schema:
            type: string
          description: File extension filter
      responses:
        "200":
          description: File download (binary)
          content:
            application/octet-stream:
              schema:
                type: string
                format: binary
        "400":
          description: Unsupported name or ambiguous match
        "404":
          description: File not found

  /external_storage/mount:
    post:
      tags: [External Storage]
      summary: Mount remote NFS storage
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids, mount_point, remote_address, export_path]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                mount_point:
                  type: string
                remote_address:
                  type: string
                export_path:
                  type: string
      responses:
        "200":
          description: Remote storage mounted
        "400":
          description: Validation error

  /external_storage/unmount:
    post:
      tags: [External Storage]
      summary: Unmount remote storage
      requestBody:
        required: true
        content:
          application/json:
            schema:
              type: object
              required: [uuids, mount_point]
              properties:
                uuids:
                  type: array
                  items:
                    type: string
                mount_point:
                  type: string
      responses:
        "200":
          description: Remote storage unmounted
        "400":
          description: Validation error

  /version:
    get:
      tags: [Version]
      summary: Get product version
      security: []
      responses:
        "200":
          description: Version returned
          content:
            application/json:
              schema:
                allOf:
                  - $ref: "#/components/schemas/SuccessEnvelope"
                  - type: object
                    properties:
                      result:
                        $ref: "#/components/schemas/Version"
```

---

## Endpoint Summary Table

| # | Method | Path | Auth | Description |
|---|---|---|---|---|
| 1 | POST | `/api/auth` | No | Obtain JWT token |
| 2 | POST | `/api/auth/refresh` | Yes | Refresh JWT token |
| 3 | POST | `/api/auth/change_password` | Yes | Change admin password |
| 4 | GET | `/api/config/info` | Yes | Get full system configuration |
| 5 | POST | `/api/config/update` | Yes | Configure store (FILE/BLOCK) |
| 6 | POST | `/api/config/reset_store` | Yes | Reinitialize store |
| 7 | POST | `/api/config/mount` | Yes | Mount Bryck store |
| 8 | POST | `/api/config/eject` | Yes | Eject Bryck |
| 9 | POST | `/api/config/armageddon` | Yes | Factory reset (destructive) |
| 10 | POST | `/api/config/shutdown` | Yes | Shutdown system |
| 11 | POST | `/api/config/upgrade` | Yes | Start software upgrade |
| 12 | POST | `/api/config/upload` | Yes | Upload file / upgrade package |
| 13 | GET | `/api/config/getlogs` | Yes | Retrieve system logs |
| 14 | POST | `/api/config/marklog` | Yes | Mark log(s) as read |
| 15 | GET | `/api/config/bryck_info` | Yes | Get Bryck hardware info |
| 16 | GET | `/api/config/tray_info` | Yes | Get tray info |
| 17 | GET | `/api/config/server_info` | Yes | Get server info |
| 18 | GET | `/api/config/aws_connect` | Yes | Check AWS configuration |
| 19 | POST | `/api/config/scan` | Yes | Scan for drives |
| 20 | POST | `/api/config/remove` | Yes | Remove drives |
| 21 | POST | `/api/config/alert_user` | Yes | Subscribe to alerts |
| 22 | POST | `/api/config/alert_user_update` | Yes | Update alert subscription |
| 23 | POST | `/api/config/alert_user_delete` | Yes | Delete alert subscription |
| 24 | GET | `/api/config/alert_user_list` | Yes | List alert subscribers |
| 25 | GET | `/api/hardware/brycks` | Yes | List Bryck devices |
| 26 | GET | `/api/hardware/logical_cards` | Yes | List logical cards |
| 27 | GET | `/api/hardware/trays` | Yes | List trays |
| 28 | GET | `/api/network/info` | Yes | Get network configuration |
| 29 | POST | `/api/network/configure` | Yes | Configure network interface |
| 30 | POST | `/api/network/configure_ntp` | Yes | Configure NTP server |
| 31 | GET | `/api/tasks/list` | Yes | List tracked tasks |
| 32 | POST | `/api/tasks/transfer` | Yes | Start data transfer |
| 33 | POST | `/api/tasks/verify` | Yes | Start data verification |
| 34 | POST | `/api/tasks/dismiss` | Yes | Dismiss finished tasks |
| 35 | POST | `/api/tasks/capture_bryck_state` | Yes | Capture diagnostic bundle |
| 36 | GET | `/api/download` | Yes | Download file |
| 37 | POST | `/api/external_storage/mount` | Yes | Mount remote NFS storage |
| 38 | POST | `/api/external_storage/unmount` | Yes | Unmount remote storage |
| 39 | GET | `/api/version` | No | Get product version |

---

## Quick Start Guide

```python
import requests

BASE = "http://BRYCK_HOST/api"

# 1. Authenticate
auth = requests.post(f"{BASE}/auth", json={"username": "admin", "password": "YourP@ss1"})
token = auth.json()["result"]["access_token"]
headers = {"Authorization": f"JWT {token}"}

# 2. Check version
ver = requests.get(f"{BASE}/version")
print(f"Bryck version: {ver.json()['result']['version']}")

# 3. Get system status
info = requests.get(f"{BASE}/config/info", headers=headers)
print(info.json()["result"])

# 4. List hardware
brycks = requests.get(f"{BASE}/hardware/brycks", headers=headers)
cards = requests.get(f"{BASE}/hardware/logical_cards", headers=headers)
trays = requests.get(f"{BASE}/hardware/trays", headers=headers)

# 5. Start a data transfer
requests.post(f"{BASE}/tasks/transfer", headers=headers, json={
    "logical_card": "le0",
    "src": "/data/files/",
    "dst": "/bryck/backup/",
    "generate_crc": True
})

# 6. Monitor progress
tasks = requests.get(f"{BASE}/tasks/list", headers=headers, params={"task_type": "TRANSFER"})
for t in tasks.json()["result"]:
    print(f"  {t['task_id']}: {t['state']} — {t.get('percent_completed', '?')}%")

# 7. Refresh token before it expires
refresh = requests.post(f"{BASE}/auth/refresh", headers=headers)
token = refresh.json()["result"]["access_token"]
```

---

*Generated from codebase analysis — Bryck API (c) 2018 Tsecond — MIT License*

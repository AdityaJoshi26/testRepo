# Bryck API Documentation (Auto-generated from bryckapi source)

This document is generated from code analysis of the bryckapi folder only.

- API style: Flask + Blueprints
- Auth: JWT (flask-jwt-extended)
- Response envelope: `success`, `error`, `result`
- Base URL (default): `http://localhost:5000`

## OpenAPI 3.1 Specification

```yaml
openapi: 3.1.0
info:
  title: Bryck API
  version: 1.0.0
  description: |
    OpenAPI specification inferred from Flask routes in bryckapi/api.
    Most endpoints are authenticated via JWT.
servers:
  - url: http://localhost:5000
    description: Local default
security:
  - JWTAuth: []
paths:
  /api/auth:
    post:
      tags: [Authentication]
      summary: Obtain access token
      description: Authenticates a user and returns an access token and expiration epoch.
      security: []
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/AuthRequest'
            examples:
              default:
                value: { username: admin, password: correct_password }
      responses:
        '200':
          description: Token issued
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AuthTokenResponseRaw'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'
        '401':
          description: Invalid credentials
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AuthErrorRaw'

  /api/auth/refresh:
    post:
      tags: [Authentication]
      summary: Refresh access token
      description: Returns a newly issued access token if JWT claims validation succeeds.
      responses:
        '200':
          description: Token refreshed
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AuthTokenResponseRaw'
        '401':
          description: Invalid token
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/AuthErrorRaw'

  /api/auth/change_password:
    post:
      tags: [Authentication]
      summary: Change password
      description: Changes password for the authenticated admin user.
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ChangePasswordRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeMessage'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'
        '401':
          $ref: '#/components/responses/UnauthorizedEnvelope'

  /api/version:
    get:
      tags: [Version]
      summary: Get product version
      security: []
      responses:
        '200':
          description: Version response
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeVersion'

  /api/config/getlogs:
    get:
      tags: [Config]
      summary: Get system logs
      parameters:
        - in: query
          name: cursor
          required: false
          schema:
            type: string
          description: Log cursor or period marker (for example Today, This week, Last 30 days).
      responses:
        '200':
          description: Log list
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeLogList'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/aws_connect:
    get:
      tags: [Config]
      summary: Validate AWS CLI connection
      responses:
        '200':
          description: Configured
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeString'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/info:
    get:
      tags: [Config]
      summary: Get merged system configuration
      responses:
        '200':
          description: Merged configuration and runtime info
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeConfigInfo'

  /api/config/upload:
    post:
      tags: [Config]
      summary: Upload package/key file
      description: Supports upload workflow; for upgrades expects type=upgrade and package naming constraints.
      requestBody:
        required: true
        content:
          multipart/form-data:
            schema:
              type: object
              required: [type, file]
              properties:
                type:
                  type: string
                  enum: [upgrade]
                file:
                  type: string
                  format: binary
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/update:
    post:
      tags: [Config]
      summary: Configure store
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ConfigUpdateRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/reset_store:
    post:
      tags: [Config]
      summary: Reinitialize store
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
                  items: { type: string }
                reinit_type:
                  type: string
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/armageddon:
    post:
      tags: [Config]
      summary: Submit armageddon job
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'

  /api/config/shutdown:
    post:
      tags: [Config]
      summary: Submit shutdown job
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'

  /api/config/eject:
    post:
      tags: [Config]
      summary: Eject devices
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
                  items: { type: string }
                no_fs_check:
                  type: boolean
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'

  /api/config/bryck_info:
    get:
      tags: [Config]
      summary: Get bryck info
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeAny'

  /api/config/tray_info:
    get:
      tags: [Config]
      summary: Get tray info
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeAny'

  /api/config/server_info:
    get:
      tags: [Config]
      summary: Get server info
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeAny'

  /api/config/mount:
    post:
      tags: [Config]
      summary: Mount stores
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ConfigMountRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/upgrade:
    post:
      tags: [Config]
      summary: Trigger upgrade job
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
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'

  /api/config/marklog:
    post:
      tags: [Config]
      summary: Mark logs as read
      requestBody:
        required: false
        content:
          application/json:
            schema:
              type: object
              properties:
                id: { type: integer }
                all: { type: boolean }
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/alert_user:
    post:
      tags: [Config]
      summary: Add alert recipient
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/AlertUserRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/alert_user_update:
    post:
      tags: [Config]
      summary: Update alert recipient
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/AlertUserRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/alert_user_delete:
    post:
      tags: [Config]
      summary: Delete alert recipient
      requestBody:
        required: true
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
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/config/alert_user_list:
    get:
      tags: [Config]
      summary: List alert recipients
      responses:
        '200':
          description: Alert recipients
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeAlertUserList'

  /api/config/scan:
    post:
      tags: [Config]
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
                  items: { type: string }
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'

  /api/config/remove:
    post:
      tags: [Config]
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
                  items: { type: string }
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'

  /api/download:
    get:
      tags: [Download]
      summary: Download artifact
      parameters:
        - in: query
          name: name
          required: true
          schema:
            type: string
            enum: [bryckcp_client, user_guide, bryck_report]
        - in: query
          name: type
          required: false
          schema:
            type: string
          description: Optional file extension filter.
      responses:
        '200':
          description: Binary file response
          content:
            application/octet-stream:
              schema:
                type: string
                format: binary
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'
        '404':
          description: File not found
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorEnvelope'

  /api/external_storage/mount:
    post:
      tags: [External Storage]
      summary: Mount remote storage
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ExternalMountRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/external_storage/unmount:
    post:
      tags: [External Storage]
      summary: Unmount remote storage
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/ExternalUnmountRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/hardware/brycks:
    get:
      tags: [Hardware]
      summary: List brycks
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeBrycks'

  /api/hardware/logical_cards:
    get:
      tags: [Hardware]
      summary: List logical cards
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeLogicalCards'

  /api/hardware/trays:
    get:
      tags: [Hardware]
      summary: List trays
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeTrays'

  /api/network/info:
    get:
      tags: [Network]
      summary: Get network info
      parameters:
        - in: query
          name: uuids
          required: false
          schema: { type: string }
          description: UUID filter string (implementation treats this as string membership).
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeAny'

  /api/network/configure:
    post:
      tags: [Network]
      summary: Configure network
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/NetworkConfigureRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/network/configure_ntp:
    post:
      tags: [Network]
      summary: Configure NTP
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
                  items: { type: string }
                ntp_server:
                  type: string
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/tasks/list:
    get:
      tags: [Tasks]
      summary: List tracked tasks
      parameters:
        - in: query
          name: task_type
          required: false
          schema:
            type: string
            enum: [TRANSFER, VERIFICATION, CAPTURE_BRYCK_STATE]
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/SuccessEnvelopeTaskList'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/tasks/transfer:
    post:
      tags: [Tasks]
      summary: Start transfer task
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/TaskTransferRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/tasks/verify:
    post:
      tags: [Tasks]
      summary: Start verification task
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/TaskVerifyRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/tasks/dismiss:
    post:
      tags: [Tasks]
      summary: Dismiss tasks
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/TaskDismissRequest'
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '400':
          $ref: '#/components/responses/BadRequestEnvelope'

  /api/tasks/capture_bryck_state:
    post:
      tags: [Tasks]
      summary: Capture bryck state bundle
      responses:
        '200':
          $ref: '#/components/responses/SuccessEnvelopeEmpty'
        '409':
          description: Conflicting active capture task
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorEnvelope'

components:
  securitySchemes:
    JWTAuth:
      type: apiKey
      in: header
      name: Authorization
      description: Use value format `JWT <access_token>`.

  responses:
    SuccessEnvelopeEmpty:
      description: Empty successful envelope
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/SuccessEnvelopeEmpty'
    SuccessEnvelopeAny:
      description: Successful envelope with dynamic result object
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/SuccessEnvelopeAny'
    SuccessEnvelopeMessage:
      description: Success message envelope
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/SuccessEnvelopeMessage'
    BadRequestEnvelope:
      description: Bad request envelope
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/ErrorEnvelope'
    UnauthorizedEnvelope:
      description: Unauthorized envelope
      content:
        application/json:
          schema:
            $ref: '#/components/schemas/ErrorEnvelope'

  schemas:
    SuccessEnvelopeEmpty:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result: { type: object, additionalProperties: true }
      required: [success, error, result]

    SuccessEnvelopeAny:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          oneOf:
            - type: object
              additionalProperties: true
            - type: array
              items: {}
            - type: string
      required: [success, error, result]

    SuccessEnvelopeMessage:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: object
          properties:
            message: { type: string }
          required: [message]
      required: [success, error, result]

    SuccessEnvelopeVersion:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: object
          properties:
            version: { type: string }
          required: [version]
      required: [success, error, result]

    ErrorEnvelope:
      type: object
      properties:
        success: { type: boolean, const: false }
        error:
          type: object
          additionalProperties: true
          properties:
            message: { type: string }
        result: { type: object, additionalProperties: true }
      required: [success, error, result]

    AuthRequest:
      type: object
      required: [username, password]
      properties:
        username: { type: string }
        password: { type: string }

    AuthTokenResponseRaw:
      type: object
      properties:
        access_token: { type: string }
        expires: { type: integer, description: Unix epoch seconds }
      required: [access_token, expires]

    AuthErrorRaw:
      type: object
      properties:
        error: { type: string }
      required: [error]

    ChangePasswordRequest:
      type: object
      required: [username, old_password, new_password]
      properties:
        username:
          type: string
          enum: [admin]
        old_password: { type: string }
        new_password:
          type: string
          description: Must be 8+ chars, include upper/lower/digit/symbol.

    ConfigUpdateRequest:
      type: object
      required: [store_type, uuids]
      properties:
        store_type:
          type: string
          enum: [STORE, FILE_STORE, BLOCK_STORE]
        uuids:
          type: array
          items: { type: string }
        raid_level:
          type: integer
          enum: [0, 5, 6, 7]
        encryption_check: { type: boolean }
        encryption_option: { type: string, enum: [AWS_KMS] }
        description: { type: string }
        mount_point: { type: string }
        export_options: { type: string }
        acl: { type: string, maxLength: 100 }
        iqn: { type: string }
        suffix: { type: string }
        IoSize: { type: string, default: '2048' }
        DataSync: { type: string, default: application sync }
        dedup: { type: boolean }
        compress: { type: boolean }
        mountonreboot: { type: boolean }

    ConfigMountRequest:
      type: object
      required: [uuids]
      properties:
        uuids:
          type: array
          items: { type: string }
        mount_point: { type: string }
        encryption_check: { type: boolean }
        encryption_option: { type: string, enum: [AWS_KMS] }
        force_mount: { type: boolean }
        mountonreboot: { type: boolean }
        IoSize: { type: string }
        DataSync: { type: string }

    AlertUserRequest:
      type: object
      required: [mailid, alert_type]
      properties:
        user: { type: string }
        mailid: { type: string, format: email }
        alert_type:
          type: string
          description: Comma-separated values from Alert,Critical,Error,Warning,Notice,Info.

    AlertUserRecord:
      type: object
      properties:
        username: { type: string }
        mailid: { type: string }
        alerts: { type: string }
      required: [username, mailid, alerts]

    SuccessEnvelopeAlertUserList:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: array
          items:
            $ref: '#/components/schemas/AlertUserRecord'
      required: [success, error, result]

    ExternalMountRequest:
      type: object
      required: [uuids, mount_point, remote_address, export_path]
      properties:
        uuids:
          type: array
          items: { type: string }
        mount_point:
          type: string
          pattern: '^/.*'
        remote_address: { type: string }
        export_path:
          type: string
          pattern: '^/.*'

    ExternalUnmountRequest:
      type: object
      required: [uuids, mount_point]
      properties:
        uuids:
          type: array
          items: { type: string }
        mount_point:
          type: string
          pattern: '^/.*'

    NetworkInfo:
      type: object
      properties:
        dhcp: { type: boolean }
        ip: { type: string }
        netmask: { type: string }
        gateway: { type: string }
        nameservers:
          type: array
          items: { type: string }

    NetworkConfigureRequest:
      type: object
      required: [uuids]
      properties:
        uuids:
          type: array
          items: { type: string }
        interface_name: { type: string }
        dhcp: { type: boolean }
        ip: { type: string }
        netmask: { type: string }
        gateway: { type: string }
        nameservers:
          type: array
          items: { type: string }
        ntp_server: { type: string }
        mtu: { type: integer }

    BryckRecord:
      type: object
      properties:
        id: { type: string }
        name: { type: string }
        tray_id: { type: string }
        status:
          oneOf: [{ type: integer }, { type: string }]
        logical_card_ids:
          type: array
          items: { type: string }
      required: [id, name, tray_id, status, logical_card_ids]

    SuccessEnvelopeBrycks:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: object
          properties:
            brycks:
              type: array
              items:
                $ref: '#/components/schemas/BryckRecord'
      required: [success, error, result]

    LogicalCardStatus:
      type: object
      properties:
        store: { type: integer, enum: [0, 1] }
        network: { type: integer, enum: [0, 1] }

    DriveRecord:
      type: object
      properties:
        serial: { type: string }
        name: { type: string }
        model: { type: string }
        subsystems: { type: string }
        size: { type: string }
      additionalProperties: true

    LogicalCardRecord:
      type: object
      properties:
        id: { type: string }
        name: { type: string }
        status: { $ref: '#/components/schemas/LogicalCardStatus' }
        drives:
          type: array
          items:
            $ref: '#/components/schemas/DriveRecord'
      required: [id, name, status, drives]

    SuccessEnvelopeLogicalCards:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: object
          properties:
            logical_cards:
              type: array
              items:
                $ref: '#/components/schemas/LogicalCardRecord'
      required: [success, error, result]

    TrayRecord:
      type: object
      properties:
        id: { type: string }
        name: { type: string }
        status: { type: integer }
        connections: { type: integer }
        bryck_ids:
          type: array
          items: { type: string }
      required: [id, name, status, connections, bryck_ids]

    SuccessEnvelopeTrays:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: object
          properties:
            trays:
              type: array
              items:
                $ref: '#/components/schemas/TrayRecord'
      required: [success, error, result]

    TaskRecord:
      type: object
      properties:
        task_type: { type: string }
        task_id: { type: string }
        store: { type: string }
        state: { type: string, enum: [ACTIVE, COMPLETED, FAILED, STALE] }
        started_at: { type: integer }
        last_updated: { type: integer }
        src: { type: string }
        dst: { type: string }
        path: { type: string }
        copied_bytes: { type: integer }
        verified_bytes: { type: integer }
        total_bytes: { type: integer }
        percent_completed: { type: integer }
        throughput: { type: integer }
        errors:
          type: array
          items:
            type: object
            properties:
              timestamp: { type: integer }
              error_level: { type: string }
              error_msg: { type: string }
      additionalProperties: true

    SuccessEnvelopeTaskList:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: array
          items:
            $ref: '#/components/schemas/TaskRecord'
      required: [success, error, result]

    TaskTransferRequest:
      type: object
      required: [logical_card, src, dst]
      properties:
        logical_card: { type: string }
        src: { type: string }
        dst: { type: string }
        generate_crc: { type: boolean, default: false }

    TaskVerifyRequest:
      type: object
      required: [logical_card, path]
      properties:
        logical_card: { type: string }
        path: { type: string }

    TaskDismissRequest:
      type: object
      required: [logical_card]
      properties:
        logical_card: { type: string, description: Use '*' for all (state-based dismiss only). }
        task_id: { type: string }
        task_type: { type: string, enum: [TRANSFER, VERIFICATION, CAPTURE_BRYCK_STATE] }
        states:
          type: array
          items:
            type: string
            enum: [STALE, FAILED, COMPLETED]

    LogRecord:
      type: object
      properties:
        cursor: { type: string }
        timestamp:
          oneOf: [{ type: integer }, { type: string }]
        message: { type: string }
        priority: { type: string }
      additionalProperties: true

    SuccessEnvelopeLogList:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: array
          items:
            $ref: '#/components/schemas/LogRecord'
      required: [success, error, result]

    SuccessEnvelopeString:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result: { type: string }
      required: [success, error, result]

    SuccessEnvelopeConfigInfo:
      type: object
      properties:
        success: { type: boolean, const: true }
        error: { type: object, additionalProperties: true }
        result:
          type: object
          properties:
            bryck_info:
              oneOf:
                - type: object
                  additionalProperties: true
                - type: string
            server_info:
              oneOf:
                - type: object
                  additionalProperties: true
                - type: string
            tray_info:
              oneOf:
                - type: object
                  additionalProperties: true
                - type: string
            logical_cards:
              type: object
              additionalProperties: true
            properties:
              type: object
              additionalProperties: true
            upgrade: { type: boolean }
            upgrade_info:
              type: object
              additionalProperties: true
            build_info:
              type: object
              additionalProperties: true
          additionalProperties: true
      required: [success, error, result]
```

## Authentication

- Protected endpoints use `@jwt_required`.
- Send token as header: `Authorization: JWT <access_token>`.
- Token can also be cookie-based (`access_token_cookie`).
- Token claims include client IP, and mismatch causes `401 Invalid token`.

### Auth flow
1. Call `POST /api/auth` with username/password.
2. Receive `access_token` and `expires`.
3. Use token for other endpoints.
4. Refresh via `POST /api/auth/refresh`.

## Error Model

Primary envelope for most API handlers:

```json
{
  "success": false,
  "error": {
    "message": "..."
  },
  "result": {}
}
```

Auth endpoints may return raw:

```json
{ "error": "Invalid credentials" }
```

Common statuses:
- `400` malformed request, missing required fields, domain validation failure
- `401` unauthenticated or invalid token
- `404` download target not found
- `405` method not allowed
- `409` task conflict (capture already running)
- `500` unexpected internal exception

## Data Models Inferred

### User model
- `username: string`
- `id: string`
- `password_hash: string`
- Password complexity checks enforce: length >= 8, upper/lower, digit, symbol.

### Configuration model
- Dynamic store-backed object (`BryckStore` or `TrayStore`) with keys:
- `uuid`, `logical_cards`, `properties`
- `logical_cards[*].properties.network_info`, drive details, current conditions.

### Task model
- `task_id`, `task_type`, `state`, `store`, timestamps
- transfer fields: `src`, `dst`, `copied_bytes`, `total_bytes`, `percent_completed`
- verification fields: `path`, `verified_bytes`
- optional errors list.

## Pagination, Filtering, Sorting, Rate Limiting, Webhooks, Background Tasks

- Pagination: no classical page/limit style detected.
- Filtering: `task_type` on `/api/tasks/list`, optional UUID filter string on `/api/network/info`, cursor/period on `/api/config/getlogs`.
- Sorting: not exposed as explicit query parameter.
- Rate limiting: no explicit middleware/decorator detected.
- Webhooks: none detected.
- Background tasks: present, job-based queueing via `AgentClient` and tracked through `/api/tasks/list`.

## Endpoint Reference (Human-readable)

### Authentication

#### POST /api/auth
- What it does: logs in and issues JWT token.
- When to use: first step before calling protected APIs.
- Request fields:
  - `username` (required): account name.
  - `password` (required): account password.
- Response fields:
  - `access_token`: JWT string.
  - `expires`: unix timestamp when token expires.

Curl:
```bash
curl -X POST http://localhost:5000/api/auth \
  -H "Content-Type: application/json" \
  -d '{"username":"admin","password":"correct_password"}'
```

Python:
```python
import requests
r = requests.post("http://localhost:5000/api/auth", json={"username": "admin", "password": "correct_password"})
print(r.status_code, r.json())
```

#### POST /api/auth/refresh
- What it does: issues a fresh token for a valid authenticated caller.
- When to use: renew token before expiry.

Curl:
```bash
curl -X POST http://localhost:5000/api/auth/refresh \
  -H "Authorization: JWT <access_token>"
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
r = requests.post("http://localhost:5000/api/auth/refresh", headers=headers)
print(r.status_code, r.json())
```

#### POST /api/auth/change_password
- What it does: changes admin password after verifying old password and complexity of new password.
- When to use: credential rotation.
- Request fields:
  - `username` (required): must be `admin`.
  - `old_password` (required)
  - `new_password` (required)

Curl:
```bash
curl -X POST http://localhost:5000/api/auth/change_password \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{"username":"admin","old_password":"old123!A","new_password":"new123!B"}'
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
payload = {"username": "admin", "old_password": "old123!A", "new_password": "new123!B"}
r = requests.post("http://localhost:5000/api/auth/change_password", headers=headers, json=payload)
print(r.status_code, r.json())
```

### Version

#### GET /api/version
- What it does: returns product version from manifest.
- When to use: health/version checks during deployment.

Curl:
```bash
curl http://localhost:5000/api/version
```

Python:
```python
import requests
print(requests.get("http://localhost:5000/api/version").json())
```

### Config

#### GET /api/config/info
- What it does: returns merged device, logical card, server and upgrade metadata.
- When to use: initial dashboard load and status summary.
- Relationships: complements `/api/config/bryck_info`, `/api/config/tray_info`, `/api/config/server_info`.

#### GET /api/config/getlogs
- What it does: returns system logs.
- When to use: audit/operations UI.
- Query fields:
  - `cursor` (optional): period or cursor token.

#### GET /api/config/aws_connect
- What it does: validates AWS CLI configuration presence.
- When to use: before selecting AWS KMS encryption options.

#### POST /api/config/upload
- What it does: uploads upgrade package using multipart form.
- When to use: before calling `/api/config/upgrade`.
- Request form fields:
  - `type=upgrade`
  - `file=<binary>`

#### POST /api/config/update
- What it does: submits store configuration job.
- When to use: create or change store mode and options.
- Key fields:
  - `store_type`: STORE/FILE_STORE/BLOCK_STORE
  - `uuids`: target logical cards
  - optional RAID, encryption, iSCSI, and mount options.

#### POST /api/config/reset_store
- What it does: reinitializes selected stores.
- Request:
  - `uuids` required
  - `reinit_type` optional enum value

#### POST /api/config/armageddon
- What it does: submits full reset/destructive maintenance job.

#### POST /api/config/shutdown
- What it does: submits bryck shutdown job.

#### POST /api/config/eject
- What it does: ejects selected UUIDs.
- Request:
  - `uuids` required
  - `no_fs_check` optional

#### GET /api/config/bryck_info
#### GET /api/config/tray_info
#### GET /api/config/server_info
- What they do: return individual info payloads from corresponding jobs.
- When to use: retrieve specific subsets without full `/info` payload.

#### POST /api/config/mount
- What it does: mounts selected stores.
- Request:
  - `uuids` required
  - optional mount/encryption/IO settings.

#### POST /api/config/upgrade
- What it does: triggers upgrade workflow for uploaded build.
- Request:
  - `build_filename` required.

#### POST /api/config/marklog
- What it does: marks one or all DB logs as read.
- Request:
  - `id` for single row
  - `all=true` for all rows

#### POST /api/config/alert_user
#### POST /api/config/alert_user_update
#### POST /api/config/alert_user_delete
#### GET /api/config/alert_user_list
- What they do: CRUD-like operations for alert recipient registry.
- Fields:
  - `mailid`: email
  - `alert_type`: comma-separated alert labels
  - `user`: optional username

#### POST /api/config/scan
#### POST /api/config/remove
- What they do: submit scan/remove jobs for selected UUIDs.

Shared Config Curl example:
```bash
curl -X POST http://localhost:5000/api/config/mount \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{"uuids":["<lc_uuid>"],"mount_point":"/bryck"}'
```

Shared Config Python example:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
payload = {"uuids": ["<lc_uuid>"], "mount_point": "/bryck"}
r = requests.post("http://localhost:5000/api/config/mount", headers=headers, json=payload)
print(r.status_code, r.json())
```

### Download

#### GET /api/download
- What it does: returns binary artifact from downloads directory.
- Query fields:
  - `name` required: `bryckcp_client`, `user_guide`, or `bryck_report`
  - `type` optional file extension filter

Curl:
```bash
curl -L "http://localhost:5000/api/download?name=user_guide" \
  -H "Authorization: JWT <access_token>" \
  -o user_guide.pdf
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
r = requests.get("http://localhost:5000/api/download", params={"name": "user_guide"}, headers=headers)
open("download.bin", "wb").write(r.content)
```

### External Storage

#### POST /api/external_storage/mount
- What it does: mounts remote export path onto selected UUIDs.
- Request fields:
  - `uuids` required
  - `mount_point` required, must start with `/`
  - `remote_address` required
  - `export_path` required, must start with `/`

#### POST /api/external_storage/unmount
- What it does: unmounts mount point from selected UUIDs.
- Request fields:
  - `uuids` required
  - `mount_point` required

Curl:
```bash
curl -X POST http://localhost:5000/api/external_storage/mount \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{"uuids":["<lc_uuid>"],"mount_point":"/mnt/nfs","remote_address":"10.0.0.5","export_path":"/exports/data"}'
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
payload = {"uuids": ["<lc_uuid>"], "mount_point": "/mnt/nfs", "remote_address": "10.0.0.5", "export_path": "/exports/data"}
r = requests.post("http://localhost:5000/api/external_storage/mount", headers=headers, json=payload)
print(r.status_code, r.json())
```

### Hardware

#### GET /api/hardware/brycks
- What it does: returns bryck inventory summary.

#### GET /api/hardware/logical_cards
- What it does: returns logical cards with status and drives.

#### GET /api/hardware/trays
- What it does: returns tray information.

Curl:
```bash
curl -H "Authorization: JWT <access_token>" http://localhost:5000/api/hardware/logical_cards
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
print(requests.get("http://localhost:5000/api/hardware/logical_cards", headers=headers).json())
```

### Network

#### GET /api/network/info
- What it does: returns network settings keyed by UUID.
- Query field:
  - `uuids` optional filter string.

#### POST /api/network/configure
- What it does: submits network configuration job.
- Request fields:
  - `uuids` required
  - optional: `interface_name`, `dhcp`, `ip`, `netmask`, `gateway`, `nameservers`, `ntp_server`, `mtu`

#### POST /api/network/configure_ntp
- What it does: submits NTP update job.
- Request fields:
  - `uuids` required
  - `ntp_server` required

Curl:
```bash
curl -X POST http://localhost:5000/api/network/configure \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{"uuids":["<lc_uuid>"],"dhcp":false,"ip":"192.168.1.10","netmask":"255.255.255.0","gateway":"192.168.1.1","nameservers":["8.8.8.8"]}'
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
payload = {"uuids": ["<lc_uuid>"], "dhcp": False, "ip": "192.168.1.10", "netmask": "255.255.255.0", "gateway": "192.168.1.1", "nameservers": ["8.8.8.8"]}
r = requests.post("http://localhost:5000/api/network/configure", headers=headers, json=payload)
print(r.status_code, r.json())
```

### Tasks

#### GET /api/tasks/list
- What it does: lists in-memory tracked tasks.
- Query:
  - `task_type` optional enum filter.
- Relationships:
  - Use after `/api/tasks/transfer`, `/api/tasks/verify`, and `/api/tasks/capture_bryck_state`.

#### POST /api/tasks/transfer
- What it does: starts transfer task.
- Request fields:
  - `logical_card` required
  - `src` required
  - `dst` required
  - `generate_crc` optional
- Rule:
  - one of `src`/`dst` must start with `/bryck`.

#### POST /api/tasks/verify
- What it does: starts data verification task.
- Request fields:
  - `logical_card` required
  - `path` required

#### POST /api/tasks/dismiss
- What it does: removes task records by id or state filter.
- Request fields:
  - `logical_card` required
  - `task_id` optional
  - `task_type` optional enum
  - `states` optional enum list (STALE/FAILED/COMPLETED)

#### POST /api/tasks/capture_bryck_state
- What it does: starts package capture of bryck state into downloads.
- Conflict behavior:
  - returns 409 if another capture is active.

Curl:
```bash
curl -X POST http://localhost:5000/api/tasks/transfer \
  -H "Authorization: JWT <access_token>" \
  -H "Content-Type: application/json" \
  -d '{"logical_card":"<lc_uuid>","src":"/bryck/source","dst":"/tmp/dest","generate_crc":false}'
```

Python:
```python
import requests
headers = {"Authorization": "JWT <access_token>"}
payload = {"logical_card": "<lc_uuid>", "src": "/bryck/source", "dst": "/tmp/dest", "generate_crc": False}
r = requests.post("http://localhost:5000/api/tasks/transfer", headers=headers, json=payload)
print(r.status_code, r.json())

r2 = requests.get("http://localhost:5000/api/tasks/list", headers=headers)
print(r2.status_code, r2.json())
```

## Field Meaning Guide

- `uuids`: target logical card identifiers for job dispatch.
- `store_type`: desired storage mode (`STORE`, `FILE_STORE`, `BLOCK_STORE`).
- `mount_point`: local filesystem path where store/export should be mounted.
- `remote_address`: remote storage host/address.
- `export_path`: remote exported path.
- `task_type`: task class filter (`TRANSFER`, `VERIFICATION`, `CAPTURE_BRYCK_STATE`).
- `states`: dismissal/status values for task list manipulation.
- `cursor`: log continuation pointer or period selector.

## Notes and Caveats

- The API is mostly job-submission oriented: many endpoints return empty success envelopes while work continues asynchronously.
- `/api/tasks/list` is the primary observation endpoint for transfer/verification/capture progress.
- `/api/auth` and `/api/auth/refresh` return a raw JSON shape, while most other endpoints use the response envelope.
- No explicit SQLAlchemy table definitions were found in bryckapi models; models are mainly runtime configuration abstractions.

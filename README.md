# Repository Test Function and Suite Analysis

Generated: 2026-03-11 13:34:46

## Summary
- Total test function definitions (def test_*): 915
- Total suite definitions (list vars containing test_*): 51
- Unique test names defined: 759
- Unique test names referenced in suites: 711
- Missing test names (referenced in suite but not defined): 5
- Unused test definitions (defined but never referenced in suite lists): 56

## 1. All Test Functions

| Function | File | Class | Line | Description |
|---|---|---|---:|---|
| test_cmds | blockstore_data_tests.py | - | 205 | Defined test function; not referenced by any detected suite list. |
| test_bryck_mount | bryckutil_test.py | Tsutil | 131 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_invalid_key | bryckutil_test.py | Tsutil | 144 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_non_exist_keyfile | bryckutil_test.py | Tsutil | 156 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_no_mnt_directory | bryckutil_test.py | Tsutil | 168 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_write_files | bryckutil_test.py | Tsutil | 180 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_files_checksum | bryckutil_test.py | Tsutil | 194 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_stress | bryckutil_test.py | Tsutil | 235 | Defined test function; not referenced by any detected suite list. |
| test_bryck_setkey_key_change | bryckutil_test.py | Tsutil | 264 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_oldkey_invalid | bryckutil_test.py | Tsutil | 284 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_newkey_invalid | bryckutil_test.py | Tsutil | 299 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_no_keyfile | bryckutil_test.py | Tsutil | 312 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_stress | bryckutil_test.py | Tsutil | 325 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_non_formatted_bryck | bryckutil_test.py | Tsutil | 339 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_non_formatted_bryck_with_nvme | bryckutil_test.py | Tsutil | 349 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_formatted_bryck | bryckutil_test.py | Tsutil | 360 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_mounted_bryck | bryckutil_test.py | Tsutil | 371 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_not_inserted | bryckutil_test.py | Tsutil | 383 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_not_inserted_with_nvme | bryckutil_test.py | Tsutil | 392 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_stress | bryckutil_test.py | Tsutil | 402 | Defined test function; not referenced by any detected suite list. |
| test_bryck_format_inserted_bryck | bryckutil_test.py | Tsutil | 423 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_already_formatted | bryckutil_test.py | Tsutil | 432 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_already_mounted | bryckutil_test.py | Tsutil | 442 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_not_found | bryckutil_test.py | Tsutil | 453 | Defined test function; referenced by at least one suite list. |
| test_format_invalid_key | bryckutil_test.py | Tsutil | 463 | Defined test function; referenced by at least one suite list. |
| test_format_stress | bryckutil_test.py | Tsutil | 472 | Defined test function; not referenced by any detected suite list. |
| test_bryck_eject | bryckutil_test.py | Tsutil | 489 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_already_ejected | bryckutil_test.py | Tsutil | 500 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_directory_use | bryckutil_test.py | Tsutil | 515 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_data_consistency | bryckutil_test.py | Tsutil | 534 | Defined test function; referenced by at least one suite list. |
| test_bryck_erase_mounted | bryckutil_test.py | Tsutil | 565 | Defined test function; referenced by at least one suite list. |
| test_bryck_erase_unmounted | bryckutil_test.py | Tsutil | 576 | Defined test function; referenced by at least one suite list. |
| test_break_mount_after_erase | bryckutil_test.py | Tsutil | 587 | Defined test function; referenced by at least one suite list. |
| test_consistency_check_for_cloud | cloud_store.py | CloudStore | 1604 | Defined test function; not referenced by any detected suite list. |
| test_consistency_check_for_bryck_fs | cloud_store.py | CloudStore | 1736 | Defined test function; not referenced by any detected suite list. |
| test_configure | config_store.py | ConfigStore | 141 | Defined test function; not referenced by any detected suite list. |
| test_configure_luns_format | config_store.py | ConfigStore | 191 | Defined test function; not referenced by any detected suite list. |
| test_configure_luns_mount | config_store.py | ConfigStore | 215 | Defined test function; not referenced by any detected suite list. |
| test_ui_configure | config_store.py | ConfigStore | 271 | Defined test function; not referenced by any detected suite list. |
| test_bryck_resiliency | config_store.py | ConfigStore | 367 | Defined test function; not referenced by any detected suite list. |
| test_encryption_corruption | config_store.py | ConfigStore | 406 | Defined test function; not referenced by any detected suite list. |
| test_partition_corruption | config_store.py | ConfigStore | 427 | Defined test function; not referenced by any detected suite list. |
| test_drive_failure | config_store.py | ConfigStore | 503 | Defined test function; not referenced by any detected suite list. |
| test_drive_failure_negative_case | config_store.py | ConfigStore | 561 | Defined test function; not referenced by any detected suite list. |
| test_data_protection_io_failure | config_store.py | ConfigStore | 628 | Defined test function; referenced by at least one suite list. |
| test_data_protection_checksum_failure | config_store.py | ConfigStore | 697 | Defined test function; referenced by at least one suite list. |
| test_download_client_package | config_store.py | ConfigStore | 794 | Defined test function; not referenced by any detected suite list. |
| test_ui_dashboard_wizard | config_store.py | ConfigStore | 1396 | Defined test function; not referenced by any detected suite list. |
| test_ui_format | config_store.py | ConfigStore | 2182 | Defined test function; not referenced by any detected suite list. |
| test_data_movement | mobility_store.py | MobilityStore | 59 | Defined test function; not referenced by any detected suite list. |
| test_data_movement_in_cloud | mobility_store.py | MobilityStore | 122 | Defined test function; not referenced by any detected suite list. |
| test_multi_hop_data_movement | mobility_store.py | MobilityStore | 288 | Defined test function; not referenced by any detected suite list. |
| test_bryck_check | test_agylstor.py | AgylstorTest | 192 | Defined test function; referenced by at least one suite list. |
| test_filestore_configure | test_agylstor.py | AgylstorTest | 208 | Defined test function; referenced by at least one suite list. |
| test_filestore_nfs_mount | test_agylstor.py | AgylstorTest | 211 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_nfs_local_push_n_stream | test_agylstor.py | AgylstorTest | 214 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_nfs_local_pull_n_stream | test_agylstor.py | AgylstorTest | 217 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_nfs_local_copy_with_illegal_patterns | test_agylstor.py | AgylstorTest | 220 | Defined test function; referenced by at least one suite list. |
| test_filestore_nfs_umount | test_agylstor.py | AgylstorTest | 223 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_nfs_remote_push_n_stream | test_agylstor.py | AgylstorTest | 228 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_nfs_remote_pull_n_stream | test_agylstor.py | AgylstorTest | 231 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_rdma_nfs_remote_push_n_stream | test_agylstor.py | AgylstorTest | 234 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_rdma_nfs_remote_pull_n_stream | test_agylstor.py | AgylstorTest | 238 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_remote_pull_1_stream | test_agylstor.py | AgylstorTest | 243 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_remote_push_n_stream | test_agylstor.py | AgylstorTest | 246 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_remote_pull_n_stream | test_agylstor.py | AgylstorTest | 249 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_rdma_smb_remote_push_n_stream | test_agylstor.py | AgylstorTest | 252 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_rdma_smb_remote_pull_n_stream | test_agylstor.py | AgylstorTest | 256 | Defined test function; referenced by at least one suite list. |
| test_ftp_remote_push_n_stream | test_agylstor.py | AgylstorTest | 261 | Defined test function; referenced by at least one suite list. |
| test_ftp_remote_pull_n_stream | test_agylstor.py | AgylstorTest | 265 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_1_stream_n_rdwr | test_agylstor.py | AgylstorTest | 269 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_1_stream_n_rdwr | test_agylstor.py | AgylstorTest | 272 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_n_stream_n_rdwr | test_agylstor.py | AgylstorTest | 275 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_n_stream_n_rdwr | test_agylstor.py | AgylstorTest | 278 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_data_verify | test_agylstor.py | AgylstorTest | 282 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_pull_data_verify | test_agylstor.py | AgylstorTest | 285 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_tcp_pull_data_verify_file_missing | test_agylstor.py | AgylstorTest | 288 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_tcp_pull_data_verify_file_changed | test_agylstor.py | AgylstorTest | 291 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_tcp_pull_data_verify_dir_missing | test_agylstor.py | AgylstorTest | 294 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_tcp_push_data_verify_file_missing | test_agylstor.py | AgylstorTest | 297 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_tcp_push_data_verify_file_changed | test_agylstor.py | AgylstorTest | 300 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_tcp_push_data_verify_dir_missing | test_agylstor.py | AgylstorTest | 303 | Defined test function; not referenced by any detected suite list. |
| test_error_bryckcp_nfs_push_crash | test_agylstor.py | AgylstorTest | 307 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_pull_crash | test_agylstor.py | AgylstorTest | 310 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_push_crash_segv | test_agylstor.py | AgylstorTest | 317 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_pull_crash_segv | test_agylstor.py | AgylstorTest | 320 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_push_access_source | test_agylstor.py | AgylstorTest | 324 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_push_access_dest | test_agylstor.py | AgylstorTest | 327 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_pull_access_source | test_agylstor.py | AgylstorTest | 330 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_nfs_pull_access_dest | test_agylstor.py | AgylstorTest | 333 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_tcp_push_access_source | test_agylstor.py | AgylstorTest | 336 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_tcp_push_access_dest | test_agylstor.py | AgylstorTest | 339 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_tcp_pull_access_source | test_agylstor.py | AgylstorTest | 342 | Defined test function; referenced by at least one suite list. |
| test_error_bryckcp_tcp_pull_access_dest | test_agylstor.py | AgylstorTest | 345 | Defined test function; referenced by at least one suite list. |
| test_filestore_reinit | test_agylstor.py | AgylstorTest | 366 | Defined test function; referenced by at least one suite list. |
| test_bryck_report_start | test_agylstor.py | AgylstorTest | 372 | Defined test function; referenced by at least one suite list. |
| test_bryck_report_check | test_agylstor.py | AgylstorTest | 375 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject | test_agylstor.py | AgylstorTest | 380 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_once | test_agylstor.py | AgylstorTest | 383 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount | test_agylstor.py | AgylstorTest | 386 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_agylstor.py | AgylstorTest | 399 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_agylstor.py | AgylstorTest | 411 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_agylstor.py | AgylstorTest | 420 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_aws | test_agylstor.py | AgylstorTest | 424 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_aws | test_agylstor.py | AgylstorTest | 428 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_gcp | test_agylstor.py | AgylstorTest | 432 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_gcp | test_agylstor.py | AgylstorTest | 436 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_azure | test_agylstor.py | AgylstorTest | 441 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_azure | test_agylstor.py | AgylstorTest | 445 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_object_set_aws | test_agylstor.py | AgylstorTest | 449 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_object_set_aws | test_agylstor.py | AgylstorTest | 453 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_agylstor.py | AgylstorTest | 457 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_agylstor.py | AgylstorTest | 459 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_agylstor.py | AgylstorTest | 462 | Defined test function; referenced by at least one suite list. |
| test_create_access_key | test_agylstor.py | AgylstorTest | 466 | Defined test function; not referenced by any detected suite list. |
| test_list_access_key | test_agylstor.py | AgylstorTest | 475 | Defined test function; not referenced by any detected suite list. |
| test_delete_acess_key | test_agylstor.py | AgylstorTest | 478 | Defined test function; not referenced by any detected suite list. |
| test_create_bucket_with_access_key | test_agylstor.py | AgylstorTest | 481 | Defined test function; not referenced by any detected suite list. |
| test_delete_bucket_with_access_key | test_agylstor.py | AgylstorTest | 485 | Defined test function; not referenced by any detected suite list. |
| test_configure_luns | test_agylstor.py | AgylstorTest | 489 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_with_luns | test_agylstor.py | AgylstorTest | 492 | Defined test function; referenced by at least one suite list. |
| test_configure_luns_with_N_volumes | test_agylstor.py | AgylstorTest | 496 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_with_luns | test_agylstor.py | AgylstorTest | 500 | Defined test function; referenced by at least one suite list. |
| test_filestore_reinit_with_luns | test_agylstor.py | AgylstorTest | 503 | Defined test function; referenced by at least one suite list. |
| test_filestore_configure_no_enc_automount | test_agylstor.py | AgylstorTest | 506 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_no_enc | test_agylstor.py | AgylstorTest | 508 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_force | test_agylstor.py | AgylstorTest | 511 | Defined test function; referenced by at least one suite list. |
| test_eject_bryck_force | test_agylstor.py | AgylstorTest | 515 | Defined test function; referenced by at least one suite list. |
| test_filestore_reinit_final | test_agylstor.py | AgylstorTest | 517 | Defined test function; referenced by at least one suite list. |
| test_to_configure_five_red_camera | test_agylstor.py | AgylstorTest | 520 | Defined test function; referenced by at least one suite list. |
| test_bryckck_verify_bryck_fs | test_agylstor.py | AgylstorTest | 533 | Defined test function; referenced by at least one suite list. |
| test_build_upgrade_ui | test_agylstor.py | AgylstorTest | 539 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_aibryck.py | AiBryckTest | 105 | Defined test function; referenced by at least one suite list. |
| test_inferencing_one_specific_model | test_aibryck.py | AiBryckTest | 109 | Defined test function; referenced by at least one suite list. |
| test_inferencing_one_model_with_100TB_data | test_aibryck.py | AiBryckTest | 128 | Defined test function; referenced by at least one suite list. |
| test_inferencing_one_model_N_times_parallely | test_aibryck.py | AiBryckTest | 148 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_on_multiple_models_sequentially | test_aibryck.py | AiBryckTest | 166 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_on_Multiple_models_N_times_parallely | test_aibryck.py | AiBryckTest | 186 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_on_N_models_with_N_no_of_dataset_parallely | test_aibryck.py | AiBryckTest | 205 | Defined test function; referenced by at least one suite list. |
| test_inferencing_four__model_with_100TB_data | test_aibryck.py | AiBryckTest | 222 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_streaming_data_one_model | test_aibryck.py | AiBryckTest | 242 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_streaming_data_one_model_N_times_parallely | test_aibryck.py | AiBryckTest | 260 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_streaming_data_on_muliple_models | test_aibryck.py | AiBryckTest | 276 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_streaming_data_on_Multiple_models_N_times_parallely | test_aibryck.py | AiBryckTest | 292 | Defined test function; referenced by at least one suite list. |
| test_run_inferencing_streaming_data_on_N_models_with_N_streaming_source_parallely | test_aibryck.py | AiBryckTest | 308 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_directory | test_bcp.py | BcpTest | 89 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_file | test_bcp.py | BcpTest | 103 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_directory | test_bcp.py | BcpTest | 112 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_smb_push_file | test_bcp.py | BcpTest | 128 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_directory_with_space_in_src | test_bcp.py | BcpTest | 144 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_file_with_space_in_src | test_bcp.py | BcpTest | 157 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_directory_with_space_in_src | test_bcp.py | BcpTest | 170 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_smb_push_file_with_space_in_src | test_bcp.py | BcpTest | 185 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_directory_with_space_in_dst | test_bcp.py | BcpTest | 202 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_file_with_space_in_dst | test_bcp.py | BcpTest | 214 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_directory_with_space_in_dst | test_bcp.py | BcpTest | 223 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_smb_push_file_with_space_in_dst | test_bcp.py | BcpTest | 237 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_directory_wrong_mnt_pnt | test_bcp.py | BcpTest | 253 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_directory_wrong_mnt_pnt | test_bcp.py | BcpTest | 261 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_directory_invalid_src_path | test_bcp.py | BcpTest | 276 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_directory_invalid_src_path | test_bcp.py | BcpTest | 285 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_directory_invalid_dst_path | test_bcp.py | BcpTest | 301 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_directory_invalid_dst_path | test_bcp.py | BcpTest | 309 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_smb_push_delete_file | test_bcp.py | BcpTest | 324 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_validate_directory | test_bcp.py | BcpTest | 340 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_validate_exist_directory | test_bcp.py | BcpTest | 352 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_push_validate_src_exist_directory | test_bcp.py | BcpTest | 366 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_smb_push_validate_file | test_bcp.py | BcpTest | 381 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_push_delete_directory | test_bcp.py | BcpTest | 397 | Defined test function; not referenced by any detected suite list. |
| test_bryckcp_tcp_pull_directory | test_bcp.py | BcpTest | 430 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_file | test_bcp.py | BcpTest | 443 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_directory_with_space_in_src | test_bcp.py | BcpTest | 454 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_directory_with_space_in_dst | test_bcp.py | BcpTest | 468 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_directory_invalid_src_path | test_bcp.py | BcpTest | 481 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_directory_invalid_dst_path | test_bcp.py | BcpTest | 491 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_delete_directory | test_bcp.py | BcpTest | 504 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_bryck_stream.py | TestBryckStream | 107 | Defined test function; referenced by at least one suite list. |
| test_to_configure_one_red_camera | test_bryck_stream.py | TestBryckStream | 111 | Defined test function; referenced by at least one suite list. |
| test_to_list_out_all_red_cameras | test_bryck_stream.py | TestBryckStream | 130 | Defined test function; referenced by at least one suite list. |
| test_to_check_after_reboot_red_camera_resumes_streaming | test_bryck_stream.py | TestBryckStream | 141 | Defined test function; referenced by at least one suite list. |
| test_to_deconfigure_specific_red_camera | test_bryck_stream.py | TestBryckStream | 156 | Defined test function; referenced by at least one suite list. |
| test_to_configure_five_red_camera | test_bryck_stream.py | TestBryckStream | 172 | Defined test function; referenced by at least one suite list. |
| test_to_configure_ten_red_camera | test_bryck_stream.py | TestBryckStream | 187 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_video_kernal | test_bryck_stream.py | TestBryckStream | 203 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_video_kernal_reboot | test_bryck_stream.py | TestBryckStream | 248 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_audio_kernal | test_bryck_stream.py | TestBryckStream | 293 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_audio_kernal_reboot | test_bryck_stream.py | TestBryckStream | 333 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_video_dpdk | test_bryck_stream.py | TestBryckStream | 374 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_video_dpdk_reboot | test_bryck_stream.py | TestBryckStream | 418 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_audio_dpdk | test_bryck_stream.py | TestBryckStream | 465 | Defined test function; referenced by at least one suite list. |
| test_to_configure_st21_audio_dpdk_reboot | test_bryck_stream.py | TestBryckStream | 505 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_bryckcp.py | BryckcpTest | 100 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_2gb_files | test_bryckcp.py | BryckcpTest | 105 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_64mb_files | test_bryckcp.py | BryckcpTest | 114 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_64mb_files_multi_level | test_bryckcp.py | BryckcpTest | 123 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_2gb_files_crash_transfer | test_bryckcp.py | BryckcpTest | 132 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_64mb_files_crash_transfer | test_bryckcp.py | BryckcpTest | 142 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_64mb_files_multi_level_crash_transfer | test_bryckcp.py | BryckcpTest | 152 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_small_files_where_dest_contains_files | test_bryckcp.py | BryckcpTest | 162 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_with_some_duplicate_files_of_the_dest | test_bryckcp.py | BryckcpTest | 172 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_tcp_pull_push_transfer | test_bryckcp.py | BryckcpTest | 185 | Defined test function; referenced by at least one suite list. |
| test_bryckcp_local_transfer | test_bryckcp.py | BryckcpTest | 197 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cleanup.py | CleanUPTest | 83 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_config.py | CloudConfigure | 100 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_config.py | CloudConfigure | 105 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_config.py | CloudConfigure | 108 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_config.py | CloudConfigure | 115 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_user_aws | test_cloud_config.py | CloudConfigure | 118 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_user_azure | test_cloud_config.py | CloudConfigure | 120 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_keyid_aws | test_cloud_config.py | CloudConfigure | 122 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_keyid_azure | test_cloud_config.py | CloudConfigure | 124 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_user_keyid_aws | test_cloud_config.py | CloudConfigure | 126 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_user_keyid_azure | test_cloud_config.py | CloudConfigure | 128 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_cloudtype_aws | test_cloud_config.py | CloudConfigure | 130 | Defined test function; referenced by at least one suite list. |
| test_miss_configure_cloud_wrong_cloudtype_azure | test_cloud_config.py | CloudConfigure | 132 | Defined test function; referenced by at least one suite list. |
| test_list_out_all_cloud_configuration | test_cloud_config.py | CloudConfigure | 135 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_config.py | CloudConfigure | 137 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_config.py | CloudConfigure | 139 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_config.py | CloudConfigure | 141 | Defined test function; referenced by at least one suite list. |
| test_modify_cloud_configuration | test_cloud_config.py | CloudConfigure | 143 | Defined test function; referenced by at least one suite list. |
| test_to_store_cloud_credentails_securely | test_cloud_config.py | CloudConfigure | 146 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_crash.py | CloudCrash | 154 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_crash.py | CloudCrash | 159 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_crash.py | CloudCrash | 172 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_crash.py | CloudCrash | 180 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_crash.py | CloudCrash | 186 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_crash.py | CloudCrash | 200 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_crash.py | CloudCrash | 203 | Defined test function; referenced by at least one suite list. |
| test_configure_the_bryck | test_cloud_crash.py | CloudCrash | 271 | Defined test function; referenced by at least one suite list. |
| test_eject_the_bryck | test_cloud_crash.py | CloudCrash | 278 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_reboot | test_cloud_crash.py | CloudCrash | 290 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_reboot | test_cloud_crash.py | CloudCrash | 297 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set_reboot | test_cloud_crash.py | CloudCrash | 302 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set_reboot | test_cloud_crash.py | CloudCrash | 308 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_data_set_reboot | test_cloud_crash.py | CloudCrash | 312 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_data_set_reboot | test_cloud_crash.py | CloudCrash | 319 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_data_set_reboot | test_cloud_crash.py | CloudCrash | 323 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_data_set_reboot | test_cloud_crash.py | CloudCrash | 329 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_data_set_reboot | test_cloud_crash.py | CloudCrash | 334 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_data_set_reboot | test_cloud_crash.py | CloudCrash | 340 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_data_set_reboot | test_cloud_crash.py | CloudCrash | 344 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_data_set_reboot | test_cloud_crash.py | CloudCrash | 351 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_reboot | test_cloud_crash.py | CloudCrash | 355 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_data_reboot | test_cloud_crash.py | CloudCrash | 362 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set_reboot | test_cloud_crash.py | CloudCrash | 367 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set_reboot | test_cloud_crash.py | CloudCrash | 373 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_object_set_reboot | test_cloud_crash.py | CloudCrash | 376 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_object_set_reboot | test_cloud_crash.py | CloudCrash | 382 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_object_set_reboot | test_cloud_crash.py | CloudCrash | 385 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_object_set_reboot | test_cloud_crash.py | CloudCrash | 391 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_object_set_reboot | test_cloud_crash.py | CloudCrash | 394 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_object_set_reboot | test_cloud_crash.py | CloudCrash | 400 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_object_set_reboot | test_cloud_crash.py | CloudCrash | 403 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_object_set_reboot | test_cloud_crash.py | CloudCrash | 409 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_set_reboot | test_cloud_crash.py | CloudCrash | 412 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_object_set_reboot | test_cloud_crash.py | CloudCrash | 418 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_app_crash | test_cloud_crash.py | CloudCrash | 422 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_app_crash | test_cloud_crash.py | CloudCrash | 429 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set_app_crash | test_cloud_crash.py | CloudCrash | 433 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set_app_crash | test_cloud_crash.py | CloudCrash | 440 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_data_set_app_crash | test_cloud_crash.py | CloudCrash | 444 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_data_set_app_crash | test_cloud_crash.py | CloudCrash | 451 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_data_set_app_crash | test_cloud_crash.py | CloudCrash | 455 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_data_set_app_crash | test_cloud_crash.py | CloudCrash | 461 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_data_set_app_crash | test_cloud_crash.py | CloudCrash | 465 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_data_set_app_crash | test_cloud_crash.py | CloudCrash | 472 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_data_set_app_crash | test_cloud_crash.py | CloudCrash | 476 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_data_set_app_crash | test_cloud_crash.py | CloudCrash | 483 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_app_crash | test_cloud_crash.py | CloudCrash | 487 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_data_app_crash | test_cloud_crash.py | CloudCrash | 494 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set_app_crash | test_cloud_crash.py | CloudCrash | 499 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set_app_crash | test_cloud_crash.py | CloudCrash | 505 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set_app_crash | test_cloud_crash.py | CloudCrash | 509 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set_app_crash | test_cloud_crash.py | CloudCrash | 515 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_object_set_app_crash | test_cloud_crash.py | CloudCrash | 518 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_object_set_app_crash | test_cloud_crash.py | CloudCrash | 524 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_object_set_app_crash | test_cloud_crash.py | CloudCrash | 527 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_object_set_app_crash | test_cloud_crash.py | CloudCrash | 533 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_object_set_app_crash | test_cloud_crash.py | CloudCrash | 536 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_object_set_app_crash | test_cloud_crash.py | CloudCrash | 542 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_object_set_app_crash | test_cloud_crash.py | CloudCrash | 545 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_object_set_app_crash | test_cloud_crash.py | CloudCrash | 551 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_set_app_crash | test_cloud_crash.py | CloudCrash | 554 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_object_set_app_crash | test_cloud_crash.py | CloudCrash | 559 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_mobility.py | CloudMobility | 105 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_mobility.py | CloudMobility | 110 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_mobility.py | CloudMobility | 115 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_mobility.py | CloudMobility | 131 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_mobility.py | CloudMobility | 137 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_mobility.py | CloudMobility | 142 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_mobility.py | CloudMobility | 148 | Defined test function; referenced by at least one suite list. |
| test_upload_small_data_set_mobility | test_cloud_mobility.py | CloudMobility | 171 | Defined test function; referenced by at least one suite list. |
| test_download_small_data_set_mobility | test_cloud_mobility.py | CloudMobility | 178 | Defined test function; referenced by at least one suite list. |
| test_upload_large_data_set_mobility | test_cloud_mobility.py | CloudMobility | 183 | Defined test function; referenced by at least one suite list. |
| test_download_large_data_set_mobility | test_cloud_mobility.py | CloudMobility | 190 | Defined test function; referenced by at least one suite list. |
| test_upload_small_object_set_mobility | test_cloud_mobility.py | CloudMobility | 195 | Defined test function; referenced by at least one suite list. |
| test_download_small_object_set_mobility | test_cloud_mobility.py | CloudMobility | 202 | Defined test function; referenced by at least one suite list. |
| test_upload_large_object_set_mobility | test_cloud_mobility.py | CloudMobility | 207 | Defined test function; referenced by at least one suite list. |
| test_download_large_object_set_mobility | test_cloud_mobility.py | CloudMobility | 214 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_modify.py | CloudPauseResume | 126 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_modify.py | CloudPauseResume | 132 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_modify.py | CloudPauseResume | 135 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_modify.py | CloudPauseResume | 142 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 180 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 185 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 189 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 195 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 199 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 204 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 207 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 213 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 217 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 224 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 228 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 234 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_pause_modify | test_cloud_modify.py | CloudPauseResume | 238 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_data_pause_modify | test_cloud_modify.py | CloudPauseResume | 243 | Defined test function; referenced by at least one suite list. |
| test_upload_multi_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 247 | Defined test function; not referenced by any detected suite list. |
| test_download_multi_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 253 | Defined test function; not referenced by any detected suite list. |
| test_upload_single_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 259 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 264 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 268 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 274 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 278 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 283 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 286 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 292 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 296 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 303 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 307 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 313 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_pause_modify | test_cloud_modify.py | CloudPauseResume | 317 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_object_pause_modify | test_cloud_modify.py | CloudPauseResume | 322 | Defined test function; referenced by at least one suite list. |
| test_upload_multi_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 326 | Defined test function; not referenced by any detected suite list. |
| test_download_multi_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 332 | Defined test function; not referenced by any detected suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_modify.py | CloudPauseResume | 338 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_modify.py | CloudPauseResume | 341 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_modify.py | CloudPauseResume | 344 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_pause_resume.py | CloudPauseResume | 128 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_pause_resume.py | CloudPauseResume | 134 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_pause_resume.py | CloudPauseResume | 146 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_pause_resume.py | CloudPauseResume | 155 | Defined test function; referenced by at least one suite list. |
| test_configure_the_bryck | test_cloud_pause_resume.py | CloudPauseResume | 224 | Defined test function; referenced by at least one suite list. |
| test_eject_the_bryck | test_cloud_pause_resume.py | CloudPauseResume | 231 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 240 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 246 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 251 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 257 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 261 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 268 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 272 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 278 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 282 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 289 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 293 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_data_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 300 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_pause | test_cloud_pause_resume.py | CloudPauseResume | 304 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_data_pause | test_cloud_pause_resume.py | CloudPauseResume | 310 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 314 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 320 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 325 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 332 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 336 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 343 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 347 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 353 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 357 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 365 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 369 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_object_set_pause | test_cloud_pause_resume.py | CloudPauseResume | 376 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_pause | test_cloud_pause_resume.py | CloudPauseResume | 380 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_object_pause | test_cloud_pause_resume.py | CloudPauseResume | 386 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_pause_resume.py | CloudPauseResume | 391 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_pause_resume.py | CloudPauseResume | 405 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_pause_resume.py | CloudPauseResume | 409 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_transfer.py | CloudTransfer | 155 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_transfer.py | CloudTransfer | 161 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_transfer.py | CloudTransfer | 174 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_transfer.py | CloudTransfer | 182 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_transfer.py | CloudTransfer | 192 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_transfer.py | CloudTransfer | 206 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_transfer.py | CloudTransfer | 209 | Defined test function; referenced by at least one suite list. |
| test_configure_the_bryck | test_cloud_transfer.py | CloudTransfer | 276 | Defined test function; referenced by at least one suite list. |
| test_eject_the_bryck | test_cloud_transfer.py | CloudTransfer | 283 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set | test_cloud_transfer.py | CloudTransfer | 295 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set | test_cloud_transfer.py | CloudTransfer | 301 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 305 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 311 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set | test_cloud_transfer.py | CloudTransfer | 317 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set | test_cloud_transfer.py | CloudTransfer | 324 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 328 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 335 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_data_set | test_cloud_transfer.py | CloudTransfer | 340 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_data_set | test_cloud_transfer.py | CloudTransfer | 349 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 353 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 362 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_data_set | test_cloud_transfer.py | CloudTransfer | 367 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_data_set | test_cloud_transfer.py | CloudTransfer | 375 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 379 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 387 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_data_set | test_cloud_transfer.py | CloudTransfer | 391 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_data_set | test_cloud_transfer.py | CloudTransfer | 397 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 401 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 407 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_data_set | test_cloud_transfer.py | CloudTransfer | 411 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_data_set | test_cloud_transfer.py | CloudTransfer | 418 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 422 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_data_set_failed_validation | test_cloud_transfer.py | CloudTransfer | 430 | Defined test function; referenced by at least one suite list. |
| test_upload_multi_stream_single_file_small_data_set | test_cloud_transfer.py | CloudTransfer | 436 | Defined test function; referenced by at least one suite list. |
| test_download_multi_stream_single_file_small_data_set | test_cloud_transfer.py | CloudTransfer | 447 | Defined test function; referenced by at least one suite list. |
| test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_upload | test_cloud_transfer.py | CloudTransfer | 455 | Defined test function; referenced by at least one suite list. |
| test_to_check_transfer_can_not_be_done_if_cloud_not_configured_upload | test_cloud_transfer.py | CloudTransfer | 463 | Defined test function; referenced by at least one suite list. |
| test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_upload | test_cloud_transfer.py | CloudTransfer | 481 | Defined test function; referenced by at least one suite list. |
| test_to_check_if_user_invoke_duplicate_transfer_upload | test_cloud_transfer.py | CloudTransfer | 484 | Defined test function; referenced by at least one suite list. |
| test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_download | test_cloud_transfer.py | CloudTransfer | 494 | Defined test function; referenced by at least one suite list. |
| test_to_check_transfer_can_not_be_done_if_cloud_not_configured_download | test_cloud_transfer.py | CloudTransfer | 497 | Defined test function; referenced by at least one suite list. |
| test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_download | test_cloud_transfer.py | CloudTransfer | 515 | Defined test function; referenced by at least one suite list. |
| test_to_check_if_user_invoke_duplicate_transfer_download | test_cloud_transfer.py | CloudTransfer | 518 | Defined test function; referenced by at least one suite list. |
| test_to_cancel_ongoing_transfer | test_cloud_transfer.py | CloudTransfer | 528 | Defined test function; referenced by at least one suite list. |
| test_to_reinitiate_previously_cancelled_transfer | test_cloud_transfer.py | CloudTransfer | 538 | Defined test function; referenced by at least one suite list. |
| test_to_pause_the_transfer_and_delete_the_data_src | test_cloud_transfer.py | CloudTransfer | 548 | Defined test function; referenced by at least one suite list. |
| test_to_pause_the_transfer_delete_cloud_configuration | test_cloud_transfer.py | CloudTransfer | 558 | Defined test function; referenced by at least one suite list. |
| test_to_submit_N_number_of_transfers | test_cloud_transfer.py | CloudTransfer | 576 | Defined test function; referenced by at least one suite list. |
| test_to_specify_N_number_of_live_parallel_transfers | test_cloud_transfer.py | CloudTransfer | 581 | Defined test function; referenced by at least one suite list. |
| test_to_track_the_progress_of_one_transfer | test_cloud_transfer.py | CloudTransfer | 592 | Defined test function; referenced by at least one suite list. |
| test_to_get_all_the_transfers_details_for_specific_transfer_state | test_cloud_transfer.py | CloudTransfer | 602 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_object_set | test_cloud_transfer.py | CloudTransfer | 614 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_object_set | test_cloud_transfer.py | CloudTransfer | 624 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set | test_cloud_transfer.py | CloudTransfer | 628 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set | test_cloud_transfer.py | CloudTransfer | 634 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_small_object_set | test_cloud_transfer.py | CloudTransfer | 638 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_small_object_set | test_cloud_transfer.py | CloudTransfer | 645 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_large_object_set | test_cloud_transfer.py | CloudTransfer | 649 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_large_object_set | test_cloud_transfer.py | CloudTransfer | 657 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_large_object_set | test_cloud_transfer.py | CloudTransfer | 660 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_large_object_set | test_cloud_transfer.py | CloudTransfer | 666 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_N_level_large_object_set | test_cloud_transfer.py | CloudTransfer | 669 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_N_level_large_object_set | test_cloud_transfer.py | CloudTransfer | 676 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_with_billions_file_terabyte_object | test_cloud_transfer.py | CloudTransfer | 681 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_with_billions_file_terabyte_object | test_cloud_transfer.py | CloudTransfer | 688 | Defined test function; referenced by at least one suite list. |
| test_upload_multi_stream_single_file_small_object_set | test_cloud_transfer.py | CloudTransfer | 694 | Defined test function; referenced by at least one suite list. |
| test_download_multi_stream_single_file_small_object_set | test_cloud_transfer.py | CloudTransfer | 705 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_cloud_transfer_shipment.py | CloudTransferShipment | 104 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_cloud_transfer_shipment.py | CloudTransferShipment | 110 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_cloud_transfer_shipment.py | CloudTransferShipment | 121 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_cloud_transfer_shipment.py | CloudTransferShipment | 129 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_cloud_transfer_shipment.py | CloudTransferShipment | 135 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_cloud_transfer_shipment.py | CloudTransferShipment | 138 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_cloud_transfer_shipment.py | CloudTransferShipment | 141 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_data_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 223 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_data_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 229 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_data_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 233 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_data_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 241 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_single_file_small_object_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 246 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_single_file_small_object_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 253 | Defined test function; referenced by at least one suite list. |
| test_upload_single_stream_directory_small_object_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 257 | Defined test function; referenced by at least one suite list. |
| test_download_single_stream_directory_small_object_set | test_cloud_transfer_shipment.py | CloudTransferShipment | 263 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_config.py | ConfigTest | 113 | Defined test function; referenced by at least one suite list. |
| test_configure_filestore_with_enc_dp_IO_DS | test_config.py | ConfigTest | 118 | Defined test function; referenced by at least one suite list. |
| test_eject_with_hot_pluggability_true_with_enc | test_config.py | ConfigTest | 172 | Defined test function; referenced by at least one suite list. |
| test_eject_with_hot_pluggability_true_without_enc | test_config.py | ConfigTest | 181 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_with_hot_pluggable_eject | test_config.py | ConfigTest | 191 | Defined test function; referenced by at least one suite list. |
| test_hot_pluggability_with_skip_drives | test_config.py | ConfigTest | 201 | Defined test function; referenced by at least one suite list. |
| test_dedup_storage_efficiency | test_config.py | ConfigTest | 212 | Defined test function; referenced by at least one suite list. |
| test_dedup_delete_directory | test_config.py | ConfigTest | 226 | Defined test function; referenced by at least one suite list. |
| test_dedup_measure_performance | test_config.py | ConfigTest | 239 | Defined test function; referenced by at least one suite list. |
| test_dedup_transfer_non_duplicate_data | test_config.py | ConfigTest | 254 | Defined test function; referenced by at least one suite list. |
| test_dedup_transfer_duplicate_data | test_config.py | ConfigTest | 268 | Defined test function; referenced by at least one suite list. |
| test_dedup_erase_bryck | test_config.py | ConfigTest | 282 | Defined test function; referenced by at least one suite list. |
| test_dedup_mount_bryck | test_config.py | ConfigTest | 296 | Defined test function; referenced by at least one suite list. |
| test_compresion_storage_efficiency | test_config.py | ConfigTest | 309 | Defined test function; referenced by at least one suite list. |
| test_compression_transfer_non_compressible_data | test_config.py | ConfigTest | 323 | Defined test function; referenced by at least one suite list. |
| test_compression_erase_bryck | test_config.py | ConfigTest | 339 | Defined test function; referenced by at least one suite list. |
| test_compression_mount_bryck | test_config.py | ConfigTest | 353 | Defined test function; referenced by at least one suite list. |
| test_remote_object_transfer | test_config.py | ConfigTest | 368 | Defined test function; referenced by at least one suite list. |
| test_add_alert_user | test_config.py | ConfigTest | 379 | Defined test function; referenced by at least one suite list. |
| test_configure_email_sender | test_config.py | ConfigTest | 392 | Defined test function; referenced by at least one suite list. |
| test_deconfigure_email_sender | test_config.py | ConfigTest | 409 | Defined test function; referenced by at least one suite list. |
| test_list_email_sender | test_config.py | ConfigTest | 419 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_config_shipment.py | ConfigTestShipment | 93 | Defined test function; referenced by at least one suite list. |
| test_configure_filestore_with_enc_dp_IO_DS | test_config_shipment.py | ConfigTestShipment | 98 | Defined test function; referenced by at least one suite list. |
| test_remote_object_transfer | test_config_shipment.py | ConfigTestShipment | 152 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_data_corrution.py | TestDataCorruption | 107 | Defined test function; referenced by at least one suite list. |
| test_encryption_corruption_one_drive | test_data_corrution.py | TestDataCorruption | 111 | Defined test function; referenced by at least one suite list. |
| test_encryption_corruption_two_drive | test_data_corrution.py | TestDataCorruption | 116 | Defined test function; referenced by at least one suite list. |
| test_encryption_corruption_multi_drive | test_data_corrution.py | TestDataCorruption | 121 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_with_enc_one_partition | test_data_corrution.py | TestDataCorruption | 126 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_with_enc_two_partition | test_data_corrution.py | TestDataCorruption | 136 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_with_enc_multi_partition | test_data_corrution.py | TestDataCorruption | 146 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_without_enc_one_partition | test_data_corrution.py | TestDataCorruption | 156 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_without_enc_two_partition | test_data_corrution.py | TestDataCorruption | 166 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_without_enc_multi_partition | test_data_corrution.py | TestDataCorruption | 176 | Defined test function; referenced by at least one suite list. |
| test_encryption_corruption_one_drive_luns | test_data_corrution.py | TestDataCorruption | 186 | Defined test function; referenced by at least one suite list. |
| test_encryption_corruption_two_drive_luns | test_data_corrution.py | TestDataCorruption | 192 | Defined test function; referenced by at least one suite list. |
| test_encryption_corruption_multi_drive_luns | test_data_corrution.py | TestDataCorruption | 198 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_with_enc_one_partition_luns | test_data_corrution.py | TestDataCorruption | 204 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_with_enc_two_partition_luns | test_data_corrution.py | TestDataCorruption | 215 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_with_enc_multi_partition_luns | test_data_corrution.py | TestDataCorruption | 226 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_without_enc_one_partition_luns | test_data_corrution.py | TestDataCorruption | 237 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_without_enc_two_partition_luns | test_data_corrution.py | TestDataCorruption | 248 | Defined test function; referenced by at least one suite list. |
| test_partition_corruption_without_enc_multi_partition_luns | test_data_corrution.py | TestDataCorruption | 259 | Defined test function; referenced by at least one suite list. |
| test_data_protection_io_failure | test_data_corrution.py | TestDataCorruption | 270 | Defined test function; referenced by at least one suite list. |
| test_data_protection_checksum_failure | test_data_corrution.py | TestDataCorruption | 279 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_data_dart.py | DataDartTest | 122 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_aws | test_data_dart.py | DataDartTest | 126 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_azure | test_data_dart.py | DataDartTest | 130 | Defined test function; referenced by at least one suite list. |
| test_configure_cloud_gcp | test_data_dart.py | DataDartTest | 138 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_aws | test_data_dart.py | DataDartTest | 142 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_azure | test_data_dart.py | DataDartTest | 145 | Defined test function; referenced by at least one suite list. |
| test_delete_cloud_configuraiton_gcp | test_data_dart.py | DataDartTest | 148 | Defined test function; referenced by at least one suite list. |
| test_verify_bryck_fs | test_data_dart.py | DataDartTest | 153 | Defined test function; referenced by at least one suite list. |
| test_verify_bryck_object | test_data_dart.py | DataDartTest | 158 | Defined test function; referenced by at least one suite list. |
| test_verify_cloud_transfer_fs | test_data_dart.py | DataDartTest | 163 | Defined test function; referenced by at least one suite list. |
| test_verify_cloud_transfer_object | test_data_dart.py | DataDartTest | 170 | Defined test function; referenced by at least one suite list. |
| test_verify_bryck_fs_missing_files | test_data_dart.py | DataDartTest | 176 | Defined test function; referenced by at least one suite list. |
| test_verify_bryck_object_missing_files | test_data_dart.py | DataDartTest | 181 | Defined test function; referenced by at least one suite list. |
| test_verify_cloud_down_missing_files | test_data_dart.py | DataDartTest | 186 | Defined test function; referenced by at least one suite list. |
| test_verify_cloud_down_missing_object | test_data_dart.py | DataDartTest | 192 | Defined test function; referenced by at least one suite list. |
| test_verify_bryck_fs_corrupted_files | test_data_dart.py | DataDartTest | 200 | Defined test function; referenced by at least one suite list. |
| test_verify_bryck_object_corrupted_files | test_data_dart.py | DataDartTest | 205 | Defined test function; referenced by at least one suite list. |
| test_to_create_admin | test_data_dart_admin.py | DataDartAdminTest | 122 | Defined test function; referenced by at least one suite list. |
| test_to_login_to_admin_space | test_data_dart_admin.py | DataDartAdminTest | 128 | Defined test function; referenced by at least one suite list. |
| test_to_update_contact_details | test_data_dart_admin.py | DataDartAdminTest | 136 | Defined test function; referenced by at least one suite list. |
| test_to_get_admin_details | test_data_dart_admin.py | DataDartAdminTest | 140 | Defined test function; referenced by at least one suite list. |
| test_to_create_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 145 | Defined test function; referenced by at least one suite list. |
| test_to_update_the_details_of_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 151 | Defined test function; referenced by at least one suite list. |
| test_to_activate_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 155 | Defined test function; referenced by at least one suite list. |
| test_to_deactivate_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 158 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 161 | Defined test function; referenced by at least one suite list. |
| test_to_get_the_list_of_all_shipping_center_of_a_zone | test_data_dart_admin.py | DataDartAdminTest | 167 | Defined test function; referenced by at least one suite list. |
| test_to_search_for_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 170 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_orders_of_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 174 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_subscriptions_of_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 177 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_infra_engg_of_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 180 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_available_hardwares_of_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 183 | Defined test function; referenced by at least one suite list. |
| test_to_create_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 187 | Defined test function; referenced by at least one suite list. |
| test_to_update_the_details_of_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 190 | Defined test function; referenced by at least one suite list. |
| test_to_activate_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 194 | Defined test function; referenced by at least one suite list. |
| test_to_deactivate_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 197 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 200 | Defined test function; referenced by at least one suite list. |
| test_to_get_the_list_of_all_cloud_end_point_of_a_zone | test_data_dart_admin.py | DataDartAdminTest | 203 | Defined test function; referenced by at least one suite list. |
| test_to_search_for_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 206 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_orders_of_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 210 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_subscriptions_of_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 213 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_infra_engg_of_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 217 | Defined test function; referenced by at least one suite list. |
| test_to_add_clouds_to_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 220 | Defined test function; referenced by at least one suite list. |
| test_to_get_public_clouds_of_a_cloud_point | test_data_dart_admin.py | DataDartAdminTest | 224 | Defined test function; referenced by at least one suite list. |
| test_to_create_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 229 | Defined test function; referenced by at least one suite list. |
| test_to_update_the_details_of_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 232 | Defined test function; referenced by at least one suite list. |
| test_to_activate_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 236 | Defined test function; referenced by at least one suite list. |
| test_to_deactivate_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 239 | Defined test function; referenced by at least one suite list. |
| test_to_get_an_infra_engg_by_id | test_data_dart_admin.py | DataDartAdminTest | 242 | Defined test function; referenced by at least one suite list. |
| test_to_get_an_infra_engg_by_mail_id | test_data_dart_admin.py | DataDartAdminTest | 245 | Defined test function; referenced by at least one suite list. |
| test_to_list_out_all_infra_engg_of_a_zone | test_data_dart_admin.py | DataDartAdminTest | 249 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_orders_of_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 253 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_all_subscriptions_of_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 256 | Defined test function; referenced by at least one suite list. |
| test_to_get_shipping_center_of_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 259 | Defined test function; referenced by at least one suite list. |
| test_to_get_cloud_end_point_of_an_infra_engg | test_data_dart_admin.py | DataDartAdminTest | 262 | Defined test function; referenced by at least one suite list. |
| test_to_assign_an_infra_engg_to_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 266 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_an_infra_engg_to_a_shipping_center | test_data_dart_admin.py | DataDartAdminTest | 269 | Defined test function; referenced by at least one suite list. |
| test_to_assign_an_infra_engg_to_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 273 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_an_infra_engg_to_a_cloud_end_point | test_data_dart_admin.py | DataDartAdminTest | 276 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_a_customer_by_uuid | test_data_dart_admin.py | DataDartAdminTest | 280 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_a_customer_by_mail_id | test_data_dart_admin.py | DataDartAdminTest | 284 | Defined test function; referenced by at least one suite list. |
| test_to_list_out_all_the_customer | test_data_dart_admin.py | DataDartAdminTest | 289 | Defined test function; referenced by at least one suite list. |
| test_to_search_for_a_customer | test_data_dart_admin.py | DataDartAdminTest | 291 | Defined test function; referenced by at least one suite list. |
| test_to_get_orders_of_a_customer | test_data_dart_admin.py | DataDartAdminTest | 293 | Defined test function; referenced by at least one suite list. |
| test_to_get_subscriptions_of_a_customer | test_data_dart_admin.py | DataDartAdminTest | 297 | Defined test function; referenced by at least one suite list. |
| test_to_create_a_customer | test_data_dart_customer.py | DataDartCustomerTest | 96 | Defined test function; referenced by at least one suite list. |
| test_to_login_to_customer_space | test_data_dart_customer.py | DataDartCustomerTest | 101 | Defined test function; referenced by at least one suite list. |
| test_to_get_customer_by_uid | test_data_dart_customer.py | DataDartCustomerTest | 103 | Defined test function; referenced by at least one suite list. |
| test_to_get_customer_by_email | test_data_dart_customer.py | DataDartCustomerTest | 106 | Defined test function; referenced by at least one suite list. |
| test_to_create_an_order | test_data_dart_customer.py | DataDartCustomerTest | 109 | Defined test function; referenced by at least one suite list. |
| test_to_get_order_by_uid | test_data_dart_customer.py | DataDartCustomerTest | 112 | Defined test function; referenced by at least one suite list. |
| test_to_get_hardwares_of_order | test_data_dart_customer.py | DataDartCustomerTest | 115 | Defined test function; referenced by at least one suite list. |
| test_to_get_orders_of_a_customer | test_data_dart_customer.py | DataDartCustomerTest | 118 | Defined test function; referenced by at least one suite list. |
| test_to_update_timeline_of_order | test_data_dart_customer.py | DataDartCustomerTest | 121 | Defined test function; referenced by at least one suite list. |
| test_to_get_timeline_of_order | test_data_dart_customer.py | DataDartCustomerTest | 123 | Defined test function; referenced by at least one suite list. |
| test_to_cancel_an_order | test_data_dart_customer.py | DataDartCustomerTest | 127 | Defined test function; referenced by at least one suite list. |
| test_to_create_a_subscription | test_data_dart_customer.py | DataDartCustomerTest | 130 | Defined test function; referenced by at least one suite list. |
| test_to_get_subscription_by_uid | test_data_dart_customer.py | DataDartCustomerTest | 133 | Defined test function; referenced by at least one suite list. |
| test_to_get_hardwares_of_subscription | test_data_dart_customer.py | DataDartCustomerTest | 136 | Defined test function; referenced by at least one suite list. |
| test_to_get_subscriptions_of_a_customer | test_data_dart_customer.py | DataDartCustomerTest | 139 | Defined test function; referenced by at least one suite list. |
| test_to_update_timeline_of_subscription | test_data_dart_customer.py | DataDartCustomerTest | 142 | Defined test function; referenced by at least one suite list. |
| test_to_get_timeline_of_subscription | test_data_dart_customer.py | DataDartCustomerTest | 144 | Defined test function; referenced by at least one suite list. |
| test_to_cancel_a_subscription | test_data_dart_customer.py | DataDartCustomerTest | 148 | Defined test function; referenced by at least one suite list. |
| test_to_assign_source_contact_to_order | test_data_dart_customer.py | DataDartCustomerTest | 151 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_source_contact_to_order | test_data_dart_customer.py | DataDartCustomerTest | 154 | Defined test function; referenced by at least one suite list. |
| test_to_assign_destinaiton_contact_to_order | test_data_dart_customer.py | DataDartCustomerTest | 157 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_destication_contact_to_order | test_data_dart_customer.py | DataDartCustomerTest | 160 | Defined test function; referenced by at least one suite list. |
| test_to_assign_source_contact_to_subscription | test_data_dart_customer.py | DataDartCustomerTest | 163 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_source_contact_from_subscription | test_data_dart_customer.py | DataDartCustomerTest | 166 | Defined test function; referenced by at least one suite list. |
| test_to_login_to_infra_engg_space | test_data_dart_infraengg.py | DataDartInfraEnggTest | 148 | Defined test function; referenced by at least one suite list. |
| test_to_update_profile_details | test_data_dart_infraengg.py | DataDartInfraEnggTest | 150 | Defined test function; referenced by at least one suite list. |
| test_to_get_infra_engg_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 154 | Defined test function; referenced by at least one suite list. |
| test_to_get_infra_engg_by_email | test_data_dart_infraengg.py | DataDartInfraEnggTest | 158 | Defined test function; referenced by at least one suite list. |
| test_to_get_all_infra_engg_of_a_zone | test_data_dart_infraengg.py | DataDartInfraEnggTest | 161 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_shipping_center_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 166 | Defined test function; referenced by at least one suite list. |
| test_to_get_the_list_of_shipping_centers_by_zone | test_data_dart_infraengg.py | DataDartInfraEnggTest | 169 | Defined test function; referenced by at least one suite list. |
| test_to_search_a_shipping_center_by_name | test_data_dart_infraengg.py | DataDartInfraEnggTest | 172 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_cloud_end_point_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 178 | Defined test function; referenced by at least one suite list. |
| test_to_get_the_list_of_cloud_end_point_by_zone | test_data_dart_infraengg.py | DataDartInfraEnggTest | 181 | Defined test function; referenced by at least one suite list. |
| test_to_search_a_cloud_end_point_by_name | test_data_dart_infraengg.py | DataDartInfraEnggTest | 184 | Defined test function; referenced by at least one suite list. |
| test_to_get_details_of_customer_by_mail | test_data_dart_infraengg.py | DataDartInfraEnggTest | 189 | Defined test function; referenced by at least one suite list. |
| test_to_get_the_list_of_customers_by_zone | test_data_dart_infraengg.py | DataDartInfraEnggTest | 192 | Defined test function; referenced by at least one suite list. |
| test_to_search_a_customer_by_name | test_data_dart_infraengg.py | DataDartInfraEnggTest | 195 | Defined test function; referenced by at least one suite list. |
| test_to_get_order_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 200 | Defined test function; referenced by at least one suite list. |
| test_to_get_all_orders_of_a_zone | test_data_dart_infraengg.py | DataDartInfraEnggTest | 203 | Defined test function; referenced by at least one suite list. |
| test_to_change_location_of_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 206 | Defined test function; referenced by at least one suite list. |
| test_to_change_internal_status_of_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 209 | Defined test function; referenced by at least one suite list. |
| test_to_change_overall_status_of_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 212 | Defined test function; referenced by at least one suite list. |
| test_to_assign_hardware_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 215 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_hardware_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 218 | Defined test function; referenced by at least one suite list. |
| test_to_assign_source_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 221 | Defined test function; referenced by at least one suite list. |
| test_to_assign_destination_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 224 | Defined test function; referenced by at least one suite list. |
| test_to_assign_engg_to_source_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 227 | Defined test function; referenced by at least one suite list. |
| test_to_assign_engg_to_destinaiton_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 230 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_source_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 233 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_destination_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 236 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_engg_to_source_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 239 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_engg_to_destinaiton_shipping_center_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 242 | Defined test function; referenced by at least one suite list. |
| test_to_assign_source_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 245 | Defined test function; referenced by at least one suite list. |
| test_to_assign_destination_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 248 | Defined test function; referenced by at least one suite list. |
| test_to_assign_engg_to_source_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 251 | Defined test function; referenced by at least one suite list. |
| test_to_assign_engg_to_destinaiton_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 254 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_source_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 257 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_destination_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 260 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_engg_to_source_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 263 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_engg_to_destinaiton_cloud_end_point_to_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 266 | Defined test function; referenced by at least one suite list. |
| test_to_view_timeline_of_an_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 269 | Defined test function; referenced by at least one suite list. |
| test_to_update_time_line_of_order | test_data_dart_infraengg.py | DataDartInfraEnggTest | 272 | Defined test function; referenced by at least one suite list. |
| test_to_view_all_the_orders_associated_with_a_shipping_center | test_data_dart_infraengg.py | DataDartInfraEnggTest | 276 | Defined test function; referenced by at least one suite list. |
| test_to_view_all_orders_associated_with_a_cloud_end_point | test_data_dart_infraengg.py | DataDartInfraEnggTest | 279 | Defined test function; referenced by at least one suite list. |
| test_to_get_subscription_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 284 | Defined test function; referenced by at least one suite list. |
| test_to_get_all_subscriptions_of_a_zone | test_data_dart_infraengg.py | DataDartInfraEnggTest | 287 | Defined test function; referenced by at least one suite list. |
| test_to_change_location_of_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 290 | Defined test function; referenced by at least one suite list. |
| test_to_change_internal_status_of_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 293 | Defined test function; referenced by at least one suite list. |
| test_to_change_overall_status_of_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 296 | Defined test function; referenced by at least one suite list. |
| test_to_assign_hardware_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 299 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_hardware_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 302 | Defined test function; referenced by at least one suite list. |
| test_to_assign_source_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 305 | Defined test function; referenced by at least one suite list. |
| test_to_assign_destination_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 308 | Defined test function; referenced by at least one suite list. |
| test_to_assign_engg_to_source_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 311 | Defined test function; referenced by at least one suite list. |
| test_to_assign_engg_to_destinaiton_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 314 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_source_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 317 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_destination_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 320 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_engg_to_source_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 323 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_engg_to_destinaiton_shipping_center_to_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 326 | Defined test function; referenced by at least one suite list. |
| test_to_view_timeline_of_an_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 329 | Defined test function; referenced by at least one suite list. |
| test_to_update_time_line_of_subscription | test_data_dart_infraengg.py | DataDartInfraEnggTest | 332 | Defined test function; referenced by at least one suite list. |
| test_to_view_all_the_subscriptions_associated_with_a_shipping_center | test_data_dart_infraengg.py | DataDartInfraEnggTest | 336 | Defined test function; referenced by at least one suite list. |
| test_to_add_bryck | test_data_dart_infraengg.py | DataDartInfraEnggTest | 341 | Defined test function; referenced by at least one suite list. |
| test_to_add_bryck_ai | test_data_dart_infraengg.py | DataDartInfraEnggTest | 344 | Defined test function; referenced by at least one suite list. |
| test_to_add_bryck_tray | test_data_dart_infraengg.py | DataDartInfraEnggTest | 347 | Defined test function; referenced by at least one suite list. |
| test_to_add_server | test_data_dart_infraengg.py | DataDartInfraEnggTest | 350 | Defined test function; referenced by at least one suite list. |
| test_to_get_hardware_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 353 | Defined test function; referenced by at least one suite list. |
| test_to_activate_hardware_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 356 | Defined test function; referenced by at least one suite list. |
| test_to_deactivate_hardware_by_uid | test_data_dart_infraengg.py | DataDartInfraEnggTest | 359 | Defined test function; referenced by at least one suite list. |
| test_to_assign_hardware_to_shipping_center | test_data_dart_infraengg.py | DataDartInfraEnggTest | 362 | Defined test function; referenced by at least one suite list. |
| test_to_unassign_hardware_to_shipping_center | test_data_dart_infraengg.py | DataDartInfraEnggTest | 365 | Defined test function; referenced by at least one suite list. |
| test_to_freeup_hardware | test_data_dart_infraengg.py | DataDartInfraEnggTest | 368 | Defined test function; referenced by at least one suite list. |
| test_to_request_for_hardware_to_other_shipping_center | test_data_dart_infraengg.py | DataDartInfraEnggTest | 372 | Defined test function; referenced by at least one suite list. |
| test_to_create_entities | test_data_dart_use.py | DataDartUseTest | 84 | Defined test function; referenced by at least one suite list. |
| test_to_check_private_cloud_to_private_cloud_transfer | test_data_dart_use.py | DataDartUseTest | 95 | Defined test function; referenced by at least one suite list. |
| test_to_check_private_cloud_to_public_cloud_transfer_gcp | test_data_dart_use.py | DataDartUseTest | 98 | Defined test function; referenced by at least one suite list. |
| test_to_check_private_cloud_to_public_cloud_transfer_aws | test_data_dart_use.py | DataDartUseTest | 101 | Defined test function; referenced by at least one suite list. |
| test_to_check_private_cloud_to_public_cloud_transfer_azure | test_data_dart_use.py | DataDartUseTest | 105 | Defined test function; referenced by at least one suite list. |
| test_to_check_public_cloud_to_private_cloud_transfer_gcp | test_data_dart_use.py | DataDartUseTest | 109 | Defined test function; referenced by at least one suite list. |
| test_to_check_public_cloud_to_private_cloud_transfer_aws | test_data_dart_use.py | DataDartUseTest | 113 | Defined test function; referenced by at least one suite list. |
| test_to_check_public_cloud_to_private_cloud_transfer_azure | test_data_dart_use.py | DataDartUseTest | 117 | Defined test function; referenced by at least one suite list. |
| test_to_check_gcp_to_aws_transfer | test_data_dart_use.py | DataDartUseTest | 121 | Defined test function; referenced by at least one suite list. |
| test_to_check_gcp_to_azure_transfer | test_data_dart_use.py | DataDartUseTest | 126 | Defined test function; referenced by at least one suite list. |
| test_to_check_aws_to_gcp_transfer | test_data_dart_use.py | DataDartUseTest | 131 | Defined test function; referenced by at least one suite list. |
| test_to_check_aws_to_azure_transfer | test_data_dart_use.py | DataDartUseTest | 136 | Defined test function; referenced by at least one suite list. |
| test_to_check_subscription | test_data_dart_use.py | DataDartUseTest | 141 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_drive_failure.py | TestDriveFailure | 103 | Defined test function; referenced by at least one suite list. |
| test_power_failure | test_drive_failure.py | TestDriveFailure | 107 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_one_drive | test_drive_failure.py | TestDriveFailure | 111 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_one_drive_neagative_case | test_drive_failure.py | TestDriveFailure | 121 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_multi_drive | test_drive_failure.py | TestDriveFailure | 131 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_multi_drive_negative_case | test_drive_failure.py | TestDriveFailure | 141 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_one_drive_luns | test_drive_failure.py | TestDriveFailure | 151 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_one_drive_neagative_case_luns | test_drive_failure.py | TestDriveFailure | 161 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_multi_drive_luns | test_drive_failure.py | TestDriveFailure | 171 | Defined test function; referenced by at least one suite list. |
| test_drive_failure_multi_drive_negative_case_luns | test_drive_failure.py | TestDriveFailure | 181 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_no_enc_fs | test_drive_failure.py | TestDriveFailure | 193 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_with_enc_fs | test_drive_failure.py | TestDriveFailure | 207 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_no_enc_obj | test_drive_failure.py | TestDriveFailure | 220 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_with_enc_obj | test_drive_failure.py | TestDriveFailure | 234 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_no_enc_fs | test_drive_failure.py | TestDriveFailure | 248 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_with_enc_fs | test_drive_failure.py | TestDriveFailure | 261 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_no_enc_obj | test_drive_failure.py | TestDriveFailure | 273 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_with_enc_obj | test_drive_failure.py | TestDriveFailure | 285 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_drive_failure_shipment.py | TestDriveFailureShipment | 95 | Defined test function; referenced by at least one suite list. |
| test_power_failure | test_drive_failure_shipment.py | TestDriveFailureShipment | 99 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_no_enc_fs | test_drive_failure_shipment.py | TestDriveFailureShipment | 104 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_with_enc_fs | test_drive_failure_shipment.py | TestDriveFailureShipment | 118 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_no_enc_obj | test_drive_failure_shipment.py | TestDriveFailureShipment | 131 | Defined test function; referenced by at least one suite list. |
| test_power_failure_dataprotection_1_with_enc_obj | test_drive_failure_shipment.py | TestDriveFailureShipment | 145 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_no_enc_fs | test_drive_failure_shipment.py | TestDriveFailureShipment | 159 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_with_enc_fs | test_drive_failure_shipment.py | TestDriveFailureShipment | 172 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_no_enc_obj | test_drive_failure_shipment.py | TestDriveFailureShipment | 185 | Defined test function; referenced by at least one suite list. |
| test_power_failure_auto_mount_dataprotection_1_with_enc_obj | test_drive_failure_shipment.py | TestDriveFailureShipment | 197 | Defined test function; referenced by at least one suite list. |
| test_bcpftp_push_directory | test_ftp.py | BcpTest | 77 | Defined test function; referenced by at least one suite list. |
| test_bcpftp_push_file | test_ftp.py | BcpTest | 88 | Defined test function; referenced by at least one suite list. |
| test_bcpftp_push_directory_with_space_in_src | test_ftp.py | BcpTest | 101 | Defined test function; referenced by at least one suite list. |
| test_bcpftp_push_file_with_space_in_src | test_ftp.py | BcpTest | 113 | Defined test function; referenced by at least one suite list. |
| test_bcpftp_push_directory_with_space_in_dst | test_ftp.py | BcpTest | 124 | Defined test function; referenced by at least one suite list. |
| test_bcpftp_push_delete_directory | test_ftp.py | BcpTest | 137 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_hostname.py | HostNameTest | 60 | Defined test function; referenced by at least one suite list. |
| test_hostname_change | test_hostname.py | HostNameTest | 64 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_install.py | InstallTest | 89 | Defined test function; referenced by at least one suite list. |
| test_install_packages | test_install.py | InstallTest | 93 | Defined test function; referenced by at least one suite list. |
| test_uninstall_packages | test_install.py | InstallTest | 97 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_kms.py | KmsTest | 109 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_with_aws_key | test_kms.py | KmsTest | 113 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_with_luns_with_kms | test_kms.py | KmsTest | 117 | Defined test function; referenced by at least one suite list. |
| test_format_failure_without_aws_key | test_kms.py | KmsTest | 122 | Defined test function; referenced by at least one suite list. |
| test_format_failure_due_to_miscarriage_of_key_in_cloud | test_kms.py | KmsTest | 125 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_with_aws_key | test_kms.py | KmsTest | 128 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_uploading_aws_key_manually | test_kms.py | KmsTest | 135 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_without_aws_key | test_kms.py | KmsTest | 138 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_uploading_non_aws_key | test_kms.py | KmsTest | 141 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_while_aws_key_deleted_in_cloud | test_kms.py | KmsTest | 144 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_while_aws_key_lost_in_cloud | test_kms.py | KmsTest | 147 | Defined test function; referenced by at least one suite list. |
| test_auto_mount_with_aws_key | test_kms.py | KmsTest | 151 | Defined test function; referenced by at least one suite list. |
| test_auto_mount_failure_without_aws_key | test_kms.py | KmsTest | 154 | Defined test function; referenced by at least one suite list. |
| test_auto_mount_uploading_aws_key_manually | test_kms.py | KmsTest | 157 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_uploading_other_kms_key_manually | test_kms.py | KmsTest | 160 | Defined test function; referenced by at least one suite list. |
| test_key_mapping_deleted_and_key_deleted_from_cloud_post_bryck_erase | test_kms.py | KmsTest | 163 | Defined test function; referenced by at least one suite list. |
| test_aws_cloud_generated_key_is_256_bit | test_kms.py | KmsTest | 167 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_with_aws_key_web | test_kms.py | KmsTest | 172 | Defined test function; referenced by at least one suite list. |
| test_format_failure_without_aws_key_web | test_kms.py | KmsTest | 181 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_with_aws_key_web | test_kms.py | KmsTest | 190 | Defined test function; referenced by at least one suite list. |
| test_mount_bryck_uploading_aws_key_manually_web | test_kms.py | KmsTest | 199 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_without_aws_key_web | test_kms.py | KmsTest | 209 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_uploading_non_aws_key_web | test_kms.py | KmsTest | 218 | Defined test function; referenced by at least one suite list. |
| test_format_failure_due_to_misconfiguration_of_aws_web | test_kms.py | KmsTest | 227 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_longevity_performance.py | LongevityPerformanceTest | 75 | Defined test function; referenced by at least one suite list. |
| test_longevity_performance | test_longevity_performance.py | LongevityPerformanceTest | 79 | Defined test function; referenced by at least one suite list. |
| test_extended_longevity_performance | test_longevity_performance.py | LongevityPerformanceTest | 88 | Defined test function; referenced by at least one suite list. |
| test_extended_longevity_performance_delete_at_once | test_longevity_performance.py | LongevityPerformanceTest | 98 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_mobility.py | MobilityTest | 122 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_dataprotection_0 | test_mobility.py | MobilityTest | 126 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_dataprotection_1 | test_mobility.py | MobilityTest | 131 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_dataprotection_2 | test_mobility.py | MobilityTest | 135 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_dataprotection_0_with_enc | test_mobility.py | MobilityTest | 139 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_dataprotection_1_with_enc | test_mobility.py | MobilityTest | 143 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_dataprotection_2_with_enc | test_mobility.py | MobilityTest | 148 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_encryption_corruption_one_drive | test_mobility.py | MobilityTest | 152 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_encryption_corruption_two_drive | test_mobility.py | MobilityTest | 158 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_encryption_corruption_multi_drive | test_mobility.py | MobilityTest | 164 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_partition_corruption_with_enc_one_partition | test_mobility.py | MobilityTest | 170 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_partition_corruption_with_enc_two_partition | test_mobility.py | MobilityTest | 181 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_partition_corruption_with_enc_multi_partition | test_mobility.py | MobilityTest | 192 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_partition_corruption_without_enc_one_partition | test_mobility.py | MobilityTest | 203 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_partition_corruption_without_enc_two_partition | test_mobility.py | MobilityTest | 214 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_partition_corruption_without_enc_multi_partition | test_mobility.py | MobilityTest | 225 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_drive_failure_one_drive | test_mobility.py | MobilityTest | 236 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_drive_failure_multi_drive | test_mobility.py | MobilityTest | 246 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_data_protection_io_failure | test_mobility.py | MobilityTest | 257 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_data_protection_checksum_failure | test_mobility.py | MobilityTest | 267 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_aws_kms | test_mobility.py | MobilityTest | 277 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_mounting_with_aws_key_uploading_manually | test_mobility.py | MobilityTest | 286 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_mount_failure_not_having_aws_connection | test_mobility.py | MobilityTest | 295 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_mount_failure_uploading_different_key | test_mobility.py | MobilityTest | 304 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_mount_failure_no_key_in_cloud_mount_success_uploading_manually | test_mobility.py | MobilityTest | 313 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_mount_failure_key_lost_in_cloud | test_mobility.py | MobilityTest | 322 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_automount_using_aws_key | test_mobility.py | MobilityTest | 331 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_automount_failure_not_having_aws_connection | test_mobility.py | MobilityTest | 340 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_automount_uploading_aws_key_manually_during_mount | test_mobility.py | MobilityTest | 349 | Defined test function; referenced by at least one suite list. |
| test_multi_hop_mobility_with_enc | test_mobility.py | MobilityTest | 359 | Defined test function; referenced by at least one suite list. |
| test_multi_hop_mobility_without_enc | test_mobility.py | MobilityTest | 364 | Defined test function; referenced by at least one suite list. |
| test_bryck_mobility_with_luns | test_mobility.py | MobilityTest | 369 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_performance.py | PerformanceTest | 74 | Defined test function; referenced by at least one suite list. |
| test_local_performance | test_performance.py | PerformanceTest | 79 | Defined test function; referenced by at least one suite list. |
| test_nfs_performance | test_performance.py | PerformanceTest | 88 | Defined test function; referenced by at least one suite list. |
| test_local_performance_compression | test_performance.py | PerformanceTest | 103 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_raw_performance.py | RawPerformanceTest | 73 | Defined test function; referenced by at least one suite list. |
| test_raw_performance | test_raw_performance.py | RawPerformanceTest | 77 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_reboot.py | RebootTest | 110 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_0 | test_reboot.py | RebootTest | 114 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1 | test_reboot.py | RebootTest | 124 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_2 | test_reboot.py | RebootTest | 134 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_0_with_enc | test_reboot.py | RebootTest | 145 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_with_enc | test_reboot.py | RebootTest | 156 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_2_with_enc | test_reboot.py | RebootTest | 165 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_0_no_enc | test_reboot.py | RebootTest | 176 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_no_enc | test_reboot.py | RebootTest | 187 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_0_obj | test_reboot.py | RebootTest | 199 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_obj | test_reboot.py | RebootTest | 210 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_2_obj | test_reboot.py | RebootTest | 220 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_0_with_enc_obj | test_reboot.py | RebootTest | 230 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_with_enc_obj | test_reboot.py | RebootTest | 241 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_2_with_enc_obj | test_reboot.py | RebootTest | 251 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_0_no_enc_obj | test_reboot.py | RebootTest | 261 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_no_enc_obj | test_reboot.py | RebootTest | 271 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_0_luns | test_reboot.py | RebootTest | 283 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_luns | test_reboot.py | RebootTest | 293 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_2_luns | test_reboot.py | RebootTest | 303 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_0_with_enc_luns | test_reboot.py | RebootTest | 313 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_with_enc_luns | test_reboot.py | RebootTest | 323 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_2_with_enc_luns | test_reboot.py | RebootTest | 333 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_0_no_enc_luns | test_reboot.py | RebootTest | 343 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_no_enc_luns | test_reboot.py | RebootTest | 353 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_reboot_shipment.py | RebootTestShipment | 94 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1 | test_reboot_shipment.py | RebootTestShipment | 99 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_with_enc | test_reboot_shipment.py | RebootTestShipment | 111 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_no_enc | test_reboot_shipment.py | RebootTestShipment | 124 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_with_enc | test_reboot_shipment.py | RebootTestShipment | 136 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_obj | test_reboot_shipment.py | RebootTestShipment | 152 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_dataprotection_1_with_enc_obj | test_reboot_shipment.py | RebootTestShipment | 168 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_no_enc_obj | test_reboot_shipment.py | RebootTestShipment | 183 | Defined test function; referenced by at least one suite list. |
| test_system_reboot_auto_mount_dataprotection_1_with_enc_obj | test_reboot_shipment.py | RebootTestShipment | 195 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_stress.py | StressTest | 91 | Defined test function; referenced by at least one suite list. |
| test_system_stability_with_all_variants | test_stress.py | StressTest | 95 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_stress_shipment.py | StressTestShipment | 91 | Defined test function; referenced by at least one suite list. |
| test_system_stability_with_all_variants | test_stress_shipment.py | StressTestShipment | 95 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_tsutil.py | TsutilTest | 55 | Defined test function; referenced by at least one suite list. |
| test_tsutil_functions | test_tsutil.py | TsutilTest | 59 | Defined test function; referenced by at least one suite list. |
| test_build_upgrade | test_upgrade.py | UpgradeTest | 63 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_web.py | WebTest | 107 | Defined test function; referenced by at least one suite list. |
| test_ui_configure_all_variants | test_web.py | WebTest | 111 | Defined test function; referenced by at least one suite list. |
| test_ui_system_page_drive_serial_no_check | test_web.py | WebTest | 167 | Defined test function; referenced by at least one suite list. |
| test_ui_system_page_download_client_package | test_web.py | WebTest | 177 | Defined test function; referenced by at least one suite list. |
| test_ui_data_transfer_no_enc | test_web.py | WebTest | 188 | Defined test function; referenced by at least one suite list. |
| test_ui_data_transfer_with_enc | test_web.py | WebTest | 197 | Defined test function; referenced by at least one suite list. |
| test_ui_generate_bryck_report | test_web.py | WebTest | 207 | Defined test function; referenced by at least one suite list. |
| test_ui_network_configure | test_web.py | WebTest | 217 | Defined test function; referenced by at least one suite list. |
| test_ui_network_configure_using_dhcp | test_web.py | WebTest | 232 | Defined test function; referenced by at least one suite list. |
| test_dashboard_wizard | test_web.py | WebTest | 248 | Defined test function; referenced by at least one suite list. |
| test_ui_eject_with_hot_pluggability_true_with_enc | test_web.py | WebTest | 259 | Defined test function; referenced by at least one suite list. |
| test_ui_bryck_mount_with_hot_pluggable_eject | test_web.py | WebTest | 272 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_configure | test_web.py | WebTest | 284 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_transfer_upload | test_web.py | WebTest | 292 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_transfer_download | test_web.py | WebTest | 321 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_transfer_pause_resume | test_web.py | WebTest | 339 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_transfer_cancel | test_web.py | WebTest | 367 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_transfer_upload_obj | test_web.py | WebTest | 395 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_transfer_download_obj | test_web.py | WebTest | 421 | Defined test function; referenced by at least one suite list. |
| test_cloud_ui_deconfigure | test_web.py | WebTest | 440 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_web_shipment.py | WebTestShipment | 91 | Defined test function; referenced by at least one suite list. |
| test_ui_configure_all_variants | test_web_shipment.py | WebTestShipment | 95 | Defined test function; referenced by at least one suite list. |
| test_ui_network_configure | test_web_shipment.py | WebTestShipment | 147 | Defined test function; referenced by at least one suite list. |
| test_ui_network_configure_using_dhcp | test_web_shipment.py | WebTestShipment | 162 | Defined test function; referenced by at least one suite list. |
| test_bryck_check | test_zfs.py | ZFSTest | 92 | Defined test function; referenced by at least one suite list. |
| test_zfs_filestore | test_zfs.py | ZFSTest | 96 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount | tsutil_test.py | Tsutil | 270 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_invalid_key | tsutil_test.py | Tsutil | 282 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_non_exist_keyfile | tsutil_test.py | Tsutil | 294 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_no_mnt_directory | tsutil_test.py | Tsutil | 306 | Defined test function; referenced by at least one suite list. |
| test_mount_failure_induced | tsutil_test.py | Tsutil | 317 | Defined test function; not referenced by any detected suite list. |
| test_bryck_mount_partition_table_corrupt | tsutil_test.py | Tsutil | 324 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_partition_table_corrupt_except_1 | tsutil_test.py | Tsutil | 343 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_metadata_corrupt | tsutil_test.py | Tsutil | 363 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_metadata_corrupt_except_1 | tsutil_test.py | Tsutil | 384 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_enc_metadata_corrupt | tsutil_test.py | Tsutil | 406 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_enc_metadata_corrupt_except_1 | tsutil_test.py | Tsutil | 426 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_fs_metadata_corrupt | tsutil_test.py | Tsutil | 449 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_no_enc_fs_metadata_corrupt | tsutil_test.py | Tsutil | 469 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_write_files | tsutil_test.py | Tsutil | 490 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_files_checksum | tsutil_test.py | Tsutil | 504 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_stress | tsutil_test.py | Tsutil | 540 | Defined test function; not referenced by any detected suite list. |
| test_bryck_setkey_key_change | tsutil_test.py | Tsutil | 575 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_oldkey_invalid | tsutil_test.py | Tsutil | 594 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_newkey_invalid | tsutil_test.py | Tsutil | 605 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_no_keyfile | tsutil_test.py | Tsutil | 615 | Defined test function; referenced by at least one suite list. |
| test_bryck_setkey_stress | tsutil_test.py | Tsutil | 625 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_non_formatted_bryck | tsutil_test.py | Tsutil | 640 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_non_formatted_bryck_with_nvme | tsutil_test.py | Tsutil | 651 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_formatted_bryck | tsutil_test.py | Tsutil | 663 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_mounted_bryck | tsutil_test.py | Tsutil | 675 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_not_inserted | tsutil_test.py | Tsutil | 689 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_not_inserted_with_nvme | tsutil_test.py | Tsutil | 699 | Defined test function; referenced by at least one suite list. |
| test_bryck_info_stress | tsutil_test.py | Tsutil | 710 | Defined test function; not referenced by any detected suite list. |
| test_bryck_format_inserted_bryck | tsutil_test.py | Tsutil | 734 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_already_formatted | tsutil_test.py | Tsutil | 741 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_already_mounted | tsutil_test.py | Tsutil | 752 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_not_found | tsutil_test.py | Tsutil | 764 | Defined test function; referenced by at least one suite list. |
| test_format_invalid_key | tsutil_test.py | Tsutil | 774 | Defined test function; referenced by at least one suite list. |
| test_format_stress | tsutil_test.py | Tsutil | 784 | Defined test function; not referenced by any detected suite list. |
| test_bryck_eject | tsutil_test.py | Tsutil | 802 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_already_ejected | tsutil_test.py | Tsutil | 814 | Defined test function; referenced by at least one suite list. |
| test_bryck_eject_directory_use | tsutil_test.py | Tsutil | 833 | Defined test function; referenced by at least one suite list. |
| test_bryck_erase_mounted | tsutil_test.py | Tsutil | 894 | Defined test function; referenced by at least one suite list. |
| test_bryck_erase_unmounted | tsutil_test.py | Tsutil | 907 | Defined test function; referenced by at least one suite list. |
| test_break_mount_after_erase | tsutil_test.py | Tsutil | 919 | Defined test function; referenced by at least one suite list. |
| test_bryck_file_metadata | tsutil_test.py | Tsutil | 932 | Defined test function; referenced by at least one suite list. |
| test_bryck_drive_failure | tsutil_test.py | Tsutil | 968 | Defined test function; not referenced by any detected suite list. |
| test_bryck_drive_scenarios | tsutil_test.py | Tsutil | 1027 | Defined test function; referenced by at least one suite list. |
| test_bryck_pool_conflict | tsutil_test.py | Tsutil | 1121 | Defined test function; not referenced by any detected suite list. |
| test_bryck_pool_conflict_all | tsutil_test.py | Tsutil | 1171 | Defined test function; referenced by at least one suite list. |
| test_bryck_sanity_kms_configured | tsutil_test.py | Tsutil | 1260 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_kms_no_configured | tsutil_test.py | Tsutil | 1279 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_kms_no_configured | tsutil_test.py | Tsutil | 1298 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_kms_manual_configured | tsutil_test.py | Tsutil | 1326 | Defined test function; referenced by at least one suite list. |
| test_bryck_kms_configured_key_del | tsutil_test.py | Tsutil | 1357 | Defined test function; referenced by at least one suite list. |
| test_remove_bryck | tsutil_test.py | Tsutil | 1386 | Defined test function; referenced by at least one suite list. |
| test_remove_bryck_when_mounted | tsutil_test.py | Tsutil | 1404 | Defined test function; referenced by at least one suite list. |
| test_scan_bryck | tsutil_test.py | Tsutil | 1414 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_deduplication | tsutil_test.py | Tsutil | 1430 | Defined test function; referenced by at least one suite list. |
| test_format_bryck_compression | tsutil_test.py | Tsutil | 1441 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_object_enable | tsutil_test.py | Tsutil | 1452 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_object_enable | tsutil_test.py | Tsutil | 1467 | Defined test function; referenced by at least one suite list. |
| test_bryck_format_object_disable | tsutil_test.py | Tsutil | 1478 | Defined test function; referenced by at least one suite list. |
| test_bryck_mount_object_disable | tsutil_test.py | Tsutil | 1490 | Defined test function; referenced by at least one suite list. |
| test_create_bucket_enable | tsutil_test.py | Tsutil | 1503 | Defined test function; referenced by at least one suite list. |
| test_create_bucket_already_exist | tsutil_test.py | Tsutil | 1519 | Defined test function; referenced by at least one suite list. |
| test_delete_bucket | tsutil_test.py | Tsutil | 1525 | Defined test function; referenced by at least one suite list. |
| test_delete_bucket_not_exist | tsutil_test.py | Tsutil | 1535 | Defined test function; referenced by at least one suite list. |
| test_list_no_bucket_created | tsutil_test.py | Tsutil | 1541 | Defined test function; referenced by at least one suite list. |
| test_list_bucket | tsutil_test.py | Tsutil | 1555 | Defined test function; referenced by at least one suite list. |
| test_create_delete_list_keys | tsutil_test.py | Tsutil | 1567 | Defined test function; referenced by at least one suite list. |
| test_bryck_kms_multi_drive_failure | tsutil_test.py | Tsutil | 1580 | Defined test function; referenced by at least one suite list. |
| test_dashboard_wizard | web_store.py | WebStore | 1070 | Defined test function; referenced by at least one suite list. |

## 2. Test Suites (Grouped, Ordered)

| Suite File | Suite Path | Variable | Ordered Tests |
|---|---|---|---|
| bryckutil_test.py | bryckutil_test.py | tests | 1. test_bryck_format_inserted_bryck<br>2. test_bryck_format_already_formatted<br>3. test_bryck_format_already_mounted<br>4. test_format_bryck_not_found<br>5. test_format_invalid_key |
| bryckutil_test.py | bryckutil_test.py | tests | 1. test_bryck_format_inserted_bryck<br>2. test_bryck_format_already_formatted<br>3. test_bryck_format_already_mounted<br>4. test_format_bryck_not_found<br>5. test_format_invalid_key<br>6. test_bryck_mount<br>7. test_bryck_mount_invalid_key<br>8. test_bryck_mount_non_exist_keyfile<br>9. test_bryck_mount_no_mnt_directory<br>10. test_bryck_mount_write_files<br>11. test_bryck_mount_files_checksum<br>12. test_bryck_setkey_key_change<br>13. test_bryck_setkey_oldkey_invalid<br>14. test_bryck_setkey_newkey_invalid<br>15. test_bryck_setkey_no_keyfile<br>16. test_bryck_setkey_stress<br>17. test_bryck_eject<br>18. test_bryck_eject_already_ejected<br>19. test_bryck_eject_directory_use<br>20. test_bryck_eject_data_consistency<br>21. test_bryck_erase_mounted<br>22. test_bryck_info_non_formatted_bryck<br>23. test_bryck_info_non_formatted_bryck_with_nvme<br>24. test_bryck_info_formatted_bryck<br>25. test_bryck_info_mounted_bryck<br>26. test_bryck_info_not_inserted<br>27. test_bryck_info_not_inserted_with_nvme |
| bryckutil_test.py | bryckutil_test.py | tests | 1. test_bryck_info_non_formatted_bryck<br>2. test_bryck_info_non_formatted_bryck_with_nvme<br>3. test_bryck_info_formatted_bryck<br>4. test_bryck_info_mounted_bryck<br>5. test_bryck_info_not_inserted<br>6. test_bryck_info_not_inserted_with_nvme |
| bryckutil_test.py | bryckutil_test.py | tests | 1. test_bryck_mount<br>2. test_bryck_mount_invalid_key<br>3. test_bryck_mount_non_exist_keyfile<br>4. test_bryck_mount_no_mnt_directory<br>5. test_bryck_mount_write_files<br>6. test_bryck_mount_files_checksum |
| bryckutil_test.py | bryckutil_test.py | tests | 1. test_bryck_setkey_key_change<br>2. test_bryck_setkey_oldkey_invalid<br>3. test_bryck_setkey_newkey_invalid<br>4. test_bryck_setkey_no_keyfile |
| test_agylstor.py | test_agylstor.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_filestore_configure<br>4. test_filestore_nfs_mount<br>5. test_bryckcp_nfs_local_push_n_stream<br>6. test_bryckcp_nfs_local_pull_n_stream<br>7. test_bryckcp_nfs_local_copy_with_illegal_patterns<br>8. test_bryckcp_nfs_remote_push_n_stream<br>9. test_bryckcp_nfs_remote_pull_n_stream<br>10. test_bryckcp_rdma_nfs_remote_push_n_stream<br>11. test_bryckcp_rdma_nfs_remote_pull_n_stream<br>12. test_bryckcp_smb_remote_pull_1_stream<br>13. test_bryckcp_smb_remote_push_n_stream<br>14. test_bryckcp_smb_remote_pull_n_stream<br>15. test_bryckcp_rdma_smb_remote_push_n_stream<br>16. test_bryckcp_rdma_smb_remote_pull_n_stream<br>17. test_bryck_eject<br>18. test_bryck_mount<br>19. test_bryckcp_tcp_push_1_stream_n_rdwr<br>20. test_bryckcp_tcp_pull_1_stream_n_rdwr<br>21. test_bryckcp_tcp_push_n_stream_n_rdwr<br>22. test_bryckcp_tcp_pull_n_stream_n_rdwr<br>23. test_ftp_remote_push_n_stream<br>24. test_ftp_remote_pull_n_stream<br>25. test_error_bryckcp_nfs_push_crash<br>26. test_error_bryckcp_nfs_pull_crash<br>27. test_error_bryckcp_nfs_push_crash_segv<br>28. test_error_bryckcp_nfs_pull_crash_segv<br>29. test_error_bryckcp_nfs_push_access_source<br>30. test_error_bryckcp_nfs_push_access_dest<br>31. test_error_bryckcp_nfs_pull_access_source<br>32. test_error_bryckcp_nfs_pull_access_dest<br>33. test_error_bryckcp_tcp_push_access_source<br>34. test_error_bryckcp_tcp_push_access_dest<br>35. test_error_bryckcp_tcp_pull_access_source<br>36. test_error_bryckcp_tcp_pull_access_dest<br>37. test_configure_cloud_aws<br>38. test_configure_cloud_azure<br>39. test_configure_cloud_gcp<br>40. test_upload_single_stream_single_file_small_data_set_aws<br>41. test_download_single_stream_single_file_small_data_set_aws<br>42. test_upload_single_stream_single_file_small_data_set_gcp<br>43. test_download_single_stream_single_file_small_data_set_gcp<br>44. test_upload_single_stream_single_file_small_data_set_azure<br>45. test_download_single_stream_single_file_small_data_set_azure<br>46. test_upload_single_stream_single_file_small_object_set_aws<br>47. test_download_single_stream_single_file_small_object_set_aws<br>48. test_delete_cloud_configuraiton_aws<br>49. test_delete_cloud_configuraiton_azure<br>50. test_delete_cloud_configuraiton_gcp<br>51. test_filestore_nfs_umount<br>52. test_bryck_eject_once<br>53. test_filestore_reinit<br>54. test_configure_luns<br>55. test_mount_bryck_with_luns<br>56. test_configure_luns_with_N_volumes<br>57. test_bryck_eject_with_luns<br>58. test_filestore_reinit_with_luns<br>59. test_filestore_configure_no_enc_automount<br>60. test_bryck_eject_no_enc<br>61. test_mount_bryck_force<br>62. test_eject_bryck_force<br>63. test_filestore_reinit_final<br>64. test_bryck_report_start<br>65. test_bryck_report_check<br>66. test_to_configure_five_red_camera<br>67. test_bryckck_verify_bryck_fs<br>68. test_build_upgrade_ui |
| test_aibryck.py | test_aibryck.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_inferencing_one_specific_model<br>4. test_inferencing_one_model_N_times_parallely<br>5. test_run_inferencing_on_multiple_models_sequentially<br>6. test_run_inferencing_on_Multiple_models_N_times_parallely<br>7. test_run_inferencing_on_N_models_with_N_no_of_dataset_parallely<br>8. test_inferencing_one_model_with_100TB_data<br>9. test_inferencing_four__model_with_100TB_data<br>10. test_run_inferencing_streaming_data_one_model<br>11. test_run_inferencing_streaming_data_one_model_N_times_parallely<br>12. test_run_inferencing_streaming_data_on_muliple_models<br>13. test_run_inferencing_streaming_data_on_Multiple_models_N_times_parallely<br>14. test_run_inferencing_streaming_data_on_N_models_with_N_streaming_source_parallely |
| test_bcp.py | test_bcp.py | tests | 1. test_bcp<br>2. test_bryckcp_tcp_push_validate_exist_directory<br>3. test_bcp<br>4. test_bryckcp_tcp_push_validate_src_exist_directory<br>5. test_bcp<br>6. test_bryckcp_tcp_push_directory<br>7. test_bcp<br>8. test_bryckcp_tcp_push_file<br>9. test_bcp<br>10. test_bryckcp_tcp_push_directory_with_space_in_src<br>11. test_bcp<br>12. test_bryckcp_tcp_push_file_with_space_in_src<br>13. test_bcp<br>14. test_bryckcp_tcp_push_directory_with_space_in_dst<br>15. test_bcp<br>16. test_bryckcp_tcp_push_file_with_space_in_dst<br>17. test_bcp<br>18. test_bryckcp_tcp_push_directory_wrong_mnt_pnt<br>19. test_bcp<br>20. test_bryckcp_tcp_push_directory_invalid_src_path<br>21. test_bcp<br>22. test_bryckcp_tcp_push_directory_invalid_dst_path<br>23. test_bcp<br>24. test_bryckcp_tcp_push_validate_directory<br>25. test_bcp<br>26. test_bcp<br>27. test_bryckcp_tcp_pull_directory<br>28. test_bcp<br>29. test_bryckcp_tcp_pull_file<br>30. test_bcp<br>31. test_bryckcp_tcp_pull_directory_with_space_in_src<br>32. test_bcp<br>33. test_bryckcp_tcp_pull_directory_with_space_in_dst<br>34. test_bcp<br>35. test_bryckcp_tcp_pull_directory_invalid_src_path<br>36. test_bcp<br>37. test_bryckcp_tcp_pull_directory_invalid_dst_path<br>38. test_bcp<br>39. test_bryckcp_tcp_pull_delete_directory |
| test_bryck_stream.py | test_bryck_stream.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_to_configure_one_red_camera<br>4. test_to_list_out_all_red_cameras<br>5. test_to_deconfigure_specific_red_camera<br>6. test_to_configure_five_red_camera<br>7. test_to_configure_ten_red_camera<br>8. test_to_check_after_reboot_red_camera_resumes_streaming<br>9. test_to_configure_st21_video_kernal<br>10. test_to_configure_st21_audio_kernal<br>11. test_to_configure_st21_video_kernal_reboot<br>12. test_to_configure_st21_audio_kernal_reboot<br>13. test_to_configure_st21_video_dpdk<br>14. test_to_configure_st21_audio_dpdk<br>15. test_to_configure_st21_video_dpdk_reboot<br>16. test_to_configure_st21_audio_dpdk_reboot |
| test_bryckcp.py | test_bryckcp.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_bryckcp_with_2gb_files<br>4. test_bryckcp_with_64mb_files<br>5. test_bryckcp_with_64mb_files_multi_level<br>6. test_bryckcp_with_2gb_files_crash_transfer<br>7. test_bryckcp_with_64mb_files_crash_transfer<br>8. test_bryckcp_with_64mb_files_multi_level_crash_transfer<br>9. test_bryckcp_with_small_files_where_dest_contains_files<br>10. test_bryckcp_with_some_duplicate_files_of_the_dest<br>11. test_bryckcp_tcp_pull_push_transfer<br>12. test_bryckcp_local_transfer |
| test_cleanup.py | test_cleanup.py | test_order | 1. test_order<br>2. test_bryck_check |
| test_cloud_config.py | test_cloud_config.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_miss_configure_cloud_wrong_user_aws<br>4. test_miss_configure_cloud_wrong_user_azure<br>5. test_miss_configure_cloud_wrong_keyid_aws<br>6. test_miss_configure_cloud_wrong_keyid_azure<br>7. test_miss_configure_cloud_wrong_user_keyid_aws<br>8. test_miss_configure_cloud_wrong_user_keyid_azure<br>9. test_miss_configure_cloud_wrong_cloudtype_aws<br>10. test_miss_configure_cloud_wrong_cloudtype_azure<br>11. test_configure_cloud_aws<br>12. test_configure_cloud_azure<br>13. test_configure_cloud_gcp<br>14. test_list_out_all_cloud_configuration<br>15. test_to_store_cloud_credentails_securely<br>16. test_delete_cloud_configuraiton_aws<br>17. test_delete_cloud_configuraiton_azure<br>18. test_delete_cloud_configuraiton_gcp<br>19. test_modify_cloud_configuration |
| test_cloud_crash.py | test_cloud_crash.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_configure_the_bryck<br>7. test_upload_single_stream_single_file_small_data_set_reboot<br>8. test_download_single_stream_single_file_small_data_set_reboot<br>9. test_upload_single_stream_directory_small_data_set_reboot<br>10. test_download_single_stream_directory_small_data_set_reboot<br>11. test_upload_single_stream_directory_with_N_level_small_data_set_reboot<br>12. test_download_single_stream_directory_with_N_level_small_data_set_reboot<br>13. test_upload_single_stream_single_file_large_data_set_reboot<br>14. test_download_single_stream_single_file_large_data_set_reboot<br>15. test_upload_single_stream_directory_large_data_set_reboot<br>16. test_download_single_stream_directory_large_data_set_reboot<br>17. test_upload_single_stream_directory_with_N_level_large_data_set_reboot<br>18. test_download_single_stream_directory_with_N_level_large_data_set_reboot<br>19. test_upload_single_stream_directory_with_billions_file_terabyte_data_reboot<br>20. test_download_single_stream_directory_with_billions_file_terabyte_data_reboot<br>21. test_upload_single_stream_directory_small_object_set_reboot<br>22. test_download_single_stream_directory_small_object_set_reboot<br>23. test_upload_single_stream_directory_with_N_level_small_object_set_reboot<br>24. test_download_single_stream_directory_with_N_level_small_object_set_reboot<br>25. test_upload_single_stream_single_file_large_object_set_reboot<br>26. test_download_single_stream_single_file_large_object_set_reboot<br>27. test_upload_single_stream_directory_large_object_set_reboot<br>28. test_download_single_stream_directory_large_object_set_reboot<br>29. test_upload_single_stream_directory_with_N_level_large_object_set_reboot<br>30. test_download_single_stream_directory_with_N_level_large_object_set_reboot<br>31. test_upload_single_stream_directory_with_billions_file_terabyte_object_set_reboot<br>32. test_download_single_stream_directory_with_billions_file_terabyte_object_set_reboot<br>33. test_upload_single_stream_single_file_small_data_set_app_crash<br>34. test_download_single_stream_single_file_small_data_set_app_crash<br>35. test_upload_single_stream_directory_small_data_set_app_crash<br>36. test_download_single_stream_directory_small_data_set_app_crash<br>37. test_upload_single_stream_directory_with_N_level_small_data_set_app_crash<br>38. test_download_single_stream_directory_with_N_level_small_data_set_app_crash<br>39. test_upload_single_stream_single_file_large_data_set_app_crash<br>40. test_download_single_stream_single_file_large_data_set_app_crash<br>41. test_upload_single_stream_directory_large_data_set_app_crash<br>42. test_download_single_stream_directory_large_data_set_app_crash<br>43. test_upload_single_stream_directory_with_N_level_large_data_set_app_crash<br>44. test_download_single_stream_directory_with_N_level_large_data_set_app_crash<br>45. test_upload_single_stream_directory_with_billions_file_terabyte_data_app_crash<br>46. test_download_single_stream_directory_with_billions_file_terabyte_data_app_crash<br>47. test_upload_single_stream_directory_small_object_set_app_crash<br>48. test_download_single_stream_directory_small_object_set_app_crash<br>49. test_upload_single_stream_directory_small_object_set_app_crash<br>50. test_download_single_stream_directory_small_object_set_app_crash<br>51. test_upload_single_stream_directory_with_N_level_small_object_set_app_crash<br>52. test_download_single_stream_directory_with_N_level_small_object_set_app_crash<br>53. test_upload_single_stream_single_file_large_object_set_app_crash<br>54. test_download_single_stream_single_file_large_object_set_app_crash<br>55. test_upload_single_stream_directory_large_object_set_app_crash<br>56. test_download_single_stream_directory_large_object_set_app_crash<br>57. test_upload_single_stream_directory_with_N_level_large_object_set_app_crash<br>58. test_download_single_stream_directory_with_N_level_large_object_set_app_crash<br>59. test_upload_single_stream_directory_with_billions_file_terabyte_object_set_app_crash<br>60. test_download_single_stream_directory_with_billions_file_terabyte_object_set_app_crash<br>61. test_eject_the_bryck<br>62. test_delete_cloud_configuraiton_aws<br>63. test_delete_cloud_configuraiton_azure<br>64. test_delete_cloud_configuraiton_gcp |
| test_cloud_mobility.py | test_cloud_mobility.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_upload_small_data_set_mobility<br>7. test_download_small_data_set_mobility<br>8. test_upload_large_data_set_mobility<br>9. test_download_large_data_set_mobility<br>10. test_upload_small_object_set_mobility<br>11. test_download_small_object_set_mobility<br>12. test_upload_large_object_set_mobility<br>13. test_download_large_object_set_mobility<br>14. test_delete_cloud_configuraiton_aws<br>15. test_delete_cloud_configuraiton_azure<br>16. test_delete_cloud_configuraiton_gcp |
| test_cloud_modify.py | test_cloud_modify.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_upload_single_stream_single_file_small_data_set_pause_modify<br>7. test_download_single_stream_single_file_small_data_set_pause_modify<br>8. test_upload_single_stream_directory_small_data_set_pause_modify<br>9. test_download_single_stream_directory_small_data_set_pause_modify<br>10. test_upload_single_stream_directory_with_N_level_small_data_set_pause_modify<br>11. test_download_single_stream_directory_with_N_level_small_data_set_pause_modify<br>12. test_upload_single_stream_single_file_large_data_set_pause_modify<br>13. test_download_single_stream_single_file_large_data_set_pause_modify<br>14. test_upload_single_stream_directory_large_data_set_pause_modify<br>15. test_download_single_stream_directory_large_data_set_pause_modify<br>16. test_upload_single_stream_directory_with_N_level_large_data_set_pause_modify<br>17. test_download_single_stream_directory_with_N_level_large_data_set_pause_modify<br>18. test_upload_single_stream_directory_with_billions_file_terabyte_data_pause_modify<br>19. test_download_single_stream_directory_with_billions_file_terabyte_data_pause_modify<br>20. test_upload_single_stream_single_file_small_object_set_pause_modify<br>21. test_download_single_stream_single_file_small_object_set_pause_modify<br>22. test_upload_single_stream_directory_small_object_set_pause_modify<br>23. test_download_single_stream_directory_small_object_set_pause_modify<br>24. test_upload_single_stream_directory_with_N_level_small_object_set_pause_modify<br>25. test_download_single_stream_directory_with_N_level_small_object_set_pause_modify<br>26. test_upload_single_stream_single_file_large_object_set_pause_modify<br>27. test_download_single_stream_single_file_large_object_set_pause_modify<br>28. test_upload_single_stream_directory_large_object_set_pause_modify<br>29. test_download_single_stream_directory_large_object_set_pause_modify<br>30. test_upload_single_stream_directory_with_N_level_large_object_set_pause_modify<br>31. test_download_single_stream_directory_with_N_level_large_object_set_pause_modify<br>32. test_upload_single_stream_directory_with_billions_file_terabyte_object_pause_modify<br>33. test_download_single_stream_directory_with_billions_file_terabyte_object_pause_modify<br>34. test_delete_cloud_configuraiton_aws<br>35. test_delete_cloud_configuraiton_azure<br>36. test_delete_cloud_configuraiton_gcp |
| test_cloud_pause_resume.py | test_cloud_pause_resume.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_configure_the_bryck<br>7. test_upload_single_stream_single_file_small_data_set_pause<br>8. test_download_single_stream_single_file_small_data_set_pause<br>9. test_upload_single_stream_directory_small_data_set_pause<br>10. test_download_single_stream_directory_small_data_set_pause<br>11. test_upload_single_stream_directory_with_N_level_small_data_set_pause<br>12. test_download_single_stream_directory_with_N_level_small_data_set_pause<br>13. test_upload_single_stream_single_file_large_data_set_pause<br>14. test_download_single_stream_single_file_large_data_set_pause<br>15. test_upload_single_stream_directory_large_data_set_pause<br>16. test_download_single_stream_directory_large_data_set_pause<br>17. test_upload_single_stream_directory_with_N_level_large_data_set_pause<br>18. test_download_single_stream_directory_with_N_level_large_data_set_pause<br>19. test_upload_single_stream_directory_with_billions_file_terabyte_data_pause<br>20. test_download_single_stream_directory_with_billions_file_terabyte_data_pause<br>21. test_upload_single_stream_single_file_small_object_set_pause<br>22. test_download_single_stream_single_file_small_object_set_pause<br>23. test_upload_single_stream_directory_small_object_set_pause<br>24. test_download_single_stream_directory_small_object_set_pause<br>25. test_upload_single_stream_directory_with_N_level_small_object_set_pause<br>26. test_download_single_stream_directory_with_N_level_small_object_set_pause<br>27. test_upload_single_stream_single_file_large_object_set_pause<br>28. test_download_single_stream_single_file_large_object_set_pause<br>29. test_upload_single_stream_directory_large_object_set_pause<br>30. test_download_single_stream_directory_large_object_set_pause<br>31. test_upload_single_stream_directory_with_N_level_large_object_set_pause<br>32. test_download_single_stream_directory_with_N_level_large_object_set_pause<br>33. test_upload_single_stream_directory_with_billions_file_terabyte_object_pause<br>34. test_download_single_stream_directory_with_billions_file_terabyte_object_pause<br>35. test_eject_the_bryck<br>36. test_delete_cloud_configuraiton_aws<br>37. test_delete_cloud_configuraiton_azure<br>38. test_delete_cloud_configuraiton_gcp |
| test_cloud_transfer.py | test_cloud_transfer.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_configure_the_bryck<br>7. test_upload_single_stream_single_file_small_data_set<br>8. test_download_single_stream_single_file_small_data_set<br>9. test_upload_single_stream_directory_small_data_set<br>10. test_download_single_stream_directory_small_data_set<br>11. test_upload_single_stream_directory_with_N_level_small_data_set<br>12. test_download_single_stream_directory_with_N_level_small_data_set<br>13. test_upload_single_stream_single_file_large_data_set<br>14. test_download_single_stream_single_file_large_data_set<br>15. test_upload_single_stream_directory_large_data_set<br>16. test_download_single_stream_directory_large_data_set<br>17. test_upload_single_stream_directory_with_N_level_large_data_set<br>18. test_download_single_stream_directory_with_N_level_large_data_set<br>19. test_upload_single_stream_single_file_small_data_set_failed_validation<br>20. test_download_single_stream_single_file_small_data_set_failed_validation<br>21. test_upload_single_stream_directory_small_data_set_failed_validation<br>22. test_download_single_stream_directory_small_data_set_failed_validation<br>23. test_upload_single_stream_directory_with_N_level_small_data_set_failed_validation<br>24. test_download_single_stream_directory_with_N_level_small_data_set_failed_validation<br>25. test_upload_single_stream_single_file_large_data_set_failed_validation<br>26. test_download_single_stream_single_file_large_data_set_failed_validation<br>27. test_upload_single_stream_directory_large_data_set_failed_validation<br>28. test_download_single_stream_directory_large_data_set_failed_validation<br>29. test_upload_single_stream_directory_with_N_level_large_data_set_failed_validation<br>30. test_download_single_stream_directory_with_N_level_large_data_set_failed_validation<br>31. test_upload_single_stream_single_file_small_object_set<br>32. test_download_single_stream_single_file_small_object_set<br>33. test_upload_single_stream_directory_small_object_set<br>34. test_download_single_stream_directory_small_object_set<br>35. test_upload_single_stream_directory_with_N_level_small_object_set<br>36. test_download_single_stream_directory_with_N_level_small_object_set<br>37. test_upload_single_stream_single_file_large_object_set<br>38. test_download_single_stream_single_file_large_object_set<br>39. test_upload_single_stream_directory_large_object_set<br>40. test_download_single_stream_directory_large_object_set<br>41. test_upload_single_stream_directory_with_N_level_large_object_set<br>42. test_download_single_stream_directory_with_N_level_large_object_set<br>43. test_upload_single_stream_directory_with_billions_file_terabyte_object<br>44. test_download_single_stream_directory_with_billions_file_terabyte_object<br>45. test_eject_the_bryck<br>46. test_upload_multi_stream_single_file_small_object_set<br>47. test_download_multi_stream_single_file_small_object_set<br>48. test_upload_multi_stream_single_file_small_data_set<br>49. test_download_multi_stream_single_file_small_data_set<br>50. test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_upload<br>51. test_to_check_transfer_can_not_be_done_if_cloud_not_configured_upload<br>52. test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_upload<br>53. test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_download<br>54. test_to_check_if_user_invoke_duplicate_transfer_upload<br>55. test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_download<br>56. test_to_check_transfer_can_not_be_done_if_cloud_not_configured_download<br>57. test_to_check_if_user_invoke_duplicate_transfer_download<br>58. test_to_cancel_ongoing_transfer<br>59. test_to_reinitiate_previously_cancelled_transfer<br>60. test_to_pause_the_transfer_and_delete_the_data_src<br>61. test_to_pause_the_transfer_delete_cloud_configuration<br>62. test_to_submit_N_number_of_transfers<br>63. test_to_specify_N_number_of_live_parallel_transfers<br>64. test_to_track_the_progress_of_one_transfer<br>65. test_to_get_all_the_transfers_details_for_specific_transfer_state<br>66. test_delete_cloud_configuraiton_aws<br>67. test_delete_cloud_configuraiton_azure<br>68. test_delete_cloud_configuraiton_gcp |
| test_cloud_transfer_shipment.py | test_cloud_transfer_shipment.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_upload_single_stream_single_file_small_data_set<br>7. test_download_single_stream_single_file_small_data_set<br>8. test_upload_single_stream_directory_small_data_set<br>9. test_download_single_stream_directory_small_data_set<br>10. test_upload_single_stream_single_file_small_object_set<br>11. test_download_single_stream_single_file_small_object_set<br>12. test_upload_single_stream_directory_small_object_set<br>13. test_download_single_stream_directory_small_object_set<br>14. test_delete_cloud_configuraiton_aws<br>15. test_delete_cloud_configuraiton_azure<br>16. test_delete_cloud_configuraiton_gcp |
| test_config.py | test_config.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_filestore_with_enc_dp_IO_DS<br>4. test_remote_object_transfer<br>5. test_eject_with_hot_pluggability_true_with_enc<br>6. test_eject_with_hot_pluggability_true_without_enc<br>7. test_bryck_mount_with_hot_pluggable_eject<br>8. test_data_integrity_with_hot_pluggable_eject<br>9. test_hot_pluggability_with_skip_drives<br>10. test_dedup_storage_efficiency<br>11. test_dedup_delete_directory<br>12. test_dedup_measure_performance<br>13. test_dedup_transfer_non_duplicate_data<br>14. test_dedup_transfer_duplicate_data<br>15. test_dedup_erase_bryck<br>16. test_dedup_mount_bryck<br>17. test_compresion_storage_efficiency<br>18. test_compression_transfer_non_compressible_data<br>19. test_compression_erase_bryck<br>20. test_compression_mount_bryck<br>21. test_configure_email_sender<br>22. test_list_email_sender<br>23. test_add_alert_user<br>24. test_deconfigure_email_sender |
| test_config_shipment.py | test_config_shipment.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_filestore_with_enc_dp_IO_DS<br>4. test_remote_object_transfer |
| test_data_corrution.py | test_data_corrution.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_encryption_corruption_one_drive<br>4. test_encryption_corruption_two_drive<br>5. test_encryption_corruption_multi_drive<br>6. test_partition_corruption_with_enc_one_partition<br>7. test_partition_corruption_with_enc_two_partition<br>8. test_partition_corruption_with_enc_multi_partition<br>9. test_partition_corruption_without_enc_one_partition<br>10. test_partition_corruption_without_enc_two_partition<br>11. test_partition_corruption_without_enc_multi_partition<br>12. test_encryption_corruption_one_drive_luns<br>13. test_encryption_corruption_two_drive_luns<br>14. test_encryption_corruption_multi_drive_luns<br>15. test_partition_corruption_with_enc_one_partition_luns<br>16. test_partition_corruption_with_enc_two_partition_luns<br>17. test_partition_corruption_with_enc_multi_partition_luns<br>18. test_partition_corruption_without_enc_one_partition_luns<br>19. test_partition_corruption_without_enc_two_partition_luns<br>20. test_partition_corruption_without_enc_multi_partition_luns<br>21. test_data_protection_io_failure<br>22. test_data_protection_checksum_failure |
| test_data_dart.py | test_data_dart.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_configure_cloud_aws<br>4. test_configure_cloud_azure<br>5. test_configure_cloud_gcp<br>6. test_verify_bryck_fs<br>7. test_verify_bryck_object<br>8. test_verify_cloud_transfer_fs<br>9. test_verify_cloud_transfer_object<br>10. test_verify_bryck_fs_missing_files<br>11. test_verify_bryck_object_missing_files<br>12. test_verify_cloud_down_missing_files<br>13. test_verify_cloud_down_missing_object<br>14. test_verify_bryck_fs_corrupted_files<br>15. test_verify_bryck_object_corrupted_files<br>16. test_delete_cloud_configuraiton_aws<br>17. test_delete_cloud_configuraiton_azure<br>18. test_delete_cloud_configuraiton_gcp |
| test_data_dart_admin.py | test_data_dart_admin.py | test_order | 1. test_order<br>2. test_to_create_admin<br>3. test_to_login_to_admin_space<br>4. test_to_update_contact_details<br>5. test_to_get_admin_details<br>6. test_to_create_a_shipping_center<br>7. test_to_get_details_of_a_shipping_center<br>8. test_to_update_the_details_of_a_shipping_center<br>9. test_to_activate_a_shipping_center<br>10. test_to_deactivate_a_shipping_center<br>11. test_to_get_the_list_of_all_shipping_center_of_a_zone<br>12. test_to_search_for_a_shipping_center<br>13. test_to_get_details_of_all_orders_of_a_shipping_center<br>14. test_to_get_details_of_all_subscriptions_of_a_shipping_center<br>15. test_to_get_details_of_all_infra_engg_of_a_shipping_center<br>16. test_to_get_details_of_available_hardwares_of_a_shipping_center<br>17. test_to_create_a_cloud_end_point<br>18. test_to_update_the_details_of_a_cloud_end_point<br>19. test_to_deactivate_a_cloud_end_point<br>20. test_to_activate_a_cloud_end_point<br>21. test_to_get_details_of_a_cloud_end_point<br>22. test_to_get_the_list_of_all_cloud_end_point_of_a_zone<br>23. test_to_search_for_a_cloud_end_point<br>24. test_to_get_details_of_all_orders_of_a_cloud_end_point<br>25. test_to_get_details_of_all_subscriptions_of_a_cloud_end_point<br>26. test_to_get_details_of_all_infra_engg_of_a_cloud_end_point<br>27. test_to_add_clouds_to_a_cloud_end_point<br>28. test_to_get_public_clouds_of_a_cloud_point<br>29. test_to_create_an_infra_engg<br>30. test_to_update_the_details_of_an_infra_engg<br>31. test_to_deactivate_an_infra_engg<br>32. test_to_activate_an_infra_engg<br>33. test_to_get_an_infra_engg_by_id<br>34. test_to_get_an_infra_engg_by_mail_id<br>35. test_to_list_out_all_infra_engg_of_a_zone<br>36. test_to_get_details_of_all_orders_of_an_infra_engg<br>37. test_to_get_details_of_all_subscriptions_of_an_infra_engg<br>38. test_to_assign_an_infra_engg_to_a_shipping_center<br>39. test_to_unassign_an_infra_engg_to_a_shipping_center<br>40. test_to_assign_an_infra_engg_to_a_cloud_end_point<br>41. test_to_unassign_an_infra_engg_to_a_cloud_end_point<br>42. test_to_get_shipping_center_of_an_infra_engg<br>43. test_to_get_cloud_end_point_of_an_infra_engg<br>44. test_to_get_details_of_a_customer_by_uuid<br>45. test_to_get_details_of_a_customer_by_mail_id<br>46. test_to_list_out_all_the_customer<br>47. test_to_search_for_a_customer<br>48. test_to_get_orders_of_a_customer<br>49. test_to_get_subscriptions_of_a_customer<br>50. test_to_deactivate_of_a_customer<br>51. test_to_remove_a_customer |
| test_data_dart_customer.py | test_data_dart_customer.py | test_order | 1. test_order<br>2. test_to_create_a_customer<br>3. test_to_login_to_customer_space<br>4. test_to_get_customer_by_uid<br>5. test_to_get_customer_by_email<br>6. test_to_create_an_order<br>7. test_to_cancel_an_order<br>8. test_to_get_order_by_uid<br>9. test_to_get_hardwares_of_order<br>10. test_to_get_orders_of_a_customer<br>11. test_to_update_timeline_of_order<br>12. test_to_get_timeline_of_order<br>13. test_to_create_a_subscription<br>14. test_to_get_subscription_by_uid<br>15. test_to_get_hardwares_of_subscription<br>16. test_to_get_subscriptions_of_a_customer<br>17. test_to_update_timeline_of_subscription<br>18. test_to_get_timeline_of_subscription<br>19. test_to_cancel_a_subscription<br>20. test_to_assign_source_contact_to_order<br>21. test_to_unassign_source_contact_to_order<br>22. test_to_assign_destinaiton_contact_to_order<br>23. test_to_unassign_destication_contact_to_order<br>24. test_to_assign_source_contact_to_subscription<br>25. test_to_unassign_source_contact_from_subscription |
| test_data_dart_infraengg.py | test_data_dart_infraengg.py | test_order | 1. test_order<br>2. test_to_login_to_infra_engg_space<br>3. test_to_update_profile_details<br>4. test_to_get_infra_engg_by_uid<br>5. test_to_get_infra_engg_by_email<br>6. test_to_get_all_infra_engg_of_a_zone<br>7. test_to_add_bryck<br>8. test_to_add_bryck_ai<br>9. test_to_add_bryck_tray<br>10. test_to_add_server<br>11. test_to_get_hardware_by_uid<br>12. test_to_activate_hardware_by_uid<br>13. test_to_deactivate_hardware_by_uid<br>14. test_to_get_details_of_shipping_center_by_uid<br>15. test_to_get_the_list_of_shipping_centers_by_zone<br>16. test_to_search_a_shipping_center_by_name<br>17. test_to_get_details_of_cloud_end_point_by_uid<br>18. test_to_get_the_list_of_cloud_end_point_by_zone<br>19. test_to_search_a_cloud_end_point_by_name<br>20. test_to_get_details_of_customer_by_mail<br>21. test_to_get_the_list_of_customers_by_zone<br>22. test_to_search_a_customer_by_name<br>23. test_to_get_order_by_uid<br>24. test_to_get_all_orders_of_a_zone<br>25. test_to_change_location_of_order<br>26. test_to_change_internal_status_of_order<br>27. test_to_change_overall_status_of_order<br>28. test_to_assign_hardware_to_order<br>29. test_to_unassign_hardware_to_order<br>30. test_to_assign_source_shipping_center_to_order<br>31. test_to_assign_destination_shipping_center_to_order<br>32. test_to_assign_engg_to_source_shipping_center_to_order<br>33. test_to_assign_engg_to_destinaiton_shipping_center_to_order<br>34. test_to_unassign_source_shipping_center_to_order<br>35. test_to_unassign_destination_shipping_center_to_order<br>36. test_to_unassign_engg_to_source_shipping_center_to_order<br>37. test_to_unassign_engg_to_destinaiton_shipping_center_to_order<br>38. test_to_assign_source_cloud_end_point_to_order<br>39. test_to_assign_destination_cloud_end_point_to_order<br>40. test_to_assign_engg_to_source_cloud_end_point_to_order<br>41. test_to_assign_engg_to_destinaiton_cloud_end_point_to_order<br>42. test_to_unassign_source_cloud_end_point_to_order<br>43. test_to_unassign_destination_cloud_end_point_to_order<br>44. test_to_unassign_engg_to_source_cloud_end_point_to_order<br>45. test_to_unassign_engg_to_destinaiton_cloud_end_point_to_order<br>46. test_to_view_timeline_of_an_order<br>47. test_to_update_time_line_of_order<br>48. test_to_view_all_the_orders_associated_with_a_shipping_center<br>49. test_to_view_all_orders_associated_with_a_cloud_end_point<br>50. test_to_assign_hardware_to_shipping_center<br>51. test_to_unassign_hardware_to_shipping_center<br>52. test_to_get_subscription_by_uid<br>53. test_to_get_all_subscriptions_of_a_zone<br>54. test_to_change_location_of_subscription<br>55. test_to_change_internal_status_of_subscription<br>56. test_to_change_overall_status_of_subscription<br>57. test_to_assign_hardware_to_subscription<br>58. test_to_unassign_hardware_to_subscription<br>59. test_to_assign_source_shipping_center_to_subscription<br>60. test_to_assign_destination_shipping_center_to_subscription<br>61. test_to_assign_engg_to_source_shipping_center_to_subscription<br>62. test_to_assign_engg_to_destinaiton_shipping_center_to_subscription<br>63. test_to_unassign_source_shipping_center_to_subscription<br>64. test_to_unassign_destination_shipping_center_to_subscription<br>65. test_to_unassign_engg_to_source_shipping_center_to_subscription<br>66. test_to_unassign_engg_to_destinaiton_shipping_center_to_subscription<br>67. test_to_view_timeline_of_an_subscription<br>68. test_to_update_time_line_of_subscription<br>69. test_to_view_all_the_subscriptions_associated_with_a_shipping_center<br>70. test_to_freeup_hardware<br>71. test_to_request_for_hardware_to_other_shipping_center |
| test_data_dart_use.py | test_data_dart_use.py | test_order | 1. test_order<br>2. test_to_create_entities<br>3. test_to_check_private_cloud_to_private_cloud_transfer<br>4. test_to_check_private_cloud_to_public_cloud_transfer_gcp<br>5. test_to_check_private_cloud_to_public_cloud_transfer_aws<br>6. test_to_check_private_cloud_to_public_cloud_transfer_azure<br>7. test_to_check_public_cloud_to_private_cloud_transfer_gcp<br>8. test_to_check_public_cloud_to_private_cloud_transfer_aws<br>9. test_to_check_public_cloud_to_private_cloud_transfer_azure<br>10. test_to_check_gcp_to_aws_transfer<br>11. test_to_check_gcp_to_azure_transfer<br>12. test_to_check_aws_to_gcp_transfer<br>13. test_to_check_aws_to_azure_transfer<br>14. test_to_check_subscription |
| test_drive_failure.py | test_drive_failure.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_power_failure<br>4. test_drive_failure_one_drive<br>5. test_drive_failure_one_drive_neagative_case<br>6. test_drive_failure_multi_drive<br>7. test_drive_failure_multi_drive_negative_case<br>8. test_drive_failure_one_drive_luns<br>9. test_drive_failure_one_drive_neagative_case_luns<br>10. test_drive_failure_multi_drive_luns<br>11. test_drive_failure_multi_drive_negative_case_luns<br>12. test_power_failure_dataprotection_1_no_enc_fs<br>13. test_power_failure_dataprotection_1_with_enc_fs<br>14. test_power_failure_dataprotection_1_no_enc_obj<br>15. test_power_failure_dataprotection_1_with_enc_obj<br>16. test_power_failure_auto_mount_dataprotection_1_no_enc_fs<br>17. test_power_failure_auto_mount_dataprotection_1_with_enc_fs<br>18. test_power_failure_auto_mount_dataprotection_1_no_enc_obj<br>19. test_power_failure_auto_mount_dataprotection_1_with_enc_obj |
| test_drive_failure_shipment.py | test_drive_failure_shipment.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_power_failure<br>4. test_power_failure_dataprotection_1_no_enc_fs<br>5. test_power_failure_dataprotection_1_with_enc_fs<br>6. test_power_failure_dataprotection_1_no_enc_obj<br>7. test_power_failure_dataprotection_1_with_enc_obj<br>8. test_power_failure_auto_mount_dataprotection_1_no_enc_fs<br>9. test_power_failure_auto_mount_dataprotection_1_with_enc_fs<br>10. test_power_failure_auto_mount_dataprotection_1_no_enc_obj<br>11. test_power_failure_auto_mount_dataprotection_1_with_enc_obj |
| test_ftp.py | test_ftp.py | tests | 1. test_bcp<br>2. test_bcpftp_push_directory<br>3. test_bcp<br>4. test_bcpftp_push_file<br>5. test_bcp<br>6. test_bcpftp_push_directory_with_space_in_src<br>7. test_bcp<br>8. test_bcpftp_push_file_with_space_in_src<br>9. test_bcp<br>10. test_bcpftp_push_directory_with_space_in_dst<br>11. test_bcp<br>12. test_bcpftp_push_delete_directory |
| test_hostname.py | test_hostname.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_hostname_change |
| test_install.py | test_install.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_install_packages<br>4. test_uninstall_packages |
| test_kms.py | test_kms.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_format_bryck_with_aws_key<br>4. test_format_bryck_with_luns_with_kms<br>5. test_format_failure_without_aws_key<br>6. test_format_failure_due_to_miscarriage_of_key_in_cloud<br>7. test_mount_bryck_with_aws_key<br>8. test_mount_bryck_uploading_aws_key_manually<br>9. test_mount_failure_without_aws_key<br>10. test_mount_failure_uploading_non_aws_key<br>11. test_mount_bryck_while_aws_key_deleted_in_cloud<br>12. test_mount_failure_while_aws_key_lost_in_cloud<br>13. test_auto_mount_with_aws_key<br>14. test_auto_mount_failure_without_aws_key<br>15. test_auto_mount_uploading_aws_key_manually<br>16. test_mount_failure_uploading_other_kms_key_manually<br>17. test_key_mapping_deleted_and_key_deleted_from_cloud_post_bryck_erase<br>18. test_aws_cloud_generated_key_is_256_bit<br>19. test_format_bryck_with_aws_key_web<br>20. test_format_failure_without_aws_key_web<br>21. test_mount_bryck_with_aws_key_web<br>22. test_mount_bryck_uploading_aws_key_manually_web<br>23. test_mount_failure_without_aws_key_web<br>24. test_mount_failure_uploading_non_aws_key_web<br>25. test_format_failure_due_to_misconfiguration_of_aws_web |
| test_longevity_performance.py | test_longevity_performance.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_longevity_performance<br>4. test_extended_longevity_performance<br>5. test_extended_longevity_performance_delete_at_once |
| test_mobility.py | test_mobility.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_bryck_mobility_dataprotection_0<br>4. test_bryck_mobility_dataprotection_1<br>5. test_bryck_mobility_dataprotection_2<br>6. test_bryck_mobility_dataprotection_0_with_enc<br>7. test_bryck_mobility_dataprotection_1_with_enc<br>8. test_bryck_mobility_dataprotection_2_with_enc<br>9. test_bryck_mobility_with_luns<br>10. test_bryck_mobility_with_encryption_corruption_one_drive<br>11. test_bryck_mobility_with_encryption_corruption_two_drive<br>12. test_bryck_mobility_with_encryption_corruption_multi_drive<br>13. test_bryck_mobility_with_partition_corruption_with_enc_one_partition<br>14. test_bryck_mobility_with_partition_corruption_with_enc_two_partition<br>15. test_bryck_mobility_with_partition_corruption_with_enc_multi_partition<br>16. test_bryck_mobility_with_partition_corruption_without_enc_one_partition<br>17. test_bryck_mobility_with_partition_corruption_without_enc_two_partition<br>18. test_bryck_mobility_with_partition_corruption_without_enc_multi_partition<br>19. test_bryck_mobility_with_drive_failure_one_drive<br>20. test_bryck_mobility_with_drive_failure_multi_drive<br>21. test_bryck_mobility_with_data_protection_io_failure<br>22. test_bryck_mobility_with_data_protection_checksum_failure<br>23. test_bryck_mobility_with_aws_kms<br>24. test_bryck_mobility_mounting_with_aws_key_uploading_manually<br>25. test_bryck_mobility_mount_failure_not_having_aws_connection<br>26. test_bryck_mobility_mount_failure_uploading_different_key<br>27. test_bryck_mobility_mount_failure_no_key_in_cloud_mount_success_uploading_manually<br>28. test_bryck_mobility_mount_failure_key_lost_in_cloud<br>29. test_bryck_mobility_automount_using_aws_key<br>30. test_bryck_mobility_automount_failure_not_having_aws_connection<br>31. test_bryck_mobility_automount_uploading_aws_key_manually_during_mount<br>32. test_multi_hop_mobility_with_enc<br>33. test_multi_hop_mobility_without_enc |
| test_performance.py | test_performance.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_local_performance<br>4. test_nfs_performance<br>5. test_local_performance_compression |
| test_raw_performance.py | test_raw_performance.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_raw_performance |
| test_reboot.py | test_reboot.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_system_reboot_dataprotection_0<br>4. test_system_reboot_dataprotection_1<br>5. test_system_reboot_dataprotection_2<br>6. test_system_reboot_dataprotection_0_with_enc<br>7. test_system_reboot_dataprotection_1_with_enc<br>8. test_system_reboot_dataprotection_2_with_enc<br>9. test_system_reboot_auto_mount_dataprotection_0_no_enc<br>10. test_system_reboot_auto_mount_dataprotection_1_no_enc<br>11. test_system_reboot_dataprotection_0_obj<br>12. test_system_reboot_dataprotection_1_obj<br>13. test_system_reboot_dataprotection_2_obj<br>14. test_system_reboot_dataprotection_0_with_enc_obj<br>15. test_system_reboot_dataprotection_1_with_enc_obj<br>16. test_system_reboot_dataprotection_2_with_enc_obj<br>17. test_system_reboot_auto_mount_dataprotection_0_no_enc_obj<br>18. test_system_reboot_auto_mount_dataprotection_1_no_enc_obj<br>19. test_system_reboot_dataprotection_0_luns<br>20. test_system_reboot_dataprotection_1_luns<br>21. test_system_reboot_dataprotection_2_luns<br>22. test_system_reboot_dataprotection_0_with_enc_luns<br>23. test_system_reboot_dataprotection_1_with_enc_luns<br>24. test_system_reboot_dataprotection_2_with_enc_luns<br>25. test_system_reboot_auto_mount_dataprotection_0_no_enc_luns<br>26. test_system_reboot_auto_mount_dataprotection_1_no_enc_luns |
| test_reboot_shipment.py | test_reboot_shipment.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_system_reboot_dataprotection_1<br>4. test_system_reboot_dataprotection_1_with_enc<br>5. test_system_reboot_auto_mount_dataprotection_1_no_enc<br>6. test_system_reboot_auto_mount_dataprotection_1_with_enc<br>7. test_system_reboot_dataprotection_1_obj<br>8. test_system_reboot_dataprotection_1_with_enc_obj<br>9. test_system_reboot_auto_mount_dataprotection_1_no_enc_obj<br>10. test_system_reboot_auto_mount_dataprotection_1_with_enc_obj |
| test_stress.py | test_stress.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_system_stability_with_all_variants |
| test_stress_shipment.py | test_stress_shipment.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_system_stability_with_all_variants |
| test_tsutil.py | test_tsutil.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_tsutil_functions |
| test_upgrade.py | test_upgrade.py | test_order | 1. test_order<br>2. test_build_upgrade |
| test_web.py | test_web.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_ui_configure_all_variants<br>4. test_ui_system_page_drive_serial_no_check<br>5. test_ui_system_page_download_client_package<br>6. test_ui_data_transfer_no_enc<br>7. test_ui_data_transfer_with_enc<br>8. test_ui_generate_bryck_report<br>9. test_ui_network_configure<br>10. test_ui_network_configure_using_dhcp<br>11. test_dashboard_wizard<br>12. test_ui_eject_with_hot_pluggability_true_with_enc<br>13. test_ui_bryck_mount_with_hot_pluggable_eject<br>14. test_cloud_ui_configure<br>15. test_cloud_ui_transfer_upload<br>16. test_cloud_ui_transfer_download<br>17. test_cloud_ui_transfer_upload_obj<br>18. test_cloud_ui_transfer_download_obj<br>19. test_cloud_ui_transfer_pause_resume<br>20. test_cloud_ui_transfer_cancel<br>21. test_cloud_ui_deconfigure |
| test_web_shipment.py | test_web_shipment.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_ui_configure_all_variants<br>4. test_ui_network_configure<br>5. test_ui_network_configure_using_dhcp |
| test_zfs.py | test_zfs.py | test_order | 1. test_order<br>2. test_bryck_check<br>3. test_zfs_filestore |
| tsutil_test.py | tsutil_test.py | tests | 1. test_bryck_format_inserted_bryck<br>2. test_bryck_format_already_formatted<br>3. test_bryck_format_already_mounted<br>4. test_format_bryck_not_found<br>5. test_format_invalid_key |
| tsutil_test.py | tsutil_test.py | tests | 1. test_bryck_format_inserted_bryck<br>2. test_bryck_format_already_formatted<br>3. test_bryck_format_already_mounted<br>4. test_format_invalid_key<br>5. test_bryck_mount<br>6. test_bryck_mount_invalid_key<br>7. test_bryck_mount_non_exist_keyfile<br>8. test_bryck_mount_no_mnt_directory<br>9. test_bryck_mount_metadata_corrupt<br>10. test_bryck_mount_enc_metadata_corrupt<br>11. test_bryck_mount_partition_table_corrupt<br>12. test_bryck_mount_metadata_corrupt_except_1<br>13. test_bryck_mount_enc_metadata_corrupt_except_1<br>14. test_bryck_mount_partition_table_corrupt_except_1<br>15. test_bryck_mount_write_files<br>16. test_bryck_mount_files_checksum<br>17. test_bryck_setkey_key_change<br>18. test_bryck_setkey_oldkey_invalid<br>19. test_bryck_setkey_newkey_invalid<br>20. test_bryck_setkey_no_keyfile<br>21. test_bryck_eject<br>22. test_bryck_eject_directory_use<br>23. test_bryck_erase_unmounted<br>24. test_break_mount_after_erase<br>25. test_bryck_info_non_formatted_bryck<br>26. test_bryck_info_non_formatted_bryck_with_nvme<br>27. test_bryck_info_formatted_bryck<br>28. test_bryck_info_not_inserted_with_nvme<br>29. test_bryck_file_metadata<br>30. test_bryck_drive_scenarios<br>31. test_bryck_pool_conflict_all<br>32. test_bryck_sanity_kms_configured<br>33. test_bryck_format_kms_no_configured<br>34. test_bryck_mount_kms_no_configured<br>35. test_bryck_mount_kms_manual_configured<br>36. test_bryck_kms_configured_key_del<br>37. test_bryck_kms_multi_drive_failure<br>38. test_scan_bryck<br>39. test_remove_bryck<br>40. test_remove_bryck_when_mounted<br>41. test_format_bryck_deduplication<br>42. test_format_bryck_compression<br>43. test_bryck_format_object_enable<br>44. test_bryck_mount_object_enable<br>45. test_bryck_format_object_enable<br>46. test_bryck_mount_object_disable<br>47. test_bryck_format_object_enable<br>48. test_bryck_mount_object_enable<br>49. test_bryck_format_object_disable<br>50. test_bryck_mount_object_disable<br>51. test_create_bucket_enable<br>52. test_create_bucket_already_exist<br>53. test_delete_bucket<br>54. test_delete_bucket_not_exist<br>55. test_list_no_bucket_created<br>56. test_list_bucket<br>57. test_create_delete_list_keys |
| tsutil_test.py | tsutil_test.py | tests | 1. test_bryck_kms_configured_key_del<br>2. test_bryck_kms_multi_drive_failure<br>3. test_scan_bryck<br>4. test_remove_bryck<br>5. test_remove_bryck_when_mounted<br>6. test_format_bryck_deduplication<br>7. test_format_bryck_compression<br>8. test_bryck_format_object_enable<br>9. test_bryck_mount_object_enable<br>10. test_bryck_format_object_enable<br>11. test_bryck_mount_object_disable<br>12. test_bryck_format_object_enable<br>13. test_bryck_mount_object_enable<br>14. test_bryck_format_object_disable<br>15. test_bryck_mount_object_disable<br>16. test_create_bucket_enable<br>17. test_create_bucket_already_exist<br>18. test_delete_bucket<br>19. test_delete_bucket_not_exist<br>20. test_list_no_bucket_created<br>21. test_list_bucket<br>22. test_create_delete_list_keys |
| tsutil_test.py | tsutil_test.py | tests | 1. test_bryck_mount<br>2. test_bryck_mount_invalid_key<br>3. test_bryck_mount_non_exist_keyfile<br>4. test_bryck_mount_no_mnt_directory<br>5. test_bryck_mount_metadata_corrupt<br>6. test_bryck_mount_enc_metadata_corrupt<br>7. test_bryck_mount_partition_table_corrupt<br>8. test_bryck_mount_fs_metadata_corrupt<br>9. test_bryck_mount_no_enc_fs_metadata_corrupt<br>10. test_bryck_mount_write_files<br>11. test_bryck_mount_files_checksum |
| tsutil_test.py | tsutil_test.py | tests | 1. test_bryck_setkey_key_change<br>2. test_bryck_setkey_oldkey_invalid<br>3. test_bryck_setkey_newkey_invalid<br>4. test_bryck_setkey_no_keyfile |
| tsutil_test.py | tsutil_test.py | tests | 1. test_bryck_info_non_formatted_bryck<br>2. test_bryck_info_non_formatted_bryck_with_nvme<br>3. test_bryck_info_formatted_bryck<br>4. test_bryck_info_mounted_bryck<br>5. test_bryck_info_not_inserted<br>6. test_bryck_info_not_inserted_with_nvme |

## 2A. Suite-by-Suite Detailed Groups

### bryckutil_test.py (tests)
Path: bryckutil_test.py

1. test_bryck_format_inserted_bryck$nl2. test_bryck_format_already_formatted$nl3. test_bryck_format_already_mounted$nl4. test_format_bryck_not_found$nl5. test_format_invalid_key$nl
### bryckutil_test.py (tests)
Path: bryckutil_test.py

1. test_bryck_format_inserted_bryck$nl2. test_bryck_format_already_formatted$nl3. test_bryck_format_already_mounted$nl4. test_format_bryck_not_found$nl5. test_format_invalid_key$nl6. test_bryck_mount$nl7. test_bryck_mount_invalid_key$nl8. test_bryck_mount_non_exist_keyfile$nl9. test_bryck_mount_no_mnt_directory$nl10. test_bryck_mount_write_files$nl11. test_bryck_mount_files_checksum$nl12. test_bryck_setkey_key_change$nl13. test_bryck_setkey_oldkey_invalid$nl14. test_bryck_setkey_newkey_invalid$nl15. test_bryck_setkey_no_keyfile$nl16. test_bryck_setkey_stress$nl17. test_bryck_eject$nl18. test_bryck_eject_already_ejected$nl19. test_bryck_eject_directory_use$nl20. test_bryck_eject_data_consistency$nl21. test_bryck_erase_mounted$nl22. test_bryck_info_non_formatted_bryck$nl23. test_bryck_info_non_formatted_bryck_with_nvme$nl24. test_bryck_info_formatted_bryck$nl25. test_bryck_info_mounted_bryck$nl26. test_bryck_info_not_inserted$nl27. test_bryck_info_not_inserted_with_nvme$nl
### bryckutil_test.py (tests)
Path: bryckutil_test.py

1. test_bryck_info_non_formatted_bryck$nl2. test_bryck_info_non_formatted_bryck_with_nvme$nl3. test_bryck_info_formatted_bryck$nl4. test_bryck_info_mounted_bryck$nl5. test_bryck_info_not_inserted$nl6. test_bryck_info_not_inserted_with_nvme$nl
### bryckutil_test.py (tests)
Path: bryckutil_test.py

1. test_bryck_mount$nl2. test_bryck_mount_invalid_key$nl3. test_bryck_mount_non_exist_keyfile$nl4. test_bryck_mount_no_mnt_directory$nl5. test_bryck_mount_write_files$nl6. test_bryck_mount_files_checksum$nl
### bryckutil_test.py (tests)
Path: bryckutil_test.py

1. test_bryck_setkey_key_change$nl2. test_bryck_setkey_oldkey_invalid$nl3. test_bryck_setkey_newkey_invalid$nl4. test_bryck_setkey_no_keyfile$nl
### test_agylstor.py (test_order)
Path: test_agylstor.py

1. test_order$nl2. test_bryck_check$nl3. test_filestore_configure$nl4. test_filestore_nfs_mount$nl5. test_bryckcp_nfs_local_push_n_stream$nl6. test_bryckcp_nfs_local_pull_n_stream$nl7. test_bryckcp_nfs_local_copy_with_illegal_patterns$nl8. test_bryckcp_nfs_remote_push_n_stream$nl9. test_bryckcp_nfs_remote_pull_n_stream$nl10. test_bryckcp_rdma_nfs_remote_push_n_stream$nl11. test_bryckcp_rdma_nfs_remote_pull_n_stream$nl12. test_bryckcp_smb_remote_pull_1_stream$nl13. test_bryckcp_smb_remote_push_n_stream$nl14. test_bryckcp_smb_remote_pull_n_stream$nl15. test_bryckcp_rdma_smb_remote_push_n_stream$nl16. test_bryckcp_rdma_smb_remote_pull_n_stream$nl17. test_bryck_eject$nl18. test_bryck_mount$nl19. test_bryckcp_tcp_push_1_stream_n_rdwr$nl20. test_bryckcp_tcp_pull_1_stream_n_rdwr$nl21. test_bryckcp_tcp_push_n_stream_n_rdwr$nl22. test_bryckcp_tcp_pull_n_stream_n_rdwr$nl23. test_ftp_remote_push_n_stream$nl24. test_ftp_remote_pull_n_stream$nl25. test_error_bryckcp_nfs_push_crash$nl26. test_error_bryckcp_nfs_pull_crash$nl27. test_error_bryckcp_nfs_push_crash_segv$nl28. test_error_bryckcp_nfs_pull_crash_segv$nl29. test_error_bryckcp_nfs_push_access_source$nl30. test_error_bryckcp_nfs_push_access_dest$nl31. test_error_bryckcp_nfs_pull_access_source$nl32. test_error_bryckcp_nfs_pull_access_dest$nl33. test_error_bryckcp_tcp_push_access_source$nl34. test_error_bryckcp_tcp_push_access_dest$nl35. test_error_bryckcp_tcp_pull_access_source$nl36. test_error_bryckcp_tcp_pull_access_dest$nl37. test_configure_cloud_aws$nl38. test_configure_cloud_azure$nl39. test_configure_cloud_gcp$nl40. test_upload_single_stream_single_file_small_data_set_aws$nl41. test_download_single_stream_single_file_small_data_set_aws$nl42. test_upload_single_stream_single_file_small_data_set_gcp$nl43. test_download_single_stream_single_file_small_data_set_gcp$nl44. test_upload_single_stream_single_file_small_data_set_azure$nl45. test_download_single_stream_single_file_small_data_set_azure$nl46. test_upload_single_stream_single_file_small_object_set_aws$nl47. test_download_single_stream_single_file_small_object_set_aws$nl48. test_delete_cloud_configuraiton_aws$nl49. test_delete_cloud_configuraiton_azure$nl50. test_delete_cloud_configuraiton_gcp$nl51. test_filestore_nfs_umount$nl52. test_bryck_eject_once$nl53. test_filestore_reinit$nl54. test_configure_luns$nl55. test_mount_bryck_with_luns$nl56. test_configure_luns_with_N_volumes$nl57. test_bryck_eject_with_luns$nl58. test_filestore_reinit_with_luns$nl59. test_filestore_configure_no_enc_automount$nl60. test_bryck_eject_no_enc$nl61. test_mount_bryck_force$nl62. test_eject_bryck_force$nl63. test_filestore_reinit_final$nl64. test_bryck_report_start$nl65. test_bryck_report_check$nl66. test_to_configure_five_red_camera$nl67. test_bryckck_verify_bryck_fs$nl68. test_build_upgrade_ui$nl
### test_aibryck.py (test_order)
Path: test_aibryck.py

1. test_order$nl2. test_bryck_check$nl3. test_inferencing_one_specific_model$nl4. test_inferencing_one_model_N_times_parallely$nl5. test_run_inferencing_on_multiple_models_sequentially$nl6. test_run_inferencing_on_Multiple_models_N_times_parallely$nl7. test_run_inferencing_on_N_models_with_N_no_of_dataset_parallely$nl8. test_inferencing_one_model_with_100TB_data$nl9. test_inferencing_four__model_with_100TB_data$nl10. test_run_inferencing_streaming_data_one_model$nl11. test_run_inferencing_streaming_data_one_model_N_times_parallely$nl12. test_run_inferencing_streaming_data_on_muliple_models$nl13. test_run_inferencing_streaming_data_on_Multiple_models_N_times_parallely$nl14. test_run_inferencing_streaming_data_on_N_models_with_N_streaming_source_parallely$nl
### test_bcp.py (tests)
Path: test_bcp.py

1. test_bcp$nl2. test_bryckcp_tcp_push_validate_exist_directory$nl3. test_bcp$nl4. test_bryckcp_tcp_push_validate_src_exist_directory$nl5. test_bcp$nl6. test_bryckcp_tcp_push_directory$nl7. test_bcp$nl8. test_bryckcp_tcp_push_file$nl9. test_bcp$nl10. test_bryckcp_tcp_push_directory_with_space_in_src$nl11. test_bcp$nl12. test_bryckcp_tcp_push_file_with_space_in_src$nl13. test_bcp$nl14. test_bryckcp_tcp_push_directory_with_space_in_dst$nl15. test_bcp$nl16. test_bryckcp_tcp_push_file_with_space_in_dst$nl17. test_bcp$nl18. test_bryckcp_tcp_push_directory_wrong_mnt_pnt$nl19. test_bcp$nl20. test_bryckcp_tcp_push_directory_invalid_src_path$nl21. test_bcp$nl22. test_bryckcp_tcp_push_directory_invalid_dst_path$nl23. test_bcp$nl24. test_bryckcp_tcp_push_validate_directory$nl25. test_bcp$nl26. test_bcp$nl27. test_bryckcp_tcp_pull_directory$nl28. test_bcp$nl29. test_bryckcp_tcp_pull_file$nl30. test_bcp$nl31. test_bryckcp_tcp_pull_directory_with_space_in_src$nl32. test_bcp$nl33. test_bryckcp_tcp_pull_directory_with_space_in_dst$nl34. test_bcp$nl35. test_bryckcp_tcp_pull_directory_invalid_src_path$nl36. test_bcp$nl37. test_bryckcp_tcp_pull_directory_invalid_dst_path$nl38. test_bcp$nl39. test_bryckcp_tcp_pull_delete_directory$nl
### test_bryck_stream.py (test_order)
Path: test_bryck_stream.py

1. test_order$nl2. test_bryck_check$nl3. test_to_configure_one_red_camera$nl4. test_to_list_out_all_red_cameras$nl5. test_to_deconfigure_specific_red_camera$nl6. test_to_configure_five_red_camera$nl7. test_to_configure_ten_red_camera$nl8. test_to_check_after_reboot_red_camera_resumes_streaming$nl9. test_to_configure_st21_video_kernal$nl10. test_to_configure_st21_audio_kernal$nl11. test_to_configure_st21_video_kernal_reboot$nl12. test_to_configure_st21_audio_kernal_reboot$nl13. test_to_configure_st21_video_dpdk$nl14. test_to_configure_st21_audio_dpdk$nl15. test_to_configure_st21_video_dpdk_reboot$nl16. test_to_configure_st21_audio_dpdk_reboot$nl
### test_bryckcp.py (test_order)
Path: test_bryckcp.py

1. test_order$nl2. test_bryck_check$nl3. test_bryckcp_with_2gb_files$nl4. test_bryckcp_with_64mb_files$nl5. test_bryckcp_with_64mb_files_multi_level$nl6. test_bryckcp_with_2gb_files_crash_transfer$nl7. test_bryckcp_with_64mb_files_crash_transfer$nl8. test_bryckcp_with_64mb_files_multi_level_crash_transfer$nl9. test_bryckcp_with_small_files_where_dest_contains_files$nl10. test_bryckcp_with_some_duplicate_files_of_the_dest$nl11. test_bryckcp_tcp_pull_push_transfer$nl12. test_bryckcp_local_transfer$nl
### test_cleanup.py (test_order)
Path: test_cleanup.py

1. test_order$nl2. test_bryck_check$nl
### test_cloud_config.py (test_order)
Path: test_cloud_config.py

1. test_order$nl2. test_bryck_check$nl3. test_miss_configure_cloud_wrong_user_aws$nl4. test_miss_configure_cloud_wrong_user_azure$nl5. test_miss_configure_cloud_wrong_keyid_aws$nl6. test_miss_configure_cloud_wrong_keyid_azure$nl7. test_miss_configure_cloud_wrong_user_keyid_aws$nl8. test_miss_configure_cloud_wrong_user_keyid_azure$nl9. test_miss_configure_cloud_wrong_cloudtype_aws$nl10. test_miss_configure_cloud_wrong_cloudtype_azure$nl11. test_configure_cloud_aws$nl12. test_configure_cloud_azure$nl13. test_configure_cloud_gcp$nl14. test_list_out_all_cloud_configuration$nl15. test_to_store_cloud_credentails_securely$nl16. test_delete_cloud_configuraiton_aws$nl17. test_delete_cloud_configuraiton_azure$nl18. test_delete_cloud_configuraiton_gcp$nl19. test_modify_cloud_configuration$nl
### test_cloud_crash.py (test_order)
Path: test_cloud_crash.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_configure_the_bryck$nl7. test_upload_single_stream_single_file_small_data_set_reboot$nl8. test_download_single_stream_single_file_small_data_set_reboot$nl9. test_upload_single_stream_directory_small_data_set_reboot$nl10. test_download_single_stream_directory_small_data_set_reboot$nl11. test_upload_single_stream_directory_with_N_level_small_data_set_reboot$nl12. test_download_single_stream_directory_with_N_level_small_data_set_reboot$nl13. test_upload_single_stream_single_file_large_data_set_reboot$nl14. test_download_single_stream_single_file_large_data_set_reboot$nl15. test_upload_single_stream_directory_large_data_set_reboot$nl16. test_download_single_stream_directory_large_data_set_reboot$nl17. test_upload_single_stream_directory_with_N_level_large_data_set_reboot$nl18. test_download_single_stream_directory_with_N_level_large_data_set_reboot$nl19. test_upload_single_stream_directory_with_billions_file_terabyte_data_reboot$nl20. test_download_single_stream_directory_with_billions_file_terabyte_data_reboot$nl21. test_upload_single_stream_directory_small_object_set_reboot$nl22. test_download_single_stream_directory_small_object_set_reboot$nl23. test_upload_single_stream_directory_with_N_level_small_object_set_reboot$nl24. test_download_single_stream_directory_with_N_level_small_object_set_reboot$nl25. test_upload_single_stream_single_file_large_object_set_reboot$nl26. test_download_single_stream_single_file_large_object_set_reboot$nl27. test_upload_single_stream_directory_large_object_set_reboot$nl28. test_download_single_stream_directory_large_object_set_reboot$nl29. test_upload_single_stream_directory_with_N_level_large_object_set_reboot$nl30. test_download_single_stream_directory_with_N_level_large_object_set_reboot$nl31. test_upload_single_stream_directory_with_billions_file_terabyte_object_set_reboot$nl32. test_download_single_stream_directory_with_billions_file_terabyte_object_set_reboot$nl33. test_upload_single_stream_single_file_small_data_set_app_crash$nl34. test_download_single_stream_single_file_small_data_set_app_crash$nl35. test_upload_single_stream_directory_small_data_set_app_crash$nl36. test_download_single_stream_directory_small_data_set_app_crash$nl37. test_upload_single_stream_directory_with_N_level_small_data_set_app_crash$nl38. test_download_single_stream_directory_with_N_level_small_data_set_app_crash$nl39. test_upload_single_stream_single_file_large_data_set_app_crash$nl40. test_download_single_stream_single_file_large_data_set_app_crash$nl41. test_upload_single_stream_directory_large_data_set_app_crash$nl42. test_download_single_stream_directory_large_data_set_app_crash$nl43. test_upload_single_stream_directory_with_N_level_large_data_set_app_crash$nl44. test_download_single_stream_directory_with_N_level_large_data_set_app_crash$nl45. test_upload_single_stream_directory_with_billions_file_terabyte_data_app_crash$nl46. test_download_single_stream_directory_with_billions_file_terabyte_data_app_crash$nl47. test_upload_single_stream_directory_small_object_set_app_crash$nl48. test_download_single_stream_directory_small_object_set_app_crash$nl49. test_upload_single_stream_directory_small_object_set_app_crash$nl50. test_download_single_stream_directory_small_object_set_app_crash$nl51. test_upload_single_stream_directory_with_N_level_small_object_set_app_crash$nl52. test_download_single_stream_directory_with_N_level_small_object_set_app_crash$nl53. test_upload_single_stream_single_file_large_object_set_app_crash$nl54. test_download_single_stream_single_file_large_object_set_app_crash$nl55. test_upload_single_stream_directory_large_object_set_app_crash$nl56. test_download_single_stream_directory_large_object_set_app_crash$nl57. test_upload_single_stream_directory_with_N_level_large_object_set_app_crash$nl58. test_download_single_stream_directory_with_N_level_large_object_set_app_crash$nl59. test_upload_single_stream_directory_with_billions_file_terabyte_object_set_app_crash$nl60. test_download_single_stream_directory_with_billions_file_terabyte_object_set_app_crash$nl61. test_eject_the_bryck$nl62. test_delete_cloud_configuraiton_aws$nl63. test_delete_cloud_configuraiton_azure$nl64. test_delete_cloud_configuraiton_gcp$nl
### test_cloud_mobility.py (test_order)
Path: test_cloud_mobility.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_upload_small_data_set_mobility$nl7. test_download_small_data_set_mobility$nl8. test_upload_large_data_set_mobility$nl9. test_download_large_data_set_mobility$nl10. test_upload_small_object_set_mobility$nl11. test_download_small_object_set_mobility$nl12. test_upload_large_object_set_mobility$nl13. test_download_large_object_set_mobility$nl14. test_delete_cloud_configuraiton_aws$nl15. test_delete_cloud_configuraiton_azure$nl16. test_delete_cloud_configuraiton_gcp$nl
### test_cloud_modify.py (test_order)
Path: test_cloud_modify.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_upload_single_stream_single_file_small_data_set_pause_modify$nl7. test_download_single_stream_single_file_small_data_set_pause_modify$nl8. test_upload_single_stream_directory_small_data_set_pause_modify$nl9. test_download_single_stream_directory_small_data_set_pause_modify$nl10. test_upload_single_stream_directory_with_N_level_small_data_set_pause_modify$nl11. test_download_single_stream_directory_with_N_level_small_data_set_pause_modify$nl12. test_upload_single_stream_single_file_large_data_set_pause_modify$nl13. test_download_single_stream_single_file_large_data_set_pause_modify$nl14. test_upload_single_stream_directory_large_data_set_pause_modify$nl15. test_download_single_stream_directory_large_data_set_pause_modify$nl16. test_upload_single_stream_directory_with_N_level_large_data_set_pause_modify$nl17. test_download_single_stream_directory_with_N_level_large_data_set_pause_modify$nl18. test_upload_single_stream_directory_with_billions_file_terabyte_data_pause_modify$nl19. test_download_single_stream_directory_with_billions_file_terabyte_data_pause_modify$nl20. test_upload_single_stream_single_file_small_object_set_pause_modify$nl21. test_download_single_stream_single_file_small_object_set_pause_modify$nl22. test_upload_single_stream_directory_small_object_set_pause_modify$nl23. test_download_single_stream_directory_small_object_set_pause_modify$nl24. test_upload_single_stream_directory_with_N_level_small_object_set_pause_modify$nl25. test_download_single_stream_directory_with_N_level_small_object_set_pause_modify$nl26. test_upload_single_stream_single_file_large_object_set_pause_modify$nl27. test_download_single_stream_single_file_large_object_set_pause_modify$nl28. test_upload_single_stream_directory_large_object_set_pause_modify$nl29. test_download_single_stream_directory_large_object_set_pause_modify$nl30. test_upload_single_stream_directory_with_N_level_large_object_set_pause_modify$nl31. test_download_single_stream_directory_with_N_level_large_object_set_pause_modify$nl32. test_upload_single_stream_directory_with_billions_file_terabyte_object_pause_modify$nl33. test_download_single_stream_directory_with_billions_file_terabyte_object_pause_modify$nl34. test_delete_cloud_configuraiton_aws$nl35. test_delete_cloud_configuraiton_azure$nl36. test_delete_cloud_configuraiton_gcp$nl
### test_cloud_pause_resume.py (test_order)
Path: test_cloud_pause_resume.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_configure_the_bryck$nl7. test_upload_single_stream_single_file_small_data_set_pause$nl8. test_download_single_stream_single_file_small_data_set_pause$nl9. test_upload_single_stream_directory_small_data_set_pause$nl10. test_download_single_stream_directory_small_data_set_pause$nl11. test_upload_single_stream_directory_with_N_level_small_data_set_pause$nl12. test_download_single_stream_directory_with_N_level_small_data_set_pause$nl13. test_upload_single_stream_single_file_large_data_set_pause$nl14. test_download_single_stream_single_file_large_data_set_pause$nl15. test_upload_single_stream_directory_large_data_set_pause$nl16. test_download_single_stream_directory_large_data_set_pause$nl17. test_upload_single_stream_directory_with_N_level_large_data_set_pause$nl18. test_download_single_stream_directory_with_N_level_large_data_set_pause$nl19. test_upload_single_stream_directory_with_billions_file_terabyte_data_pause$nl20. test_download_single_stream_directory_with_billions_file_terabyte_data_pause$nl21. test_upload_single_stream_single_file_small_object_set_pause$nl22. test_download_single_stream_single_file_small_object_set_pause$nl23. test_upload_single_stream_directory_small_object_set_pause$nl24. test_download_single_stream_directory_small_object_set_pause$nl25. test_upload_single_stream_directory_with_N_level_small_object_set_pause$nl26. test_download_single_stream_directory_with_N_level_small_object_set_pause$nl27. test_upload_single_stream_single_file_large_object_set_pause$nl28. test_download_single_stream_single_file_large_object_set_pause$nl29. test_upload_single_stream_directory_large_object_set_pause$nl30. test_download_single_stream_directory_large_object_set_pause$nl31. test_upload_single_stream_directory_with_N_level_large_object_set_pause$nl32. test_download_single_stream_directory_with_N_level_large_object_set_pause$nl33. test_upload_single_stream_directory_with_billions_file_terabyte_object_pause$nl34. test_download_single_stream_directory_with_billions_file_terabyte_object_pause$nl35. test_eject_the_bryck$nl36. test_delete_cloud_configuraiton_aws$nl37. test_delete_cloud_configuraiton_azure$nl38. test_delete_cloud_configuraiton_gcp$nl
### test_cloud_transfer.py (test_order)
Path: test_cloud_transfer.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_configure_the_bryck$nl7. test_upload_single_stream_single_file_small_data_set$nl8. test_download_single_stream_single_file_small_data_set$nl9. test_upload_single_stream_directory_small_data_set$nl10. test_download_single_stream_directory_small_data_set$nl11. test_upload_single_stream_directory_with_N_level_small_data_set$nl12. test_download_single_stream_directory_with_N_level_small_data_set$nl13. test_upload_single_stream_single_file_large_data_set$nl14. test_download_single_stream_single_file_large_data_set$nl15. test_upload_single_stream_directory_large_data_set$nl16. test_download_single_stream_directory_large_data_set$nl17. test_upload_single_stream_directory_with_N_level_large_data_set$nl18. test_download_single_stream_directory_with_N_level_large_data_set$nl19. test_upload_single_stream_single_file_small_data_set_failed_validation$nl20. test_download_single_stream_single_file_small_data_set_failed_validation$nl21. test_upload_single_stream_directory_small_data_set_failed_validation$nl22. test_download_single_stream_directory_small_data_set_failed_validation$nl23. test_upload_single_stream_directory_with_N_level_small_data_set_failed_validation$nl24. test_download_single_stream_directory_with_N_level_small_data_set_failed_validation$nl25. test_upload_single_stream_single_file_large_data_set_failed_validation$nl26. test_download_single_stream_single_file_large_data_set_failed_validation$nl27. test_upload_single_stream_directory_large_data_set_failed_validation$nl28. test_download_single_stream_directory_large_data_set_failed_validation$nl29. test_upload_single_stream_directory_with_N_level_large_data_set_failed_validation$nl30. test_download_single_stream_directory_with_N_level_large_data_set_failed_validation$nl31. test_upload_single_stream_single_file_small_object_set$nl32. test_download_single_stream_single_file_small_object_set$nl33. test_upload_single_stream_directory_small_object_set$nl34. test_download_single_stream_directory_small_object_set$nl35. test_upload_single_stream_directory_with_N_level_small_object_set$nl36. test_download_single_stream_directory_with_N_level_small_object_set$nl37. test_upload_single_stream_single_file_large_object_set$nl38. test_download_single_stream_single_file_large_object_set$nl39. test_upload_single_stream_directory_large_object_set$nl40. test_download_single_stream_directory_large_object_set$nl41. test_upload_single_stream_directory_with_N_level_large_object_set$nl42. test_download_single_stream_directory_with_N_level_large_object_set$nl43. test_upload_single_stream_directory_with_billions_file_terabyte_object$nl44. test_download_single_stream_directory_with_billions_file_terabyte_object$nl45. test_eject_the_bryck$nl46. test_upload_multi_stream_single_file_small_object_set$nl47. test_download_multi_stream_single_file_small_object_set$nl48. test_upload_multi_stream_single_file_small_data_set$nl49. test_download_multi_stream_single_file_small_data_set$nl50. test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_upload$nl51. test_to_check_transfer_can_not_be_done_if_cloud_not_configured_upload$nl52. test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_upload$nl53. test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_download$nl54. test_to_check_if_user_invoke_duplicate_transfer_upload$nl55. test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_download$nl56. test_to_check_transfer_can_not_be_done_if_cloud_not_configured_download$nl57. test_to_check_if_user_invoke_duplicate_transfer_download$nl58. test_to_cancel_ongoing_transfer$nl59. test_to_reinitiate_previously_cancelled_transfer$nl60. test_to_pause_the_transfer_and_delete_the_data_src$nl61. test_to_pause_the_transfer_delete_cloud_configuration$nl62. test_to_submit_N_number_of_transfers$nl63. test_to_specify_N_number_of_live_parallel_transfers$nl64. test_to_track_the_progress_of_one_transfer$nl65. test_to_get_all_the_transfers_details_for_specific_transfer_state$nl66. test_delete_cloud_configuraiton_aws$nl67. test_delete_cloud_configuraiton_azure$nl68. test_delete_cloud_configuraiton_gcp$nl
### test_cloud_transfer_shipment.py (test_order)
Path: test_cloud_transfer_shipment.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_upload_single_stream_single_file_small_data_set$nl7. test_download_single_stream_single_file_small_data_set$nl8. test_upload_single_stream_directory_small_data_set$nl9. test_download_single_stream_directory_small_data_set$nl10. test_upload_single_stream_single_file_small_object_set$nl11. test_download_single_stream_single_file_small_object_set$nl12. test_upload_single_stream_directory_small_object_set$nl13. test_download_single_stream_directory_small_object_set$nl14. test_delete_cloud_configuraiton_aws$nl15. test_delete_cloud_configuraiton_azure$nl16. test_delete_cloud_configuraiton_gcp$nl
### test_config.py (test_order)
Path: test_config.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_filestore_with_enc_dp_IO_DS$nl4. test_remote_object_transfer$nl5. test_eject_with_hot_pluggability_true_with_enc$nl6. test_eject_with_hot_pluggability_true_without_enc$nl7. test_bryck_mount_with_hot_pluggable_eject$nl8. test_data_integrity_with_hot_pluggable_eject$nl9. test_hot_pluggability_with_skip_drives$nl10. test_dedup_storage_efficiency$nl11. test_dedup_delete_directory$nl12. test_dedup_measure_performance$nl13. test_dedup_transfer_non_duplicate_data$nl14. test_dedup_transfer_duplicate_data$nl15. test_dedup_erase_bryck$nl16. test_dedup_mount_bryck$nl17. test_compresion_storage_efficiency$nl18. test_compression_transfer_non_compressible_data$nl19. test_compression_erase_bryck$nl20. test_compression_mount_bryck$nl21. test_configure_email_sender$nl22. test_list_email_sender$nl23. test_add_alert_user$nl24. test_deconfigure_email_sender$nl
### test_config_shipment.py (test_order)
Path: test_config_shipment.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_filestore_with_enc_dp_IO_DS$nl4. test_remote_object_transfer$nl
### test_data_corrution.py (test_order)
Path: test_data_corrution.py

1. test_order$nl2. test_bryck_check$nl3. test_encryption_corruption_one_drive$nl4. test_encryption_corruption_two_drive$nl5. test_encryption_corruption_multi_drive$nl6. test_partition_corruption_with_enc_one_partition$nl7. test_partition_corruption_with_enc_two_partition$nl8. test_partition_corruption_with_enc_multi_partition$nl9. test_partition_corruption_without_enc_one_partition$nl10. test_partition_corruption_without_enc_two_partition$nl11. test_partition_corruption_without_enc_multi_partition$nl12. test_encryption_corruption_one_drive_luns$nl13. test_encryption_corruption_two_drive_luns$nl14. test_encryption_corruption_multi_drive_luns$nl15. test_partition_corruption_with_enc_one_partition_luns$nl16. test_partition_corruption_with_enc_two_partition_luns$nl17. test_partition_corruption_with_enc_multi_partition_luns$nl18. test_partition_corruption_without_enc_one_partition_luns$nl19. test_partition_corruption_without_enc_two_partition_luns$nl20. test_partition_corruption_without_enc_multi_partition_luns$nl21. test_data_protection_io_failure$nl22. test_data_protection_checksum_failure$nl
### test_data_dart.py (test_order)
Path: test_data_dart.py

1. test_order$nl2. test_bryck_check$nl3. test_configure_cloud_aws$nl4. test_configure_cloud_azure$nl5. test_configure_cloud_gcp$nl6. test_verify_bryck_fs$nl7. test_verify_bryck_object$nl8. test_verify_cloud_transfer_fs$nl9. test_verify_cloud_transfer_object$nl10. test_verify_bryck_fs_missing_files$nl11. test_verify_bryck_object_missing_files$nl12. test_verify_cloud_down_missing_files$nl13. test_verify_cloud_down_missing_object$nl14. test_verify_bryck_fs_corrupted_files$nl15. test_verify_bryck_object_corrupted_files$nl16. test_delete_cloud_configuraiton_aws$nl17. test_delete_cloud_configuraiton_azure$nl18. test_delete_cloud_configuraiton_gcp$nl
### test_data_dart_admin.py (test_order)
Path: test_data_dart_admin.py

1. test_order$nl2. test_to_create_admin$nl3. test_to_login_to_admin_space$nl4. test_to_update_contact_details$nl5. test_to_get_admin_details$nl6. test_to_create_a_shipping_center$nl7. test_to_get_details_of_a_shipping_center$nl8. test_to_update_the_details_of_a_shipping_center$nl9. test_to_activate_a_shipping_center$nl10. test_to_deactivate_a_shipping_center$nl11. test_to_get_the_list_of_all_shipping_center_of_a_zone$nl12. test_to_search_for_a_shipping_center$nl13. test_to_get_details_of_all_orders_of_a_shipping_center$nl14. test_to_get_details_of_all_subscriptions_of_a_shipping_center$nl15. test_to_get_details_of_all_infra_engg_of_a_shipping_center$nl16. test_to_get_details_of_available_hardwares_of_a_shipping_center$nl17. test_to_create_a_cloud_end_point$nl18. test_to_update_the_details_of_a_cloud_end_point$nl19. test_to_deactivate_a_cloud_end_point$nl20. test_to_activate_a_cloud_end_point$nl21. test_to_get_details_of_a_cloud_end_point$nl22. test_to_get_the_list_of_all_cloud_end_point_of_a_zone$nl23. test_to_search_for_a_cloud_end_point$nl24. test_to_get_details_of_all_orders_of_a_cloud_end_point$nl25. test_to_get_details_of_all_subscriptions_of_a_cloud_end_point$nl26. test_to_get_details_of_all_infra_engg_of_a_cloud_end_point$nl27. test_to_add_clouds_to_a_cloud_end_point$nl28. test_to_get_public_clouds_of_a_cloud_point$nl29. test_to_create_an_infra_engg$nl30. test_to_update_the_details_of_an_infra_engg$nl31. test_to_deactivate_an_infra_engg$nl32. test_to_activate_an_infra_engg$nl33. test_to_get_an_infra_engg_by_id$nl34. test_to_get_an_infra_engg_by_mail_id$nl35. test_to_list_out_all_infra_engg_of_a_zone$nl36. test_to_get_details_of_all_orders_of_an_infra_engg$nl37. test_to_get_details_of_all_subscriptions_of_an_infra_engg$nl38. test_to_assign_an_infra_engg_to_a_shipping_center$nl39. test_to_unassign_an_infra_engg_to_a_shipping_center$nl40. test_to_assign_an_infra_engg_to_a_cloud_end_point$nl41. test_to_unassign_an_infra_engg_to_a_cloud_end_point$nl42. test_to_get_shipping_center_of_an_infra_engg$nl43. test_to_get_cloud_end_point_of_an_infra_engg$nl44. test_to_get_details_of_a_customer_by_uuid$nl45. test_to_get_details_of_a_customer_by_mail_id$nl46. test_to_list_out_all_the_customer$nl47. test_to_search_for_a_customer$nl48. test_to_get_orders_of_a_customer$nl49. test_to_get_subscriptions_of_a_customer$nl50. test_to_deactivate_of_a_customer$nl51. test_to_remove_a_customer$nl
### test_data_dart_customer.py (test_order)
Path: test_data_dart_customer.py

1. test_order$nl2. test_to_create_a_customer$nl3. test_to_login_to_customer_space$nl4. test_to_get_customer_by_uid$nl5. test_to_get_customer_by_email$nl6. test_to_create_an_order$nl7. test_to_cancel_an_order$nl8. test_to_get_order_by_uid$nl9. test_to_get_hardwares_of_order$nl10. test_to_get_orders_of_a_customer$nl11. test_to_update_timeline_of_order$nl12. test_to_get_timeline_of_order$nl13. test_to_create_a_subscription$nl14. test_to_get_subscription_by_uid$nl15. test_to_get_hardwares_of_subscription$nl16. test_to_get_subscriptions_of_a_customer$nl17. test_to_update_timeline_of_subscription$nl18. test_to_get_timeline_of_subscription$nl19. test_to_cancel_a_subscription$nl20. test_to_assign_source_contact_to_order$nl21. test_to_unassign_source_contact_to_order$nl22. test_to_assign_destinaiton_contact_to_order$nl23. test_to_unassign_destication_contact_to_order$nl24. test_to_assign_source_contact_to_subscription$nl25. test_to_unassign_source_contact_from_subscription$nl
### test_data_dart_infraengg.py (test_order)
Path: test_data_dart_infraengg.py

1. test_order$nl2. test_to_login_to_infra_engg_space$nl3. test_to_update_profile_details$nl4. test_to_get_infra_engg_by_uid$nl5. test_to_get_infra_engg_by_email$nl6. test_to_get_all_infra_engg_of_a_zone$nl7. test_to_add_bryck$nl8. test_to_add_bryck_ai$nl9. test_to_add_bryck_tray$nl10. test_to_add_server$nl11. test_to_get_hardware_by_uid$nl12. test_to_activate_hardware_by_uid$nl13. test_to_deactivate_hardware_by_uid$nl14. test_to_get_details_of_shipping_center_by_uid$nl15. test_to_get_the_list_of_shipping_centers_by_zone$nl16. test_to_search_a_shipping_center_by_name$nl17. test_to_get_details_of_cloud_end_point_by_uid$nl18. test_to_get_the_list_of_cloud_end_point_by_zone$nl19. test_to_search_a_cloud_end_point_by_name$nl20. test_to_get_details_of_customer_by_mail$nl21. test_to_get_the_list_of_customers_by_zone$nl22. test_to_search_a_customer_by_name$nl23. test_to_get_order_by_uid$nl24. test_to_get_all_orders_of_a_zone$nl25. test_to_change_location_of_order$nl26. test_to_change_internal_status_of_order$nl27. test_to_change_overall_status_of_order$nl28. test_to_assign_hardware_to_order$nl29. test_to_unassign_hardware_to_order$nl30. test_to_assign_source_shipping_center_to_order$nl31. test_to_assign_destination_shipping_center_to_order$nl32. test_to_assign_engg_to_source_shipping_center_to_order$nl33. test_to_assign_engg_to_destinaiton_shipping_center_to_order$nl34. test_to_unassign_source_shipping_center_to_order$nl35. test_to_unassign_destination_shipping_center_to_order$nl36. test_to_unassign_engg_to_source_shipping_center_to_order$nl37. test_to_unassign_engg_to_destinaiton_shipping_center_to_order$nl38. test_to_assign_source_cloud_end_point_to_order$nl39. test_to_assign_destination_cloud_end_point_to_order$nl40. test_to_assign_engg_to_source_cloud_end_point_to_order$nl41. test_to_assign_engg_to_destinaiton_cloud_end_point_to_order$nl42. test_to_unassign_source_cloud_end_point_to_order$nl43. test_to_unassign_destination_cloud_end_point_to_order$nl44. test_to_unassign_engg_to_source_cloud_end_point_to_order$nl45. test_to_unassign_engg_to_destinaiton_cloud_end_point_to_order$nl46. test_to_view_timeline_of_an_order$nl47. test_to_update_time_line_of_order$nl48. test_to_view_all_the_orders_associated_with_a_shipping_center$nl49. test_to_view_all_orders_associated_with_a_cloud_end_point$nl50. test_to_assign_hardware_to_shipping_center$nl51. test_to_unassign_hardware_to_shipping_center$nl52. test_to_get_subscription_by_uid$nl53. test_to_get_all_subscriptions_of_a_zone$nl54. test_to_change_location_of_subscription$nl55. test_to_change_internal_status_of_subscription$nl56. test_to_change_overall_status_of_subscription$nl57. test_to_assign_hardware_to_subscription$nl58. test_to_unassign_hardware_to_subscription$nl59. test_to_assign_source_shipping_center_to_subscription$nl60. test_to_assign_destination_shipping_center_to_subscription$nl61. test_to_assign_engg_to_source_shipping_center_to_subscription$nl62. test_to_assign_engg_to_destinaiton_shipping_center_to_subscription$nl63. test_to_unassign_source_shipping_center_to_subscription$nl64. test_to_unassign_destination_shipping_center_to_subscription$nl65. test_to_unassign_engg_to_source_shipping_center_to_subscription$nl66. test_to_unassign_engg_to_destinaiton_shipping_center_to_subscription$nl67. test_to_view_timeline_of_an_subscription$nl68. test_to_update_time_line_of_subscription$nl69. test_to_view_all_the_subscriptions_associated_with_a_shipping_center$nl70. test_to_freeup_hardware$nl71. test_to_request_for_hardware_to_other_shipping_center$nl
### test_data_dart_use.py (test_order)
Path: test_data_dart_use.py

1. test_order$nl2. test_to_create_entities$nl3. test_to_check_private_cloud_to_private_cloud_transfer$nl4. test_to_check_private_cloud_to_public_cloud_transfer_gcp$nl5. test_to_check_private_cloud_to_public_cloud_transfer_aws$nl6. test_to_check_private_cloud_to_public_cloud_transfer_azure$nl7. test_to_check_public_cloud_to_private_cloud_transfer_gcp$nl8. test_to_check_public_cloud_to_private_cloud_transfer_aws$nl9. test_to_check_public_cloud_to_private_cloud_transfer_azure$nl10. test_to_check_gcp_to_aws_transfer$nl11. test_to_check_gcp_to_azure_transfer$nl12. test_to_check_aws_to_gcp_transfer$nl13. test_to_check_aws_to_azure_transfer$nl14. test_to_check_subscription$nl
### test_drive_failure.py (test_order)
Path: test_drive_failure.py

1. test_order$nl2. test_bryck_check$nl3. test_power_failure$nl4. test_drive_failure_one_drive$nl5. test_drive_failure_one_drive_neagative_case$nl6. test_drive_failure_multi_drive$nl7. test_drive_failure_multi_drive_negative_case$nl8. test_drive_failure_one_drive_luns$nl9. test_drive_failure_one_drive_neagative_case_luns$nl10. test_drive_failure_multi_drive_luns$nl11. test_drive_failure_multi_drive_negative_case_luns$nl12. test_power_failure_dataprotection_1_no_enc_fs$nl13. test_power_failure_dataprotection_1_with_enc_fs$nl14. test_power_failure_dataprotection_1_no_enc_obj$nl15. test_power_failure_dataprotection_1_with_enc_obj$nl16. test_power_failure_auto_mount_dataprotection_1_no_enc_fs$nl17. test_power_failure_auto_mount_dataprotection_1_with_enc_fs$nl18. test_power_failure_auto_mount_dataprotection_1_no_enc_obj$nl19. test_power_failure_auto_mount_dataprotection_1_with_enc_obj$nl
### test_drive_failure_shipment.py (test_order)
Path: test_drive_failure_shipment.py

1. test_order$nl2. test_bryck_check$nl3. test_power_failure$nl4. test_power_failure_dataprotection_1_no_enc_fs$nl5. test_power_failure_dataprotection_1_with_enc_fs$nl6. test_power_failure_dataprotection_1_no_enc_obj$nl7. test_power_failure_dataprotection_1_with_enc_obj$nl8. test_power_failure_auto_mount_dataprotection_1_no_enc_fs$nl9. test_power_failure_auto_mount_dataprotection_1_with_enc_fs$nl10. test_power_failure_auto_mount_dataprotection_1_no_enc_obj$nl11. test_power_failure_auto_mount_dataprotection_1_with_enc_obj$nl
### test_ftp.py (tests)
Path: test_ftp.py

1. test_bcp$nl2. test_bcpftp_push_directory$nl3. test_bcp$nl4. test_bcpftp_push_file$nl5. test_bcp$nl6. test_bcpftp_push_directory_with_space_in_src$nl7. test_bcp$nl8. test_bcpftp_push_file_with_space_in_src$nl9. test_bcp$nl10. test_bcpftp_push_directory_with_space_in_dst$nl11. test_bcp$nl12. test_bcpftp_push_delete_directory$nl
### test_hostname.py (test_order)
Path: test_hostname.py

1. test_order$nl2. test_bryck_check$nl3. test_hostname_change$nl
### test_install.py (test_order)
Path: test_install.py

1. test_order$nl2. test_bryck_check$nl3. test_install_packages$nl4. test_uninstall_packages$nl
### test_kms.py (test_order)
Path: test_kms.py

1. test_order$nl2. test_bryck_check$nl3. test_format_bryck_with_aws_key$nl4. test_format_bryck_with_luns_with_kms$nl5. test_format_failure_without_aws_key$nl6. test_format_failure_due_to_miscarriage_of_key_in_cloud$nl7. test_mount_bryck_with_aws_key$nl8. test_mount_bryck_uploading_aws_key_manually$nl9. test_mount_failure_without_aws_key$nl10. test_mount_failure_uploading_non_aws_key$nl11. test_mount_bryck_while_aws_key_deleted_in_cloud$nl12. test_mount_failure_while_aws_key_lost_in_cloud$nl13. test_auto_mount_with_aws_key$nl14. test_auto_mount_failure_without_aws_key$nl15. test_auto_mount_uploading_aws_key_manually$nl16. test_mount_failure_uploading_other_kms_key_manually$nl17. test_key_mapping_deleted_and_key_deleted_from_cloud_post_bryck_erase$nl18. test_aws_cloud_generated_key_is_256_bit$nl19. test_format_bryck_with_aws_key_web$nl20. test_format_failure_without_aws_key_web$nl21. test_mount_bryck_with_aws_key_web$nl22. test_mount_bryck_uploading_aws_key_manually_web$nl23. test_mount_failure_without_aws_key_web$nl24. test_mount_failure_uploading_non_aws_key_web$nl25. test_format_failure_due_to_misconfiguration_of_aws_web$nl
### test_longevity_performance.py (test_order)
Path: test_longevity_performance.py

1. test_order$nl2. test_bryck_check$nl3. test_longevity_performance$nl4. test_extended_longevity_performance$nl5. test_extended_longevity_performance_delete_at_once$nl
### test_mobility.py (test_order)
Path: test_mobility.py

1. test_order$nl2. test_bryck_check$nl3. test_bryck_mobility_dataprotection_0$nl4. test_bryck_mobility_dataprotection_1$nl5. test_bryck_mobility_dataprotection_2$nl6. test_bryck_mobility_dataprotection_0_with_enc$nl7. test_bryck_mobility_dataprotection_1_with_enc$nl8. test_bryck_mobility_dataprotection_2_with_enc$nl9. test_bryck_mobility_with_luns$nl10. test_bryck_mobility_with_encryption_corruption_one_drive$nl11. test_bryck_mobility_with_encryption_corruption_two_drive$nl12. test_bryck_mobility_with_encryption_corruption_multi_drive$nl13. test_bryck_mobility_with_partition_corruption_with_enc_one_partition$nl14. test_bryck_mobility_with_partition_corruption_with_enc_two_partition$nl15. test_bryck_mobility_with_partition_corruption_with_enc_multi_partition$nl16. test_bryck_mobility_with_partition_corruption_without_enc_one_partition$nl17. test_bryck_mobility_with_partition_corruption_without_enc_two_partition$nl18. test_bryck_mobility_with_partition_corruption_without_enc_multi_partition$nl19. test_bryck_mobility_with_drive_failure_one_drive$nl20. test_bryck_mobility_with_drive_failure_multi_drive$nl21. test_bryck_mobility_with_data_protection_io_failure$nl22. test_bryck_mobility_with_data_protection_checksum_failure$nl23. test_bryck_mobility_with_aws_kms$nl24. test_bryck_mobility_mounting_with_aws_key_uploading_manually$nl25. test_bryck_mobility_mount_failure_not_having_aws_connection$nl26. test_bryck_mobility_mount_failure_uploading_different_key$nl27. test_bryck_mobility_mount_failure_no_key_in_cloud_mount_success_uploading_manually$nl28. test_bryck_mobility_mount_failure_key_lost_in_cloud$nl29. test_bryck_mobility_automount_using_aws_key$nl30. test_bryck_mobility_automount_failure_not_having_aws_connection$nl31. test_bryck_mobility_automount_uploading_aws_key_manually_during_mount$nl32. test_multi_hop_mobility_with_enc$nl33. test_multi_hop_mobility_without_enc$nl
### test_performance.py (test_order)
Path: test_performance.py

1. test_order$nl2. test_bryck_check$nl3. test_local_performance$nl4. test_nfs_performance$nl5. test_local_performance_compression$nl
### test_raw_performance.py (test_order)
Path: test_raw_performance.py

1. test_order$nl2. test_bryck_check$nl3. test_raw_performance$nl
### test_reboot.py (test_order)
Path: test_reboot.py

1. test_order$nl2. test_bryck_check$nl3. test_system_reboot_dataprotection_0$nl4. test_system_reboot_dataprotection_1$nl5. test_system_reboot_dataprotection_2$nl6. test_system_reboot_dataprotection_0_with_enc$nl7. test_system_reboot_dataprotection_1_with_enc$nl8. test_system_reboot_dataprotection_2_with_enc$nl9. test_system_reboot_auto_mount_dataprotection_0_no_enc$nl10. test_system_reboot_auto_mount_dataprotection_1_no_enc$nl11. test_system_reboot_dataprotection_0_obj$nl12. test_system_reboot_dataprotection_1_obj$nl13. test_system_reboot_dataprotection_2_obj$nl14. test_system_reboot_dataprotection_0_with_enc_obj$nl15. test_system_reboot_dataprotection_1_with_enc_obj$nl16. test_system_reboot_dataprotection_2_with_enc_obj$nl17. test_system_reboot_auto_mount_dataprotection_0_no_enc_obj$nl18. test_system_reboot_auto_mount_dataprotection_1_no_enc_obj$nl19. test_system_reboot_dataprotection_0_luns$nl20. test_system_reboot_dataprotection_1_luns$nl21. test_system_reboot_dataprotection_2_luns$nl22. test_system_reboot_dataprotection_0_with_enc_luns$nl23. test_system_reboot_dataprotection_1_with_enc_luns$nl24. test_system_reboot_dataprotection_2_with_enc_luns$nl25. test_system_reboot_auto_mount_dataprotection_0_no_enc_luns$nl26. test_system_reboot_auto_mount_dataprotection_1_no_enc_luns$nl
### test_reboot_shipment.py (test_order)
Path: test_reboot_shipment.py

1. test_order$nl2. test_bryck_check$nl3. test_system_reboot_dataprotection_1$nl4. test_system_reboot_dataprotection_1_with_enc$nl5. test_system_reboot_auto_mount_dataprotection_1_no_enc$nl6. test_system_reboot_auto_mount_dataprotection_1_with_enc$nl7. test_system_reboot_dataprotection_1_obj$nl8. test_system_reboot_dataprotection_1_with_enc_obj$nl9. test_system_reboot_auto_mount_dataprotection_1_no_enc_obj$nl10. test_system_reboot_auto_mount_dataprotection_1_with_enc_obj$nl
### test_stress.py (test_order)
Path: test_stress.py

1. test_order$nl2. test_bryck_check$nl3. test_system_stability_with_all_variants$nl
### test_stress_shipment.py (test_order)
Path: test_stress_shipment.py

1. test_order$nl2. test_bryck_check$nl3. test_system_stability_with_all_variants$nl
### test_tsutil.py (test_order)
Path: test_tsutil.py

1. test_order$nl2. test_bryck_check$nl3. test_tsutil_functions$nl
### test_upgrade.py (test_order)
Path: test_upgrade.py

1. test_order$nl2. test_build_upgrade$nl
### test_web.py (test_order)
Path: test_web.py

1. test_order$nl2. test_bryck_check$nl3. test_ui_configure_all_variants$nl4. test_ui_system_page_drive_serial_no_check$nl5. test_ui_system_page_download_client_package$nl6. test_ui_data_transfer_no_enc$nl7. test_ui_data_transfer_with_enc$nl8. test_ui_generate_bryck_report$nl9. test_ui_network_configure$nl10. test_ui_network_configure_using_dhcp$nl11. test_dashboard_wizard$nl12. test_ui_eject_with_hot_pluggability_true_with_enc$nl13. test_ui_bryck_mount_with_hot_pluggable_eject$nl14. test_cloud_ui_configure$nl15. test_cloud_ui_transfer_upload$nl16. test_cloud_ui_transfer_download$nl17. test_cloud_ui_transfer_upload_obj$nl18. test_cloud_ui_transfer_download_obj$nl19. test_cloud_ui_transfer_pause_resume$nl20. test_cloud_ui_transfer_cancel$nl21. test_cloud_ui_deconfigure$nl
### test_web_shipment.py (test_order)
Path: test_web_shipment.py

1. test_order$nl2. test_bryck_check$nl3. test_ui_configure_all_variants$nl4. test_ui_network_configure$nl5. test_ui_network_configure_using_dhcp$nl
### test_zfs.py (test_order)
Path: test_zfs.py

1. test_order$nl2. test_bryck_check$nl3. test_zfs_filestore$nl
### tsutil_test.py (tests)
Path: tsutil_test.py

1. test_bryck_format_inserted_bryck$nl2. test_bryck_format_already_formatted$nl3. test_bryck_format_already_mounted$nl4. test_format_bryck_not_found$nl5. test_format_invalid_key$nl
### tsutil_test.py (tests)
Path: tsutil_test.py

1. test_bryck_format_inserted_bryck$nl2. test_bryck_format_already_formatted$nl3. test_bryck_format_already_mounted$nl4. test_format_invalid_key$nl5. test_bryck_mount$nl6. test_bryck_mount_invalid_key$nl7. test_bryck_mount_non_exist_keyfile$nl8. test_bryck_mount_no_mnt_directory$nl9. test_bryck_mount_metadata_corrupt$nl10. test_bryck_mount_enc_metadata_corrupt$nl11. test_bryck_mount_partition_table_corrupt$nl12. test_bryck_mount_metadata_corrupt_except_1$nl13. test_bryck_mount_enc_metadata_corrupt_except_1$nl14. test_bryck_mount_partition_table_corrupt_except_1$nl15. test_bryck_mount_write_files$nl16. test_bryck_mount_files_checksum$nl17. test_bryck_setkey_key_change$nl18. test_bryck_setkey_oldkey_invalid$nl19. test_bryck_setkey_newkey_invalid$nl20. test_bryck_setkey_no_keyfile$nl21. test_bryck_eject$nl22. test_bryck_eject_directory_use$nl23. test_bryck_erase_unmounted$nl24. test_break_mount_after_erase$nl25. test_bryck_info_non_formatted_bryck$nl26. test_bryck_info_non_formatted_bryck_with_nvme$nl27. test_bryck_info_formatted_bryck$nl28. test_bryck_info_not_inserted_with_nvme$nl29. test_bryck_file_metadata$nl30. test_bryck_drive_scenarios$nl31. test_bryck_pool_conflict_all$nl32. test_bryck_sanity_kms_configured$nl33. test_bryck_format_kms_no_configured$nl34. test_bryck_mount_kms_no_configured$nl35. test_bryck_mount_kms_manual_configured$nl36. test_bryck_kms_configured_key_del$nl37. test_bryck_kms_multi_drive_failure$nl38. test_scan_bryck$nl39. test_remove_bryck$nl40. test_remove_bryck_when_mounted$nl41. test_format_bryck_deduplication$nl42. test_format_bryck_compression$nl43. test_bryck_format_object_enable$nl44. test_bryck_mount_object_enable$nl45. test_bryck_format_object_enable$nl46. test_bryck_mount_object_disable$nl47. test_bryck_format_object_enable$nl48. test_bryck_mount_object_enable$nl49. test_bryck_format_object_disable$nl50. test_bryck_mount_object_disable$nl51. test_create_bucket_enable$nl52. test_create_bucket_already_exist$nl53. test_delete_bucket$nl54. test_delete_bucket_not_exist$nl55. test_list_no_bucket_created$nl56. test_list_bucket$nl57. test_create_delete_list_keys$nl
### tsutil_test.py (tests)
Path: tsutil_test.py

1. test_bryck_kms_configured_key_del$nl2. test_bryck_kms_multi_drive_failure$nl3. test_scan_bryck$nl4. test_remove_bryck$nl5. test_remove_bryck_when_mounted$nl6. test_format_bryck_deduplication$nl7. test_format_bryck_compression$nl8. test_bryck_format_object_enable$nl9. test_bryck_mount_object_enable$nl10. test_bryck_format_object_enable$nl11. test_bryck_mount_object_disable$nl12. test_bryck_format_object_enable$nl13. test_bryck_mount_object_enable$nl14. test_bryck_format_object_disable$nl15. test_bryck_mount_object_disable$nl16. test_create_bucket_enable$nl17. test_create_bucket_already_exist$nl18. test_delete_bucket$nl19. test_delete_bucket_not_exist$nl20. test_list_no_bucket_created$nl21. test_list_bucket$nl22. test_create_delete_list_keys$nl
### tsutil_test.py (tests)
Path: tsutil_test.py

1. test_bryck_mount$nl2. test_bryck_mount_invalid_key$nl3. test_bryck_mount_non_exist_keyfile$nl4. test_bryck_mount_no_mnt_directory$nl5. test_bryck_mount_metadata_corrupt$nl6. test_bryck_mount_enc_metadata_corrupt$nl7. test_bryck_mount_partition_table_corrupt$nl8. test_bryck_mount_fs_metadata_corrupt$nl9. test_bryck_mount_no_enc_fs_metadata_corrupt$nl10. test_bryck_mount_write_files$nl11. test_bryck_mount_files_checksum$nl
### tsutil_test.py (tests)
Path: tsutil_test.py

1. test_bryck_setkey_key_change$nl2. test_bryck_setkey_oldkey_invalid$nl3. test_bryck_setkey_newkey_invalid$nl4. test_bryck_setkey_no_keyfile$nl
### tsutil_test.py (tests)
Path: tsutil_test.py

1. test_bryck_info_non_formatted_bryck$nl2. test_bryck_info_non_formatted_bryck_with_nvme$nl3. test_bryck_info_formatted_bryck$nl4. test_bryck_info_mounted_bryck$nl5. test_bryck_info_not_inserted$nl6. test_bryck_info_not_inserted_with_nvme$nl
## 3. Test Usage Map

| Test Function | Suites Using It |
|---|---|
| test_add_alert_user | test_config.py |
| test_auto_mount_failure_without_aws_key | test_kms.py |
| test_auto_mount_uploading_aws_key_manually | test_kms.py |
| test_auto_mount_with_aws_key | test_kms.py |
| test_aws_cloud_generated_key_is_256_bit | test_kms.py |
| test_bcp | test_bcp.py<br>test_ftp.py |
| test_bcpftp_push_delete_directory | test_ftp.py |
| test_bcpftp_push_directory | test_ftp.py |
| test_bcpftp_push_directory_with_space_in_dst | test_ftp.py |
| test_bcpftp_push_directory_with_space_in_src | test_ftp.py |
| test_bcpftp_push_file | test_ftp.py |
| test_bcpftp_push_file_with_space_in_src | test_ftp.py |
| test_break_mount_after_erase | tsutil_test.py |
| test_bryck_check | test_agylstor.py<br>test_aibryck.py<br>test_bryck_stream.py<br>test_bryckcp.py<br>test_cleanup.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_config.py<br>test_config_shipment.py<br>test_data_corrution.py<br>test_data_dart.py<br>test_drive_failure.py<br>test_drive_failure_shipment.py<br>test_hostname.py<br>test_install.py<br>test_kms.py<br>test_longevity_performance.py<br>test_mobility.py<br>test_performance.py<br>test_raw_performance.py<br>test_reboot.py<br>test_reboot_shipment.py<br>test_stress.py<br>test_stress_shipment.py<br>test_tsutil.py<br>test_web.py<br>test_web_shipment.py<br>test_zfs.py |
| test_bryck_drive_failure | - |
| test_bryck_drive_scenarios | tsutil_test.py |
| test_bryck_eject | bryckutil_test.py<br>test_agylstor.py<br>tsutil_test.py |
| test_bryck_eject_already_ejected | bryckutil_test.py |
| test_bryck_eject_data_consistency | bryckutil_test.py |
| test_bryck_eject_directory_use | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_eject_no_enc | test_agylstor.py |
| test_bryck_eject_once | test_agylstor.py |
| test_bryck_eject_with_luns | test_agylstor.py |
| test_bryck_erase_mounted | bryckutil_test.py |
| test_bryck_erase_unmounted | tsutil_test.py |
| test_bryck_file_metadata | tsutil_test.py |
| test_bryck_format_already_formatted | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_format_already_mounted | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_format_inserted_bryck | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_format_kms_no_configured | tsutil_test.py |
| test_bryck_format_object_disable | tsutil_test.py |
| test_bryck_format_object_enable | tsutil_test.py |
| test_bryck_info_formatted_bryck | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_info_mounted_bryck | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_info_non_formatted_bryck | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_info_non_formatted_bryck_with_nvme | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_info_not_inserted | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_info_not_inserted_with_nvme | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_info_stress | - |
| test_bryck_kms_configured_key_del | tsutil_test.py |
| test_bryck_kms_multi_drive_failure | tsutil_test.py |
| test_bryck_mobility_automount_failure_not_having_aws_connection | test_mobility.py |
| test_bryck_mobility_automount_uploading_aws_key_manually_during_mount | test_mobility.py |
| test_bryck_mobility_automount_using_aws_key | test_mobility.py |
| test_bryck_mobility_dataprotection_0 | test_mobility.py |
| test_bryck_mobility_dataprotection_0_with_enc | test_mobility.py |
| test_bryck_mobility_dataprotection_1 | test_mobility.py |
| test_bryck_mobility_dataprotection_1_with_enc | test_mobility.py |
| test_bryck_mobility_dataprotection_2 | test_mobility.py |
| test_bryck_mobility_dataprotection_2_with_enc | test_mobility.py |
| test_bryck_mobility_mount_failure_key_lost_in_cloud | test_mobility.py |
| test_bryck_mobility_mount_failure_no_key_in_cloud_mount_success_uploading_manually | test_mobility.py |
| test_bryck_mobility_mount_failure_not_having_aws_connection | test_mobility.py |
| test_bryck_mobility_mount_failure_uploading_different_key | test_mobility.py |
| test_bryck_mobility_mounting_with_aws_key_uploading_manually | test_mobility.py |
| test_bryck_mobility_with_aws_kms | test_mobility.py |
| test_bryck_mobility_with_data_protection_checksum_failure | test_mobility.py |
| test_bryck_mobility_with_data_protection_io_failure | test_mobility.py |
| test_bryck_mobility_with_drive_failure_multi_drive | test_mobility.py |
| test_bryck_mobility_with_drive_failure_one_drive | test_mobility.py |
| test_bryck_mobility_with_encryption_corruption_multi_drive | test_mobility.py |
| test_bryck_mobility_with_encryption_corruption_one_drive | test_mobility.py |
| test_bryck_mobility_with_encryption_corruption_two_drive | test_mobility.py |
| test_bryck_mobility_with_luns | test_mobility.py |
| test_bryck_mobility_with_partition_corruption_with_enc_multi_partition | test_mobility.py |
| test_bryck_mobility_with_partition_corruption_with_enc_one_partition | test_mobility.py |
| test_bryck_mobility_with_partition_corruption_with_enc_two_partition | test_mobility.py |
| test_bryck_mobility_with_partition_corruption_without_enc_multi_partition | test_mobility.py |
| test_bryck_mobility_with_partition_corruption_without_enc_one_partition | test_mobility.py |
| test_bryck_mobility_with_partition_corruption_without_enc_two_partition | test_mobility.py |
| test_bryck_mount | bryckutil_test.py<br>test_agylstor.py<br>tsutil_test.py |
| test_bryck_mount_enc_metadata_corrupt | tsutil_test.py |
| test_bryck_mount_enc_metadata_corrupt_except_1 | tsutil_test.py |
| test_bryck_mount_files_checksum | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_mount_fs_metadata_corrupt | tsutil_test.py |
| test_bryck_mount_invalid_key | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_mount_kms_manual_configured | tsutil_test.py |
| test_bryck_mount_kms_no_configured | tsutil_test.py |
| test_bryck_mount_metadata_corrupt | tsutil_test.py |
| test_bryck_mount_metadata_corrupt_except_1 | tsutil_test.py |
| test_bryck_mount_no_enc_fs_metadata_corrupt | tsutil_test.py |
| test_bryck_mount_no_mnt_directory | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_mount_non_exist_keyfile | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_mount_object_disable | tsutil_test.py |
| test_bryck_mount_object_enable | tsutil_test.py |
| test_bryck_mount_partition_table_corrupt | tsutil_test.py |
| test_bryck_mount_partition_table_corrupt_except_1 | tsutil_test.py |
| test_bryck_mount_stress | - |
| test_bryck_mount_with_hot_pluggable_eject | test_config.py |
| test_bryck_mount_write_files | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_pool_conflict | - |
| test_bryck_pool_conflict_all | tsutil_test.py |
| test_bryck_report_check | test_agylstor.py |
| test_bryck_report_start | test_agylstor.py |
| test_bryck_resiliency | - |
| test_bryck_sanity_kms_configured | tsutil_test.py |
| test_bryck_setkey_key_change | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_setkey_newkey_invalid | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_setkey_no_keyfile | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_setkey_oldkey_invalid | bryckutil_test.py<br>tsutil_test.py |
| test_bryck_setkey_stress | bryckutil_test.py |
| test_bryckck_verify_bryck_fs | test_agylstor.py |
| test_bryckcp_local_transfer | test_bryckcp.py |
| test_bryckcp_nfs_local_copy_with_illegal_patterns | test_agylstor.py |
| test_bryckcp_nfs_local_pull_n_stream | test_agylstor.py |
| test_bryckcp_nfs_local_push_n_stream | test_agylstor.py |
| test_bryckcp_nfs_remote_pull_n_stream | test_agylstor.py |
| test_bryckcp_nfs_remote_push_n_stream | test_agylstor.py |
| test_bryckcp_rdma_nfs_remote_pull_n_stream | test_agylstor.py |
| test_bryckcp_rdma_nfs_remote_push_n_stream | test_agylstor.py |
| test_bryckcp_rdma_smb_remote_pull_n_stream | test_agylstor.py |
| test_bryckcp_rdma_smb_remote_push_n_stream | test_agylstor.py |
| test_bryckcp_smb_push_delete_file | - |
| test_bryckcp_smb_push_directory | - |
| test_bryckcp_smb_push_directory_invalid_dst_path | - |
| test_bryckcp_smb_push_directory_invalid_src_path | - |
| test_bryckcp_smb_push_directory_with_space_in_dst | - |
| test_bryckcp_smb_push_directory_with_space_in_src | - |
| test_bryckcp_smb_push_directory_wrong_mnt_pnt | - |
| test_bryckcp_smb_push_file | - |
| test_bryckcp_smb_push_file_with_space_in_dst | - |
| test_bryckcp_smb_push_file_with_space_in_src | - |
| test_bryckcp_smb_push_validate_file | - |
| test_bryckcp_smb_remote_pull_1_stream | test_agylstor.py |
| test_bryckcp_smb_remote_pull_n_stream | test_agylstor.py |
| test_bryckcp_smb_remote_push_n_stream | test_agylstor.py |
| test_bryckcp_tcp_pull_1_stream_n_rdwr | test_agylstor.py |
| test_bryckcp_tcp_pull_data_verify | - |
| test_bryckcp_tcp_pull_delete_directory | test_bcp.py |
| test_bryckcp_tcp_pull_directory | test_bcp.py |
| test_bryckcp_tcp_pull_directory_invalid_dst_path | test_bcp.py |
| test_bryckcp_tcp_pull_directory_invalid_src_path | test_bcp.py |
| test_bryckcp_tcp_pull_directory_with_space_in_dst | test_bcp.py |
| test_bryckcp_tcp_pull_directory_with_space_in_src | test_bcp.py |
| test_bryckcp_tcp_pull_file | test_bcp.py |
| test_bryckcp_tcp_pull_n_stream_n_rdwr | test_agylstor.py |
| test_bryckcp_tcp_pull_push_transfer | test_bryckcp.py |
| test_bryckcp_tcp_push_1_stream_n_rdwr | test_agylstor.py |
| test_bryckcp_tcp_push_data_verify | - |
| test_bryckcp_tcp_push_delete_directory | - |
| test_bryckcp_tcp_push_directory | test_bcp.py |
| test_bryckcp_tcp_push_directory_invalid_dst_path | test_bcp.py |
| test_bryckcp_tcp_push_directory_invalid_src_path | test_bcp.py |
| test_bryckcp_tcp_push_directory_with_space_in_dst | test_bcp.py |
| test_bryckcp_tcp_push_directory_with_space_in_src | test_bcp.py |
| test_bryckcp_tcp_push_directory_wrong_mnt_pnt | test_bcp.py |
| test_bryckcp_tcp_push_file | test_bcp.py |
| test_bryckcp_tcp_push_file_with_space_in_dst | test_bcp.py |
| test_bryckcp_tcp_push_file_with_space_in_src | test_bcp.py |
| test_bryckcp_tcp_push_n_stream_n_rdwr | test_agylstor.py |
| test_bryckcp_tcp_push_validate_directory | test_bcp.py |
| test_bryckcp_tcp_push_validate_exist_directory | test_bcp.py |
| test_bryckcp_tcp_push_validate_src_exist_directory | test_bcp.py |
| test_bryckcp_with_2gb_files | test_bryckcp.py |
| test_bryckcp_with_2gb_files_crash_transfer | test_bryckcp.py |
| test_bryckcp_with_64mb_files | test_bryckcp.py |
| test_bryckcp_with_64mb_files_crash_transfer | test_bryckcp.py |
| test_bryckcp_with_64mb_files_multi_level | test_bryckcp.py |
| test_bryckcp_with_64mb_files_multi_level_crash_transfer | test_bryckcp.py |
| test_bryckcp_with_small_files_where_dest_contains_files | test_bryckcp.py |
| test_bryckcp_with_some_duplicate_files_of_the_dest | test_bryckcp.py |
| test_build_upgrade | test_upgrade.py |
| test_build_upgrade_ui | test_agylstor.py |
| test_cloud_ui_configure | test_web.py |
| test_cloud_ui_deconfigure | test_web.py |
| test_cloud_ui_transfer_cancel | test_web.py |
| test_cloud_ui_transfer_download | test_web.py |
| test_cloud_ui_transfer_download_obj | test_web.py |
| test_cloud_ui_transfer_pause_resume | test_web.py |
| test_cloud_ui_transfer_upload | test_web.py |
| test_cloud_ui_transfer_upload_obj | test_web.py |
| test_cmds | - |
| test_compresion_storage_efficiency | test_config.py |
| test_compression_erase_bryck | test_config.py |
| test_compression_mount_bryck | test_config.py |
| test_compression_transfer_non_compressible_data | test_config.py |
| test_configure | - |
| test_configure_cloud_aws | test_agylstor.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_data_dart.py |
| test_configure_cloud_azure | test_agylstor.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_data_dart.py |
| test_configure_cloud_gcp | test_agylstor.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_data_dart.py |
| test_configure_email_sender | test_config.py |
| test_configure_filestore_with_enc_dp_IO_DS | test_config.py<br>test_config_shipment.py |
| test_configure_luns | test_agylstor.py |
| test_configure_luns_format | - |
| test_configure_luns_mount | - |
| test_configure_luns_with_N_volumes | test_agylstor.py |
| test_configure_the_bryck | test_cloud_crash.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py |
| test_consistency_check_for_bryck_fs | - |
| test_consistency_check_for_cloud | - |
| test_create_access_key | - |
| test_create_bucket_already_exist | tsutil_test.py |
| test_create_bucket_enable | tsutil_test.py |
| test_create_bucket_with_access_key | - |
| test_create_delete_list_keys | tsutil_test.py |
| test_dashboard_wizard | test_web.py |
| test_data_integrity_with_hot_pluggable_eject | test_config.py |
| test_data_movement | - |
| test_data_movement_in_cloud | - |
| test_data_protection_checksum_failure | test_data_corrution.py |
| test_data_protection_io_failure | test_data_corrution.py |
| test_deconfigure_email_sender | test_config.py |
| test_dedup_delete_directory | test_config.py |
| test_dedup_erase_bryck | test_config.py |
| test_dedup_measure_performance | test_config.py |
| test_dedup_mount_bryck | test_config.py |
| test_dedup_storage_efficiency | test_config.py |
| test_dedup_transfer_duplicate_data | test_config.py |
| test_dedup_transfer_non_duplicate_data | test_config.py |
| test_delete_acess_key | - |
| test_delete_bucket | tsutil_test.py |
| test_delete_bucket_not_exist | tsutil_test.py |
| test_delete_bucket_with_access_key | - |
| test_delete_cloud_configuraiton_aws | test_agylstor.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_data_dart.py |
| test_delete_cloud_configuraiton_azure | test_agylstor.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_data_dart.py |
| test_delete_cloud_configuraiton_gcp | test_agylstor.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_data_dart.py |
| test_download_client_package | - |
| test_download_large_data_set_mobility | test_cloud_mobility.py |
| test_download_large_object_set_mobility | test_cloud_mobility.py |
| test_download_multi_stream_single_file_small_data_set | test_cloud_transfer.py |
| test_download_multi_stream_single_file_small_data_set_pause_modify | - |
| test_download_multi_stream_single_file_small_object_set | test_cloud_transfer.py |
| test_download_multi_stream_single_file_small_object_set_pause_modify | - |
| test_download_single_stream_directory_large_data_set | test_cloud_transfer.py |
| test_download_single_stream_directory_large_data_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_large_data_set_failed_validation | test_cloud_transfer.py |
| test_download_single_stream_directory_large_data_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_large_data_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_large_data_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_large_object_set | test_cloud_transfer.py |
| test_download_single_stream_directory_large_object_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_large_object_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_large_object_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_large_object_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_small_data_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_download_single_stream_directory_small_data_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_small_data_set_failed_validation | test_cloud_transfer.py |
| test_download_single_stream_directory_small_data_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_small_data_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_small_data_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_small_object_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_download_single_stream_directory_small_object_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_small_object_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_small_object_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_small_object_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_with_billions_file_terabyte_data_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_with_billions_file_terabyte_data_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_with_billions_file_terabyte_data_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_with_billions_file_terabyte_data_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_with_billions_file_terabyte_object | test_cloud_transfer.py |
| test_download_single_stream_directory_with_billions_file_terabyte_object_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_with_billions_file_terabyte_object_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_with_billions_file_terabyte_object_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_with_billions_file_terabyte_object_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_large_data_set | test_cloud_transfer.py |
| test_download_single_stream_directory_with_N_level_large_data_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_large_data_set_failed_validation | test_cloud_transfer.py |
| test_download_single_stream_directory_with_N_level_large_data_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_with_N_level_large_data_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_with_N_level_large_data_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_large_object_set | test_cloud_transfer.py |
| test_download_single_stream_directory_with_N_level_large_object_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_large_object_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_with_N_level_large_object_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_with_N_level_large_object_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_small_data_set | test_cloud_transfer.py |
| test_download_single_stream_directory_with_N_level_small_data_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_small_data_set_failed_validation | test_cloud_transfer.py |
| test_download_single_stream_directory_with_N_level_small_data_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_with_N_level_small_data_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_with_N_level_small_data_set_reboot | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_small_object_set | test_cloud_transfer.py |
| test_download_single_stream_directory_with_N_level_small_object_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_directory_with_N_level_small_object_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_directory_with_N_level_small_object_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_directory_with_N_level_small_object_set_reboot | test_cloud_crash.py |
| test_download_single_stream_single_file_large_data_set | test_cloud_transfer.py |
| test_download_single_stream_single_file_large_data_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_single_file_large_data_set_failed_validation | test_cloud_transfer.py |
| test_download_single_stream_single_file_large_data_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_single_file_large_data_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_single_file_large_data_set_reboot | test_cloud_crash.py |
| test_download_single_stream_single_file_large_object_set | test_cloud_transfer.py |
| test_download_single_stream_single_file_large_object_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_single_file_large_object_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_single_file_large_object_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_single_file_large_object_set_reboot | test_cloud_crash.py |
| test_download_single_stream_single_file_small_data_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_download_single_stream_single_file_small_data_set_app_crash | test_cloud_crash.py |
| test_download_single_stream_single_file_small_data_set_aws | test_agylstor.py |
| test_download_single_stream_single_file_small_data_set_azure | test_agylstor.py |
| test_download_single_stream_single_file_small_data_set_failed_validation | test_cloud_transfer.py |
| test_download_single_stream_single_file_small_data_set_gcp | test_agylstor.py |
| test_download_single_stream_single_file_small_data_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py |
| test_download_single_stream_single_file_small_data_set_reboot | test_cloud_crash.py |
| test_download_single_stream_single_file_small_object_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_download_single_stream_single_file_small_object_set_aws | test_agylstor.py |
| test_download_single_stream_single_file_small_object_set_pause | test_cloud_pause_resume.py |
| test_download_single_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py |
| test_download_small_data_set_mobility | test_cloud_mobility.py |
| test_download_small_object_set_mobility | test_cloud_mobility.py |
| test_drive_failure | - |
| test_drive_failure_multi_drive | test_drive_failure.py |
| test_drive_failure_multi_drive_luns | test_drive_failure.py |
| test_drive_failure_multi_drive_negative_case | test_drive_failure.py |
| test_drive_failure_multi_drive_negative_case_luns | test_drive_failure.py |
| test_drive_failure_negative_case | - |
| test_drive_failure_one_drive | test_drive_failure.py |
| test_drive_failure_one_drive_luns | test_drive_failure.py |
| test_drive_failure_one_drive_neagative_case | test_drive_failure.py |
| test_drive_failure_one_drive_neagative_case_luns | test_drive_failure.py |
| test_eject_bryck_force | test_agylstor.py |
| test_eject_the_bryck | test_cloud_crash.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py |
| test_eject_with_hot_pluggability_true_with_enc | test_config.py |
| test_eject_with_hot_pluggability_true_without_enc | test_config.py |
| test_encryption_corruption | - |
| test_encryption_corruption_multi_drive | test_data_corrution.py |
| test_encryption_corruption_multi_drive_luns | test_data_corrution.py |
| test_encryption_corruption_one_drive | test_data_corrution.py |
| test_encryption_corruption_one_drive_luns | test_data_corrution.py |
| test_encryption_corruption_two_drive | test_data_corrution.py |
| test_encryption_corruption_two_drive_luns | test_data_corrution.py |
| test_error_bryckcp_nfs_pull_access_dest | test_agylstor.py |
| test_error_bryckcp_nfs_pull_access_source | test_agylstor.py |
| test_error_bryckcp_nfs_pull_crash | test_agylstor.py |
| test_error_bryckcp_nfs_pull_crash_segv | test_agylstor.py |
| test_error_bryckcp_nfs_push_access_dest | test_agylstor.py |
| test_error_bryckcp_nfs_push_access_source | test_agylstor.py |
| test_error_bryckcp_nfs_push_crash | test_agylstor.py |
| test_error_bryckcp_nfs_push_crash_segv | test_agylstor.py |
| test_error_bryckcp_tcp_pull_access_dest | test_agylstor.py |
| test_error_bryckcp_tcp_pull_access_source | test_agylstor.py |
| test_error_bryckcp_tcp_pull_data_verify_dir_missing | - |
| test_error_bryckcp_tcp_pull_data_verify_file_changed | - |
| test_error_bryckcp_tcp_pull_data_verify_file_missing | - |
| test_error_bryckcp_tcp_push_access_dest | test_agylstor.py |
| test_error_bryckcp_tcp_push_access_source | test_agylstor.py |
| test_error_bryckcp_tcp_push_data_verify_dir_missing | - |
| test_error_bryckcp_tcp_push_data_verify_file_changed | - |
| test_error_bryckcp_tcp_push_data_verify_file_missing | - |
| test_extended_longevity_performance | test_longevity_performance.py |
| test_extended_longevity_performance_delete_at_once | test_longevity_performance.py |
| test_filestore_configure | test_agylstor.py |
| test_filestore_configure_no_enc_automount | test_agylstor.py |
| test_filestore_nfs_mount | test_agylstor.py |
| test_filestore_nfs_umount | test_agylstor.py |
| test_filestore_reinit | test_agylstor.py |
| test_filestore_reinit_final | test_agylstor.py |
| test_filestore_reinit_with_luns | test_agylstor.py |
| test_format_bryck_compression | tsutil_test.py |
| test_format_bryck_deduplication | tsutil_test.py |
| test_format_bryck_not_found | bryckutil_test.py<br>tsutil_test.py |
| test_format_bryck_with_aws_key | test_kms.py |
| test_format_bryck_with_aws_key_web | test_kms.py |
| test_format_bryck_with_luns_with_kms | test_kms.py |
| test_format_failure_due_to_miscarriage_of_key_in_cloud | test_kms.py |
| test_format_failure_due_to_misconfiguration_of_aws_web | test_kms.py |
| test_format_failure_without_aws_key | test_kms.py |
| test_format_failure_without_aws_key_web | test_kms.py |
| test_format_invalid_key | bryckutil_test.py<br>tsutil_test.py |
| test_format_stress | - |
| test_ftp_remote_pull_n_stream | test_agylstor.py |
| test_ftp_remote_push_n_stream | test_agylstor.py |
| test_hostname_change | test_hostname.py |
| test_hot_pluggability_with_skip_drives | test_config.py |
| test_inferencing_four__model_with_100TB_data | test_aibryck.py |
| test_inferencing_one_model_N_times_parallely | test_aibryck.py |
| test_inferencing_one_model_with_100TB_data | test_aibryck.py |
| test_inferencing_one_specific_model | test_aibryck.py |
| test_install_packages | test_install.py |
| test_key_mapping_deleted_and_key_deleted_from_cloud_post_bryck_erase | test_kms.py |
| test_list_access_key | - |
| test_list_bucket | tsutil_test.py |
| test_list_email_sender | test_config.py |
| test_list_no_bucket_created | tsutil_test.py |
| test_list_out_all_cloud_configuration | test_cloud_config.py |
| test_local_performance | test_performance.py |
| test_local_performance_compression | test_performance.py |
| test_longevity_performance | test_longevity_performance.py |
| test_miss_configure_cloud_wrong_cloudtype_aws | test_cloud_config.py |
| test_miss_configure_cloud_wrong_cloudtype_azure | test_cloud_config.py |
| test_miss_configure_cloud_wrong_keyid_aws | test_cloud_config.py |
| test_miss_configure_cloud_wrong_keyid_azure | test_cloud_config.py |
| test_miss_configure_cloud_wrong_user_aws | test_cloud_config.py |
| test_miss_configure_cloud_wrong_user_azure | test_cloud_config.py |
| test_miss_configure_cloud_wrong_user_keyid_aws | test_cloud_config.py |
| test_miss_configure_cloud_wrong_user_keyid_azure | test_cloud_config.py |
| test_modify_cloud_configuration | test_cloud_config.py |
| test_mount_bryck_force | test_agylstor.py |
| test_mount_bryck_uploading_aws_key_manually | test_kms.py |
| test_mount_bryck_uploading_aws_key_manually_web | test_kms.py |
| test_mount_bryck_while_aws_key_deleted_in_cloud | test_kms.py |
| test_mount_bryck_with_aws_key | test_kms.py |
| test_mount_bryck_with_aws_key_web | test_kms.py |
| test_mount_bryck_with_luns | test_agylstor.py |
| test_mount_failure_induced | - |
| test_mount_failure_uploading_non_aws_key | test_kms.py |
| test_mount_failure_uploading_non_aws_key_web | test_kms.py |
| test_mount_failure_uploading_other_kms_key_manually | test_kms.py |
| test_mount_failure_while_aws_key_lost_in_cloud | test_kms.py |
| test_mount_failure_without_aws_key | test_kms.py |
| test_mount_failure_without_aws_key_web | test_kms.py |
| test_multi_hop_data_movement | - |
| test_multi_hop_mobility_with_enc | test_mobility.py |
| test_multi_hop_mobility_without_enc | test_mobility.py |
| test_nfs_performance | test_performance.py |
| test_order | test_agylstor.py<br>test_aibryck.py<br>test_bryck_stream.py<br>test_bryckcp.py<br>test_cleanup.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_config.py<br>test_config_shipment.py<br>test_data_corrution.py<br>test_data_dart.py<br>test_data_dart_admin.py<br>test_data_dart_customer.py<br>test_data_dart_infraengg.py<br>test_data_dart_use.py<br>test_drive_failure.py<br>test_drive_failure_shipment.py<br>test_hostname.py<br>test_install.py<br>test_kms.py<br>test_longevity_performance.py<br>test_mobility.py<br>test_performance.py<br>test_raw_performance.py<br>test_reboot.py<br>test_reboot_shipment.py<br>test_stress.py<br>test_stress_shipment.py<br>test_tsutil.py<br>test_upgrade.py<br>test_web.py<br>test_web_shipment.py<br>test_zfs.py |
| test_partition_corruption | - |
| test_partition_corruption_with_enc_multi_partition | test_data_corrution.py |
| test_partition_corruption_with_enc_multi_partition_luns | test_data_corrution.py |
| test_partition_corruption_with_enc_one_partition | test_data_corrution.py |
| test_partition_corruption_with_enc_one_partition_luns | test_data_corrution.py |
| test_partition_corruption_with_enc_two_partition | test_data_corrution.py |
| test_partition_corruption_with_enc_two_partition_luns | test_data_corrution.py |
| test_partition_corruption_without_enc_multi_partition | test_data_corrution.py |
| test_partition_corruption_without_enc_multi_partition_luns | test_data_corrution.py |
| test_partition_corruption_without_enc_one_partition | test_data_corrution.py |
| test_partition_corruption_without_enc_one_partition_luns | test_data_corrution.py |
| test_partition_corruption_without_enc_two_partition | test_data_corrution.py |
| test_partition_corruption_without_enc_two_partition_luns | test_data_corrution.py |
| test_power_failure | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_auto_mount_dataprotection_1_no_enc_fs | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_auto_mount_dataprotection_1_no_enc_obj | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_auto_mount_dataprotection_1_with_enc_fs | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_auto_mount_dataprotection_1_with_enc_obj | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_dataprotection_1_no_enc_fs | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_dataprotection_1_no_enc_obj | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_dataprotection_1_with_enc_fs | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_power_failure_dataprotection_1_with_enc_obj | test_drive_failure.py<br>test_drive_failure_shipment.py |
| test_raw_performance | test_raw_performance.py |
| test_remote_object_transfer | test_config.py<br>test_config_shipment.py |
| test_remove_bryck | tsutil_test.py |
| test_remove_bryck_when_mounted | tsutil_test.py |
| test_run_inferencing_on_Multiple_models_N_times_parallely | test_aibryck.py |
| test_run_inferencing_on_multiple_models_sequentially | test_aibryck.py |
| test_run_inferencing_on_N_models_with_N_no_of_dataset_parallely | test_aibryck.py |
| test_run_inferencing_streaming_data_on_muliple_models | test_aibryck.py |
| test_run_inferencing_streaming_data_on_Multiple_models_N_times_parallely | test_aibryck.py |
| test_run_inferencing_streaming_data_on_N_models_with_N_streaming_source_parallely | test_aibryck.py |
| test_run_inferencing_streaming_data_one_model | test_aibryck.py |
| test_run_inferencing_streaming_data_one_model_N_times_parallely | test_aibryck.py |
| test_scan_bryck | tsutil_test.py |
| test_system_reboot_auto_mount_dataprotection_0_no_enc | test_reboot.py |
| test_system_reboot_auto_mount_dataprotection_0_no_enc_luns | test_reboot.py |
| test_system_reboot_auto_mount_dataprotection_0_no_enc_obj | test_reboot.py |
| test_system_reboot_auto_mount_dataprotection_1_no_enc | test_reboot.py<br>test_reboot_shipment.py |
| test_system_reboot_auto_mount_dataprotection_1_no_enc_luns | test_reboot.py |
| test_system_reboot_auto_mount_dataprotection_1_no_enc_obj | test_reboot.py<br>test_reboot_shipment.py |
| test_system_reboot_auto_mount_dataprotection_1_with_enc | test_reboot_shipment.py |
| test_system_reboot_auto_mount_dataprotection_1_with_enc_obj | test_reboot_shipment.py |
| test_system_reboot_dataprotection_0 | test_reboot.py |
| test_system_reboot_dataprotection_0_luns | test_reboot.py |
| test_system_reboot_dataprotection_0_obj | test_reboot.py |
| test_system_reboot_dataprotection_0_with_enc | test_reboot.py |
| test_system_reboot_dataprotection_0_with_enc_luns | test_reboot.py |
| test_system_reboot_dataprotection_0_with_enc_obj | test_reboot.py |
| test_system_reboot_dataprotection_1 | test_reboot.py<br>test_reboot_shipment.py |
| test_system_reboot_dataprotection_1_luns | test_reboot.py |
| test_system_reboot_dataprotection_1_obj | test_reboot.py<br>test_reboot_shipment.py |
| test_system_reboot_dataprotection_1_with_enc | test_reboot.py<br>test_reboot_shipment.py |
| test_system_reboot_dataprotection_1_with_enc_luns | test_reboot.py |
| test_system_reboot_dataprotection_1_with_enc_obj | test_reboot.py<br>test_reboot_shipment.py |
| test_system_reboot_dataprotection_2 | test_reboot.py |
| test_system_reboot_dataprotection_2_luns | test_reboot.py |
| test_system_reboot_dataprotection_2_obj | test_reboot.py |
| test_system_reboot_dataprotection_2_with_enc | test_reboot.py |
| test_system_reboot_dataprotection_2_with_enc_luns | test_reboot.py |
| test_system_reboot_dataprotection_2_with_enc_obj | test_reboot.py |
| test_system_stability_with_all_variants | test_stress.py<br>test_stress_shipment.py |
| test_to_activate_a_cloud_end_point | test_data_dart_admin.py |
| test_to_activate_a_shipping_center | test_data_dart_admin.py |
| test_to_activate_an_infra_engg | test_data_dart_admin.py |
| test_to_activate_hardware_by_uid | test_data_dart_infraengg.py |
| test_to_add_bryck | test_data_dart_infraengg.py |
| test_to_add_bryck_ai | test_data_dart_infraengg.py |
| test_to_add_bryck_tray | test_data_dart_infraengg.py |
| test_to_add_clouds_to_a_cloud_end_point | test_data_dart_admin.py |
| test_to_add_server | test_data_dart_infraengg.py |
| test_to_assign_an_infra_engg_to_a_cloud_end_point | test_data_dart_admin.py |
| test_to_assign_an_infra_engg_to_a_shipping_center | test_data_dart_admin.py |
| test_to_assign_destinaiton_contact_to_order | test_data_dart_customer.py |
| test_to_assign_destination_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_assign_destination_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_assign_destination_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_assign_engg_to_destinaiton_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_assign_engg_to_destinaiton_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_assign_engg_to_destinaiton_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_assign_engg_to_source_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_assign_engg_to_source_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_assign_engg_to_source_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_assign_hardware_to_order | test_data_dart_infraengg.py |
| test_to_assign_hardware_to_shipping_center | test_data_dart_infraengg.py |
| test_to_assign_hardware_to_subscription | test_data_dart_infraengg.py |
| test_to_assign_source_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_assign_source_contact_to_order | test_data_dart_customer.py |
| test_to_assign_source_contact_to_subscription | test_data_dart_customer.py |
| test_to_assign_source_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_assign_source_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_cancel_a_subscription | test_data_dart_customer.py |
| test_to_cancel_an_order | test_data_dart_customer.py |
| test_to_cancel_ongoing_transfer | test_cloud_transfer.py |
| test_to_change_internal_status_of_order | test_data_dart_infraengg.py |
| test_to_change_internal_status_of_subscription | test_data_dart_infraengg.py |
| test_to_change_location_of_order | test_data_dart_infraengg.py |
| test_to_change_location_of_subscription | test_data_dart_infraengg.py |
| test_to_change_overall_status_of_order | test_data_dart_infraengg.py |
| test_to_change_overall_status_of_subscription | test_data_dart_infraengg.py |
| test_to_check_after_reboot_red_camera_resumes_streaming | test_bryck_stream.py |
| test_to_check_aws_to_azure_transfer | test_data_dart_use.py |
| test_to_check_aws_to_gcp_transfer | test_data_dart_use.py |
| test_to_check_gcp_to_aws_transfer | test_data_dart_use.py |
| test_to_check_gcp_to_azure_transfer | test_data_dart_use.py |
| test_to_check_if_user_invoke_duplicate_transfer_download | test_cloud_transfer.py |
| test_to_check_if_user_invoke_duplicate_transfer_upload | test_cloud_transfer.py |
| test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_download | test_cloud_transfer.py |
| test_to_check_parts_of_bryck_data_can_be_transferred_to_multiple_cloud_upload | test_cloud_transfer.py |
| test_to_check_private_cloud_to_private_cloud_transfer | test_data_dart_use.py |
| test_to_check_private_cloud_to_public_cloud_transfer_aws | test_data_dart_use.py |
| test_to_check_private_cloud_to_public_cloud_transfer_azure | test_data_dart_use.py |
| test_to_check_private_cloud_to_public_cloud_transfer_gcp | test_data_dart_use.py |
| test_to_check_public_cloud_to_private_cloud_transfer_aws | test_data_dart_use.py |
| test_to_check_public_cloud_to_private_cloud_transfer_azure | test_data_dart_use.py |
| test_to_check_public_cloud_to_private_cloud_transfer_gcp | test_data_dart_use.py |
| test_to_check_subscription | test_data_dart_use.py |
| test_to_check_transfer_can_not_be_done_if_cloud_not_configured_download | test_cloud_transfer.py |
| test_to_check_transfer_can_not_be_done_if_cloud_not_configured_upload | test_cloud_transfer.py |
| test_to_configure_five_red_camera | test_agylstor.py<br>test_bryck_stream.py |
| test_to_configure_one_red_camera | test_bryck_stream.py |
| test_to_configure_st21_audio_dpdk | test_bryck_stream.py |
| test_to_configure_st21_audio_dpdk_reboot | test_bryck_stream.py |
| test_to_configure_st21_audio_kernal | test_bryck_stream.py |
| test_to_configure_st21_audio_kernal_reboot | test_bryck_stream.py |
| test_to_configure_st21_video_dpdk | test_bryck_stream.py |
| test_to_configure_st21_video_dpdk_reboot | test_bryck_stream.py |
| test_to_configure_st21_video_kernal | test_bryck_stream.py |
| test_to_configure_st21_video_kernal_reboot | test_bryck_stream.py |
| test_to_configure_ten_red_camera | test_bryck_stream.py |
| test_to_create_a_cloud_end_point | test_data_dart_admin.py |
| test_to_create_a_customer | test_data_dart_customer.py |
| test_to_create_a_shipping_center | test_data_dart_admin.py |
| test_to_create_a_subscription | test_data_dart_customer.py |
| test_to_create_admin | test_data_dart_admin.py |
| test_to_create_an_infra_engg | test_data_dart_admin.py |
| test_to_create_an_order | test_data_dart_customer.py |
| test_to_create_entities | test_data_dart_use.py |
| test_to_deactivate_a_cloud_end_point | test_data_dart_admin.py |
| test_to_deactivate_a_shipping_center | test_data_dart_admin.py |
| test_to_deactivate_an_infra_engg | test_data_dart_admin.py |
| test_to_deactivate_hardware_by_uid | test_data_dart_infraengg.py |
| test_to_deactivate_of_a_customer | test_data_dart_admin.py |
| test_to_deconfigure_specific_red_camera | test_bryck_stream.py |
| test_to_freeup_hardware | test_data_dart_infraengg.py |
| test_to_get_admin_details | test_data_dart_admin.py |
| test_to_get_all_infra_engg_of_a_zone | test_data_dart_infraengg.py |
| test_to_get_all_orders_of_a_zone | test_data_dart_infraengg.py |
| test_to_get_all_subscriptions_of_a_zone | test_data_dart_infraengg.py |
| test_to_get_all_the_transfers_details_for_specific_transfer_state | test_cloud_transfer.py |
| test_to_get_an_infra_engg_by_id | test_data_dart_admin.py |
| test_to_get_an_infra_engg_by_mail_id | test_data_dart_admin.py |
| test_to_get_cloud_end_point_of_an_infra_engg | test_data_dart_admin.py |
| test_to_get_customer_by_email | test_data_dart_customer.py |
| test_to_get_customer_by_uid | test_data_dart_customer.py |
| test_to_get_details_of_a_cloud_end_point | test_data_dart_admin.py |
| test_to_get_details_of_a_customer_by_mail_id | test_data_dart_admin.py |
| test_to_get_details_of_a_customer_by_uuid | test_data_dart_admin.py |
| test_to_get_details_of_a_shipping_center | test_data_dart_admin.py |
| test_to_get_details_of_all_infra_engg_of_a_cloud_end_point | test_data_dart_admin.py |
| test_to_get_details_of_all_infra_engg_of_a_shipping_center | test_data_dart_admin.py |
| test_to_get_details_of_all_orders_of_a_cloud_end_point | test_data_dart_admin.py |
| test_to_get_details_of_all_orders_of_a_shipping_center | test_data_dart_admin.py |
| test_to_get_details_of_all_orders_of_an_infra_engg | test_data_dart_admin.py |
| test_to_get_details_of_all_subscriptions_of_a_cloud_end_point | test_data_dart_admin.py |
| test_to_get_details_of_all_subscriptions_of_a_shipping_center | test_data_dart_admin.py |
| test_to_get_details_of_all_subscriptions_of_an_infra_engg | test_data_dart_admin.py |
| test_to_get_details_of_available_hardwares_of_a_shipping_center | test_data_dart_admin.py |
| test_to_get_details_of_cloud_end_point_by_uid | test_data_dart_infraengg.py |
| test_to_get_details_of_customer_by_mail | test_data_dart_infraengg.py |
| test_to_get_details_of_shipping_center_by_uid | test_data_dart_infraengg.py |
| test_to_get_hardware_by_uid | test_data_dart_infraengg.py |
| test_to_get_hardwares_of_order | test_data_dart_customer.py |
| test_to_get_hardwares_of_subscription | test_data_dart_customer.py |
| test_to_get_infra_engg_by_email | test_data_dart_infraengg.py |
| test_to_get_infra_engg_by_uid | test_data_dart_infraengg.py |
| test_to_get_order_by_uid | test_data_dart_customer.py<br>test_data_dart_infraengg.py |
| test_to_get_orders_of_a_customer | test_data_dart_admin.py<br>test_data_dart_customer.py |
| test_to_get_public_clouds_of_a_cloud_point | test_data_dart_admin.py |
| test_to_get_shipping_center_of_an_infra_engg | test_data_dart_admin.py |
| test_to_get_subscription_by_uid | test_data_dart_customer.py<br>test_data_dart_infraengg.py |
| test_to_get_subscriptions_of_a_customer | test_data_dart_admin.py<br>test_data_dart_customer.py |
| test_to_get_the_list_of_all_cloud_end_point_of_a_zone | test_data_dart_admin.py |
| test_to_get_the_list_of_all_shipping_center_of_a_zone | test_data_dart_admin.py |
| test_to_get_the_list_of_cloud_end_point_by_zone | test_data_dart_infraengg.py |
| test_to_get_the_list_of_customers_by_zone | test_data_dart_infraengg.py |
| test_to_get_the_list_of_shipping_centers_by_zone | test_data_dart_infraengg.py |
| test_to_get_timeline_of_order | test_data_dart_customer.py |
| test_to_get_timeline_of_subscription | test_data_dart_customer.py |
| test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_download | test_cloud_transfer.py |
| test_to_invoke_the_transfer_in_a_different_region_apart_from_configured_one_upload | test_cloud_transfer.py |
| test_to_list_out_all_infra_engg_of_a_zone | test_data_dart_admin.py |
| test_to_list_out_all_red_cameras | test_bryck_stream.py |
| test_to_list_out_all_the_customer | test_data_dart_admin.py |
| test_to_login_to_admin_space | test_data_dart_admin.py |
| test_to_login_to_customer_space | test_data_dart_customer.py |
| test_to_login_to_infra_engg_space | test_data_dart_infraengg.py |
| test_to_pause_the_transfer_and_delete_the_data_src | test_cloud_transfer.py |
| test_to_pause_the_transfer_delete_cloud_configuration | test_cloud_transfer.py |
| test_to_reinitiate_previously_cancelled_transfer | test_cloud_transfer.py |
| test_to_remove_a_customer | test_data_dart_admin.py |
| test_to_request_for_hardware_to_other_shipping_center | test_data_dart_infraengg.py |
| test_to_search_a_cloud_end_point_by_name | test_data_dart_infraengg.py |
| test_to_search_a_customer_by_name | test_data_dart_infraengg.py |
| test_to_search_a_shipping_center_by_name | test_data_dart_infraengg.py |
| test_to_search_for_a_cloud_end_point | test_data_dart_admin.py |
| test_to_search_for_a_customer | test_data_dart_admin.py |
| test_to_search_for_a_shipping_center | test_data_dart_admin.py |
| test_to_specify_N_number_of_live_parallel_transfers | test_cloud_transfer.py |
| test_to_store_cloud_credentails_securely | test_cloud_config.py |
| test_to_submit_N_number_of_transfers | test_cloud_transfer.py |
| test_to_track_the_progress_of_one_transfer | test_cloud_transfer.py |
| test_to_unassign_an_infra_engg_to_a_cloud_end_point | test_data_dart_admin.py |
| test_to_unassign_an_infra_engg_to_a_shipping_center | test_data_dart_admin.py |
| test_to_unassign_destication_contact_to_order | test_data_dart_customer.py |
| test_to_unassign_destination_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_unassign_destination_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_unassign_destination_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_unassign_engg_to_destinaiton_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_unassign_engg_to_destinaiton_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_unassign_engg_to_destinaiton_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_unassign_engg_to_source_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_unassign_engg_to_source_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_unassign_engg_to_source_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_unassign_hardware_to_order | test_data_dart_infraengg.py |
| test_to_unassign_hardware_to_shipping_center | test_data_dart_infraengg.py |
| test_to_unassign_hardware_to_subscription | test_data_dart_infraengg.py |
| test_to_unassign_source_cloud_end_point_to_order | test_data_dart_infraengg.py |
| test_to_unassign_source_contact_from_subscription | test_data_dart_customer.py |
| test_to_unassign_source_contact_to_order | test_data_dart_customer.py |
| test_to_unassign_source_shipping_center_to_order | test_data_dart_infraengg.py |
| test_to_unassign_source_shipping_center_to_subscription | test_data_dart_infraengg.py |
| test_to_update_contact_details | test_data_dart_admin.py |
| test_to_update_profile_details | test_data_dart_infraengg.py |
| test_to_update_the_details_of_a_cloud_end_point | test_data_dart_admin.py |
| test_to_update_the_details_of_a_shipping_center | test_data_dart_admin.py |
| test_to_update_the_details_of_an_infra_engg | test_data_dart_admin.py |
| test_to_update_time_line_of_order | test_data_dart_infraengg.py |
| test_to_update_time_line_of_subscription | test_data_dart_infraengg.py |
| test_to_update_timeline_of_order | test_data_dart_customer.py |
| test_to_update_timeline_of_subscription | test_data_dart_customer.py |
| test_to_view_all_orders_associated_with_a_cloud_end_point | test_data_dart_infraengg.py |
| test_to_view_all_the_orders_associated_with_a_shipping_center | test_data_dart_infraengg.py |
| test_to_view_all_the_subscriptions_associated_with_a_shipping_center | test_data_dart_infraengg.py |
| test_to_view_timeline_of_an_order | test_data_dart_infraengg.py |
| test_to_view_timeline_of_an_subscription | test_data_dart_infraengg.py |
| test_tsutil_functions | test_tsutil.py |
| test_ui_bryck_mount_with_hot_pluggable_eject | test_web.py |
| test_ui_configure | - |
| test_ui_configure_all_variants | test_web.py<br>test_web_shipment.py |
| test_ui_dashboard_wizard | - |
| test_ui_data_transfer_no_enc | test_web.py |
| test_ui_data_transfer_with_enc | test_web.py |
| test_ui_eject_with_hot_pluggability_true_with_enc | test_web.py |
| test_ui_format | - |
| test_ui_generate_bryck_report | test_web.py |
| test_ui_network_configure | test_web.py<br>test_web_shipment.py |
| test_ui_network_configure_using_dhcp | test_web.py<br>test_web_shipment.py |
| test_ui_system_page_download_client_package | test_web.py |
| test_ui_system_page_drive_serial_no_check | test_web.py |
| test_uninstall_packages | test_install.py |
| test_upload_large_data_set_mobility | test_cloud_mobility.py |
| test_upload_large_object_set_mobility | test_cloud_mobility.py |
| test_upload_multi_stream_single_file_small_data_set | test_cloud_transfer.py |
| test_upload_multi_stream_single_file_small_data_set_pause_modify | - |
| test_upload_multi_stream_single_file_small_object_set | test_cloud_transfer.py |
| test_upload_multi_stream_single_file_small_object_set_pause_modify | - |
| test_upload_single_stream_directory_large_data_set | test_cloud_transfer.py |
| test_upload_single_stream_directory_large_data_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_large_data_set_failed_validation | test_cloud_transfer.py |
| test_upload_single_stream_directory_large_data_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_large_data_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_large_data_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_large_object_set | test_cloud_transfer.py |
| test_upload_single_stream_directory_large_object_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_large_object_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_large_object_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_large_object_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_small_data_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_upload_single_stream_directory_small_data_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_small_data_set_failed_validation | test_cloud_transfer.py |
| test_upload_single_stream_directory_small_data_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_small_data_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_small_data_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_small_object_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_upload_single_stream_directory_small_object_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_small_object_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_small_object_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_small_object_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_data_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_object | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_with_billions_file_terabyte_object_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_large_data_set | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_N_level_large_data_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_large_data_set_failed_validation | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_N_level_large_data_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_with_N_level_large_data_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_with_N_level_large_data_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_large_object_set | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_N_level_large_object_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_large_object_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_with_N_level_large_object_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_with_N_level_large_object_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_small_data_set | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_N_level_small_data_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_small_data_set_failed_validation | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_N_level_small_data_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_with_N_level_small_data_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_with_N_level_small_data_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_small_object_set | test_cloud_transfer.py |
| test_upload_single_stream_directory_with_N_level_small_object_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_directory_with_N_level_small_object_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_directory_with_N_level_small_object_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_directory_with_N_level_small_object_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_single_file_large_data_set | test_cloud_transfer.py |
| test_upload_single_stream_single_file_large_data_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_single_file_large_data_set_failed_validation | test_cloud_transfer.py |
| test_upload_single_stream_single_file_large_data_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_single_file_large_data_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_single_file_large_data_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_single_file_large_object_set | test_cloud_transfer.py |
| test_upload_single_stream_single_file_large_object_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_single_file_large_object_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_single_file_large_object_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_single_file_large_object_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_single_file_small_data_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_upload_single_stream_single_file_small_data_set_app_crash | test_cloud_crash.py |
| test_upload_single_stream_single_file_small_data_set_aws | test_agylstor.py |
| test_upload_single_stream_single_file_small_data_set_azure | test_agylstor.py |
| test_upload_single_stream_single_file_small_data_set_failed_validation | test_cloud_transfer.py |
| test_upload_single_stream_single_file_small_data_set_gcp | test_agylstor.py |
| test_upload_single_stream_single_file_small_data_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py |
| test_upload_single_stream_single_file_small_data_set_reboot | test_cloud_crash.py |
| test_upload_single_stream_single_file_small_object_set | test_cloud_transfer.py<br>test_cloud_transfer_shipment.py |
| test_upload_single_stream_single_file_small_object_set_aws | test_agylstor.py |
| test_upload_single_stream_single_file_small_object_set_pause | test_cloud_pause_resume.py |
| test_upload_single_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py |
| test_upload_small_data_set_mobility | test_cloud_mobility.py |
| test_upload_small_object_set_mobility | test_cloud_mobility.py |
| test_verify_bryck_fs | test_data_dart.py |
| test_verify_bryck_fs_corrupted_files | test_data_dart.py |
| test_verify_bryck_fs_missing_files | test_data_dart.py |
| test_verify_bryck_object | test_data_dart.py |
| test_verify_bryck_object_corrupted_files | test_data_dart.py |
| test_verify_bryck_object_missing_files | test_data_dart.py |
| test_verify_cloud_down_missing_files | test_data_dart.py |
| test_verify_cloud_down_missing_object | test_data_dart.py |
| test_verify_cloud_transfer_fs | test_data_dart.py |
| test_verify_cloud_transfer_object | test_data_dart.py |
| test_zfs_filestore | test_zfs.py |

## 4. Validation

### 4.1 Referenced In Suite But Definition Not Found

| Test Name | Referenced By Suite(s) |
|---|---|
| test_bcp | test_bcp.py<br>test_ftp.py |
| test_data_integrity_with_hot_pluggable_eject | test_config.py |
| test_order | test_agylstor.py<br>test_aibryck.py<br>test_bryck_stream.py<br>test_bryckcp.py<br>test_cleanup.py<br>test_cloud_config.py<br>test_cloud_crash.py<br>test_cloud_mobility.py<br>test_cloud_modify.py<br>test_cloud_pause_resume.py<br>test_cloud_transfer.py<br>test_cloud_transfer_shipment.py<br>test_config.py<br>test_config_shipment.py<br>test_data_corrution.py<br>test_data_dart.py<br>test_data_dart_admin.py<br>test_data_dart_customer.py<br>test_data_dart_infraengg.py<br>test_data_dart_use.py<br>test_drive_failure.py<br>test_drive_failure_shipment.py<br>test_hostname.py<br>test_install.py<br>test_kms.py<br>test_longevity_performance.py<br>test_mobility.py<br>test_performance.py<br>test_raw_performance.py<br>test_reboot.py<br>test_reboot_shipment.py<br>test_stress.py<br>test_stress_shipment.py<br>test_tsutil.py<br>test_upgrade.py<br>test_web.py<br>test_web_shipment.py<br>test_zfs.py |
| test_to_deactivate_of_a_customer | test_data_dart_admin.py |
| test_to_remove_a_customer | test_data_dart_admin.py |

### 4.2 Defined But Unused By Suite Lists

| Function | File | Class | Line |
|---|---|---|---:|
| test_cmds | blockstore_data_tests.py | - | 205 |
| test_bryck_mount_stress | bryckutil_test.py | Tsutil | 235 |
| test_bryck_info_stress | bryckutil_test.py | Tsutil | 402 |
| test_format_stress | bryckutil_test.py | Tsutil | 472 |
| test_consistency_check_for_cloud | cloud_store.py | CloudStore | 1604 |
| test_consistency_check_for_bryck_fs | cloud_store.py | CloudStore | 1736 |
| test_configure | config_store.py | ConfigStore | 141 |
| test_configure_luns_format | config_store.py | ConfigStore | 191 |
| test_configure_luns_mount | config_store.py | ConfigStore | 215 |
| test_ui_configure | config_store.py | ConfigStore | 271 |
| test_bryck_resiliency | config_store.py | ConfigStore | 367 |
| test_encryption_corruption | config_store.py | ConfigStore | 406 |
| test_partition_corruption | config_store.py | ConfigStore | 427 |
| test_drive_failure | config_store.py | ConfigStore | 503 |
| test_drive_failure_negative_case | config_store.py | ConfigStore | 561 |
| test_download_client_package | config_store.py | ConfigStore | 794 |
| test_ui_dashboard_wizard | config_store.py | ConfigStore | 1396 |
| test_ui_format | config_store.py | ConfigStore | 2182 |
| test_data_movement | mobility_store.py | MobilityStore | 59 |
| test_data_movement_in_cloud | mobility_store.py | MobilityStore | 122 |
| test_multi_hop_data_movement | mobility_store.py | MobilityStore | 288 |
| test_bryckcp_tcp_push_data_verify | test_agylstor.py | AgylstorTest | 282 |
| test_bryckcp_tcp_pull_data_verify | test_agylstor.py | AgylstorTest | 285 |
| test_error_bryckcp_tcp_pull_data_verify_file_missing | test_agylstor.py | AgylstorTest | 288 |
| test_error_bryckcp_tcp_pull_data_verify_file_changed | test_agylstor.py | AgylstorTest | 291 |
| test_error_bryckcp_tcp_pull_data_verify_dir_missing | test_agylstor.py | AgylstorTest | 294 |
| test_error_bryckcp_tcp_push_data_verify_file_missing | test_agylstor.py | AgylstorTest | 297 |
| test_error_bryckcp_tcp_push_data_verify_file_changed | test_agylstor.py | AgylstorTest | 300 |
| test_error_bryckcp_tcp_push_data_verify_dir_missing | test_agylstor.py | AgylstorTest | 303 |
| test_create_access_key | test_agylstor.py | AgylstorTest | 466 |
| test_list_access_key | test_agylstor.py | AgylstorTest | 475 |
| test_delete_acess_key | test_agylstor.py | AgylstorTest | 478 |
| test_create_bucket_with_access_key | test_agylstor.py | AgylstorTest | 481 |
| test_delete_bucket_with_access_key | test_agylstor.py | AgylstorTest | 485 |
| test_bryckcp_smb_push_directory | test_bcp.py | BcpTest | 112 |
| test_bryckcp_smb_push_file | test_bcp.py | BcpTest | 128 |
| test_bryckcp_smb_push_directory_with_space_in_src | test_bcp.py | BcpTest | 170 |
| test_bryckcp_smb_push_file_with_space_in_src | test_bcp.py | BcpTest | 185 |
| test_bryckcp_smb_push_directory_with_space_in_dst | test_bcp.py | BcpTest | 223 |
| test_bryckcp_smb_push_file_with_space_in_dst | test_bcp.py | BcpTest | 237 |
| test_bryckcp_smb_push_directory_wrong_mnt_pnt | test_bcp.py | BcpTest | 261 |
| test_bryckcp_smb_push_directory_invalid_src_path | test_bcp.py | BcpTest | 285 |
| test_bryckcp_smb_push_directory_invalid_dst_path | test_bcp.py | BcpTest | 309 |
| test_bryckcp_smb_push_delete_file | test_bcp.py | BcpTest | 324 |
| test_bryckcp_smb_push_validate_file | test_bcp.py | BcpTest | 381 |
| test_bryckcp_tcp_push_delete_directory | test_bcp.py | BcpTest | 397 |
| test_upload_multi_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 247 |
| test_download_multi_stream_single_file_small_data_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 253 |
| test_upload_multi_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 326 |
| test_download_multi_stream_single_file_small_object_set_pause_modify | test_cloud_modify.py | CloudPauseResume | 332 |
| test_mount_failure_induced | tsutil_test.py | Tsutil | 317 |
| test_bryck_mount_stress | tsutil_test.py | Tsutil | 540 |
| test_bryck_info_stress | tsutil_test.py | Tsutil | 710 |
| test_format_stress | tsutil_test.py | Tsutil | 784 |
| test_bryck_drive_failure | tsutil_test.py | Tsutil | 968 |
| test_bryck_pool_conflict | tsutil_test.py | Tsutil | 1121 |


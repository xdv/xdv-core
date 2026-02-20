# XdvCoreSnapshotApp

- Source: `xdv-core/src/xdv_core_snapshot_app.ds`
- App ID: `35`
- Summary: xdv-core: runtime/state snapshot capture and restore application

## Purpose
xdv-core: runtime/state snapshot capture and restore application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `snapshot_status` | `path_ptr: UInt64` | Performs snapshot status operation. |
| `snapshot_capture` | `path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs snapshot capture operation. |
| `snapshot_restore` | `path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs snapshot restore operation. |
| `snapshot_capture_runtime` | `path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs snapshot capture runtime operation. |
| `snapshot_capture_storage` | `path_ptr: UInt64, device: Str, mount_point: Str, buffer_ptr: UInt64, size: UInt32` | Performs snapshot capture storage operation. |
| `snapshot_full` | `path_ptr: UInt64, device: Str, mount_point: Str, buffer_ptr: UInt64, size: UInt32` | Performs snapshot full operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_SNAPSHOT_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `35`
- `INVALID_FD` (`UInt64`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `io_close(...)`
- `io_open_append(...)`
- `io_open_read(...)`
- `io_read(...)`
- `io_write(...)`
- `run_runtime_minimum_set(...)`
- `storage_df(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = snapshot_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

# XdvCorePreloadApp

- Source: `xdv-core/src/xdv_core_preload_app.ds`
- App ID: `23`
- Summary: xdv-core: preload package validation and synchronization application

## Purpose
xdv-core: preload package validation and synchronization application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `preload_manifest_status` | `manifest_path_ptr: UInt64` | Performs preload manifest status operation. |
| `preload_manifest_read` | `manifest_path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs preload manifest read operation. |
| `preload_verify_package` | `package_path_ptr: UInt64` | Performs preload verify package operation. |
| `preload_verify_core_set` | `os_ptr: UInt64, core_ptr: UInt64, edx_ptr: UInt64, shell_ptr: UInt64` | Performs preload verify core set operation. |
| `preload_sync_runtime` | `manifest_path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs preload sync runtime operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_PRELOAD_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`
- `STATUS_PACKAGE_MISSING` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `23`
- `INVALID_FD` (`UInt64`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `io_close(...)`
- `io_open_read(...)`
- `io_read(...)`
- `run_runtime_minimum_set(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = preload_manifest_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

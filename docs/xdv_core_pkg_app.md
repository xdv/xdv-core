# XdvCorePkgApp

- Source: `xdv-core/src/xdv_core_pkg_app.ds`
- App ID: `33`
- Summary: xdv-core: package presence, install, and activation application

## Purpose
xdv-core: package presence, install, and activation application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `pkg_status` | `manifest_ptr: UInt64` | Performs pkg status operation. |
| `pkg_verify` | `package_ptr: UInt64` | Performs pkg verify operation. |
| `pkg_install` | `package_ptr: UInt64, mount_path_ptr: UInt64, payload_ptr: UInt64, payload_size: UInt32` | Performs pkg install operation. |
| `pkg_activate` | `(none)` | Performs pkg activate operation. |
| `pkg_list` | `path: Str` | Performs pkg list operation. |
| `pkg_sync_core_set` | `os_ptr: UInt64, core_ptr: UInt64, edx_ptr: UInt64, shell_ptr: UInt64` | Performs pkg sync core set operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_PKG_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`
- `STATUS_PACKAGE_MISSING` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `33`
- `INVALID_FD` (`UInt64`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `init_reload(...)`
- `io_close(...)`
- `io_open_read(...)`
- `io_open_write(...)`
- `io_write(...)`
- `service_reload(...)`
- `storage_dir_list(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = pkg_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

# XdvCoreEdxCtlApp

- Source: `xdv-core/src/xdv_core_edxctl_app.ds`
- App ID: `34`
- Summary: xdv-core: xdv-edx process and bridge control application

## Purpose
xdv-core: xdv-edx process and bridge control application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `edxctl_status` | `binary_path_ptr: UInt64` | Performs edxctl status operation. |
| `edxctl_register` | `entry: UInt64, priority: UInt32` | Performs edxctl register operation. |
| `edxctl_launch` | `binary_path_ptr: UInt64, entry: UInt64` | Performs edxctl launch operation. |
| `edxctl_stop` | `pid: UInt32` | Performs edxctl stop operation. |
| `edxctl_reload_bridge` | `(none)` | Performs edxctl reload bridge operation. |
| `edxctl_self_test` | `binary_path_ptr: UInt64, entry: UInt64` | Performs edxctl self test operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_EDXCTL_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `34`
- `INVALID_PID` (`UInt32`): `0`
- `DEFAULT_PRIORITY` (`UInt32`): `5`
- `DEFAULT_STACK_SIZE` (`UInt32`): `8192`

## Runtime Dependencies
- Detected runtime/API call usage:
- `init_reload(...)`
- `io_close(...)`
- `io_open_read(...)`
- `process_kill(...)`
- `process_spawn_with_stack(...)`
- `process_yield(...)`
- `run_runtime_minimum_set(...)`
- `scheduler_add(...)`
- `scheduler_remove(...)`
- `scheduler_set_priority(...)`
- `service_reload(...)`
- `sysmon_runtime_health(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = edxctl_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

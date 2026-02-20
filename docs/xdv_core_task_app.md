# XdvCoreTaskApp

- Source: `xdv-core/src/xdv_core_task_app.ds`
- App ID: `25`
- Summary: xdv-core: runtime task lifecycle management application

## Purpose
xdv-core: runtime task lifecycle management application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `task_status` | `(none)` | Performs task status operation. |
| `task_spawn` | `entry: UInt64, priority: UInt32` | Performs task spawn operation. |
| `task_join` | `pid: UInt32` | Performs task join operation. |
| `task_stop` | `pid: UInt32` | Performs task stop operation. |
| `task_cycle` | `entry: UInt64, priority: UInt32, duration_ms: UInt32` | Performs task cycle operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_TASK_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_PID` (`UInt32`): `2`
- `STATUS_INVALID_PRIORITY` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `25`
- `INVALID_PID` (`UInt32`): `0`
- `DEFAULT_STACK_SIZE` (`UInt32`): `8192`

## Runtime Dependencies
- Detected runtime/API call usage:
- `process_current_pid(...)`
- `process_join(...)`
- `process_kill(...)`
- `process_sleep(...)`
- `process_spawn_with_stack(...)`
- `scheduler_add(...)`
- `scheduler_remove(...)`
- `scheduler_set_priority(...)`
- `scheduler_status(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = task_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

# XdvCoreRepairApp

- Source: `xdv-core/src/xdv_core_repair_app.ds`
- App ID: `32`
- Summary: xdv-core: targeted runtime and filesystem repair workflows

## Purpose
xdv-core: targeted runtime and filesystem repair workflows

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `repair_status` | `(none)` | Runs repair routine for status. |
| `repair_storage` | `device: Str, mount_point: Str` | Runs repair routine for storage. |
| `repair_runtime_reload` | `(none)` | Runs repair routine for runtime reload. |
| `repair_permissions` | `path: Str` | Runs repair routine for permissions. |
| `repair_safe_mode` | `device: Str, mount_point: Str` | Runs repair routine for safe mode. |
| `repair_full` | `device: Str, mount_point: Str, path: Str` | Runs repair routine for full. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_REPAIR_FAILED` (`UInt32`): `1`

## Operational Constants
- `APP_ID` (`UInt32`): `32`

## Runtime Dependencies
- Detected runtime/API call usage:
- `recovery_diagnostics(...)`
- `recovery_reload_runtime(...)`
- `recovery_repair(...)`
- `recovery_safe_mode(...)`
- `run_runtime_minimum_set(...)`
- `security_restore(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = repair_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

# XdvCoreDiagApp

- Source: `xdv-core/src/xdv_core_diag_app.ds`
- App ID: `31`
- Summary: xdv-core: unified runtime diagnostics application

## Purpose
xdv-core: unified runtime diagnostics application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `diag_status` | `(none)` | Performs diag status operation. |
| `diag_runtime` | `(none)` | Performs diag runtime operation. |
| `diag_storage` | `device: Str, mount_point: Str` | Performs diag storage operation. |
| `diag_security` | `(none)` | Performs diag security operation. |
| `diag_full` | `device: Str, mount_point: Str` | Performs diag full operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_DIAG_FAILED` (`UInt32`): `1`

## Operational Constants
- `APP_ID` (`UInt32`): `31`

## Runtime Dependencies
- Detected runtime/API call usage:
- `recovery_diagnostics(...)`
- `run_runtime_minimum_set(...)`
- `scheduler_tick(...)`
- `security_status(...)`
- `storage_df(...)`
- `storage_status(...)`
- `sysmon_runtime_health(...)`
- `sysmon_snapshot(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = diag_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

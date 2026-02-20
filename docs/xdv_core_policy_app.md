# XdvCorePolicyApp

- Source: `xdv-core/src/xdv_core_policy_app.ds`
- App ID: `28`
- Summary: xdv-core: runtime command and profile policy application

## Purpose
xdv-core: runtime command and profile policy application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `policy_status` | `policy_path_ptr: UInt64` | Performs policy status operation. |
| `policy_load` | `policy_path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs policy load operation. |
| `policy_allow_command` | `policy_path: Str` | Performs policy allow command operation. |
| `policy_deny_command` | `policy_path: Str` | Performs policy deny command operation. |
| `policy_apply_profile` | `profile: UInt32, device: Str, mount_point: Str` | Performs policy apply profile operation. |
| `policy_reload_runtime` | `(none)` | Performs policy reload runtime operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_POLICY_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `28`
- `PROFILE_MINIMUM` (`UInt32`): `1`
- `PROFILE_ADMIN` (`UInt32`): `2`
- `PROFILE_RECOVERY` (`UInt32`): `3`
- `PROFILE_ALL` (`UInt32`): `4`
- `POLICY_FILE_MODE` (`UInt16`): `384`

## Runtime Dependencies
- Detected runtime/API call usage:
- `init_reload(...)`
- `io_close(...)`
- `io_open_read(...)`
- `io_read(...)`
- `run_profile(...)`
- `security_chmod(...)`
- `security_lockdown(...)`
- `security_status(...)`
- `service_reload(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = policy_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

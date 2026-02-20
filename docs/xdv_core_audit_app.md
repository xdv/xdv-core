# XdvCoreAuditApp

- Source: `xdv-core/src/xdv_core_audit_app.ds`
- App ID: `27`
- Summary: xdv-core: audit stream and security evidence application

## Purpose
xdv-core: audit stream and security evidence application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `audit_status` | `audit_path_ptr: UInt64` | Performs audit status operation. |
| `audit_record` | `audit_path_ptr: UInt64, event_ptr: UInt64, size: UInt32` | Performs audit record operation. |
| `audit_review` | `audit_path_ptr: UInt64, buffer_ptr: UInt64, size: UInt32` | Performs audit review operation. |
| `audit_lockdown` | `path: Str` | Performs audit lockdown operation. |
| `audit_restore` | `path: Str` | Performs audit restore operation. |
| `audit_repair_cycle` | `device: Str, mount_point: Str, audit_path_ptr: UInt64, message_ptr: UInt64, size: UInt32` | Performs audit repair cycle operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_AUDIT_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `27`

## Runtime Dependencies
- Detected runtime/API call usage:
- `journal_append(...)`
- `journal_read(...)`
- `journal_status(...)`
- `recovery_diagnostics(...)`
- `recovery_repair(...)`
- `security_lockdown(...)`
- `security_restore(...)`
- `security_status(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = audit_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

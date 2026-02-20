# XdvCoreXdvFsApp

- Source: `xdv-core/src/xdv_core_xdvfs_app.ds`
- App ID: `24`
- Summary: xdv-core: xdvfs inspection and verification application

## Purpose
xdv-core: xdvfs inspection and verification application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `xdvfs_status` | `device: Str` | Performs xdvfs status operation. |
| `xdvfs_mount_cycle` | `device: Str, mount_point: Str` | Performs xdvfs mount cycle operation. |
| `xdvfs_verify_console_kernel` | `device: Str, mount_point: Str, kernel_path: Str` | Performs xdvfs verify console kernel operation. |
| `xdvfs_space_report` | `device: Str, mount_point: Str` | Performs xdvfs space report operation. |
| `xdvfs_integrity` | `device: Str, mount_point: Str, kernel_path: Str` | Performs xdvfs integrity operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_XDVFS_FAILED` (`UInt32`): `1`
- `STATUS_MOUNT_FAILED` (`UInt32`): `2`
- `STATUS_KERNEL_MISSING` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `24`

## Runtime Dependencies
- Detected runtime/API call usage:
- `probe_all(...)`
- `space_iostat(...)`
- `storage_df(...)`
- `storage_dir_list(...)`
- `storage_fsck(...)`
- `storage_mount(...)`
- `storage_unmount(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = xdvfs_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

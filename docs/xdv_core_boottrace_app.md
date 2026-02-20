# XdvCoreBoottraceApp

- Source: `xdv-core/src/xdv_core_boottrace_app.ds`
- App ID: `22`
- Summary: xdv-core: boot timeline and loader trace application

## Purpose
xdv-core: boot timeline and loader trace application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `boottrace_status` | `trace_path_ptr: UInt64` | Performs boottrace status operation. |
| `boottrace_detect_mode` | `mbr_probe: UInt32, uefi_probe: UInt32` | Performs boottrace detect mode operation. |
| `boottrace_record_stage` | `trace_path_ptr: UInt64, message_ptr: UInt64, message_size: UInt32, stage: UInt32, ticks: UInt32` | Performs boottrace record stage operation. |
| `boottrace_validate_kernel_path` | `kernel_path_ptr: UInt64` | Performs boottrace validate kernel path operation. |
| `boottrace_summary` | `trace_path_ptr: UInt64, summary_ptr: UInt64, summary_size: UInt32, kernel_path_ptr: UInt64, mbr_probe: UInt32, uefi_probe: UInt32` | Performs boottrace summary operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_BOOTTRACE_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`
- `STATUS_INVALID_STAGE` (`UInt32`): `3`
- `STATUS_INVALID_TICK` (`UInt32`): `4`

## Operational Constants
- `APP_ID` (`UInt32`): `22`
- `BOOT_MODE_MBR` (`UInt32`): `1`
- `BOOT_MODE_UEFI` (`UInt32`): `2`
- `STAGE_MIN` (`UInt32`): `1`
- `STAGE_MAX` (`UInt32`): `12`
- `INVALID_FD` (`UInt64`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `io_close(...)`
- `io_open_read(...)`
- `log_close(...)`
- `log_open(...)`
- `log_status(...)`
- `log_write(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = boottrace_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

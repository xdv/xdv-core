# XdvCoreContractApp

- Source: `xdv-core/src/xdv_core_contract_app.ds`
- App ID: `21`
- Summary: xdv-core: boot/runtime/shell contract validation application

## Purpose
xdv-core: boot/runtime/shell contract validation application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `contract_status` | `(none)` | Performs contract status operation. |
| `contract_validate_chain` | `(none)` | Performs contract validate chain operation. |
| `contract_validate_runtime_surface` | `(none)` | Performs contract validate runtime surface operation. |
| `contract_validate_kernel_path` | `kernel_path_ptr: UInt64` | Performs contract validate kernel path operation. |
| `contract_validate_chain_paths` | `boot_path_ptr: UInt64, kernel_path_ptr: UInt64, shell_path_ptr: UInt64` | Performs contract validate chain paths operation. |
| `contract_report` | `message_ptr: UInt64` | Performs contract report operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_CONTRACT_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`
- `STATUS_CHAIN_BROKEN` (`UInt32`): `3`
- `STATUS_RUNTIME_OFFLINE` (`UInt32`): `4`

## Operational Constants
- `APP_ID` (`UInt32`): `21`
- `INVALID_FD` (`UInt64`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `console_write(...)`
- `init_status(...)`
- `io_close(...)`
- `io_open_read(...)`
- `process_current_pid(...)`
- `run_runtime_minimum_set(...)`
- `scheduler_status(...)`
- `sysmon_runtime_health(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = contract_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

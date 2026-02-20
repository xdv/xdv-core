# XdvCoreTermApp

- Source: `xdv-core/src/xdv_core_term_app.ds`
- App ID: `30`
- Summary: xdv-core: terminal rendering and interaction profile application

## Purpose
xdv-core: terminal rendering and interaction profile application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `term_status` | `(none)` | Performs term status operation. |
| `term_clear_home` | `(none)` | Performs term clear home operation. |
| `term_set_theme` | `fg: UInt8, bg: UInt8` | Performs term set theme operation. |
| `term_write_prompt` | `prompt_ptr: UInt64, row: UInt32, col: UInt32` | Performs term write prompt operation. |
| `term_banner` | `title_ptr: UInt64` | Performs term banner operation. |
| `term_reset` | `(none)` | Performs term reset operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_TERM_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`

## Operational Constants
- `APP_ID` (`UInt32`): `30`
- `DEFAULT_ROW` (`UInt32`): `0`
- `DEFAULT_COL` (`UInt32`): `0`
- `THEME_FG` (`UInt8`): `10`
- `THEME_BG` (`UInt8`): `0`

## Runtime Dependencies
- Detected runtime/API call usage:
- `console_clear(...)`
- `console_move_cursor(...)`
- `console_reset_theme(...)`
- `console_set_theme(...)`
- `console_status(...)`
- `console_write(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = term_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

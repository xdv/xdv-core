# XdvCoreKeymapApp

- Source: `xdv-core/src/xdv_core_keymap_app.ds`
- App ID: `29`
- Summary: xdv-core: keyboard map and US-layout diagnostics application

## Purpose
xdv-core: keyboard map and US-layout diagnostics application

## Public Procedures
| Procedure | Parameters | Description |
|---|---|---|
| `keymap_status` | `(none)` | Performs keymap status operation. |
| `keymap_read_scancode` | `(none)` | Performs keymap read scancode operation. |
| `keymap_is_us_printable` | `key: UInt32` | Performs keymap is us printable operation. |
| `keymap_validate_shell_chars` | `(none)` | Performs keymap validate shell chars operation. |
| `keymap_self_test` | `(none)` | Performs keymap self test operation. |

## Status And Result Codes
- `STATUS_OK` (`UInt32`): `0`
- `STATUS_KEYMAP_FAILED` (`UInt32`): `1`
- `STATUS_INVALID_INPUT` (`UInt32`): `2`
- `STATUS_KEY_NOT_PRINTABLE` (`UInt32`): `3`

## Operational Constants
- `APP_ID` (`UInt32`): `29`
- `ASCII_MIN` (`UInt32`): `32`
- `ASCII_MAX` (`UInt32`): `126`
- `KEY_COLON` (`UInt32`): `58`
- `KEY_HASH` (`UInt32`): `35`
- `KEY_SLASH` (`UInt32`): `47`
- `KEY_DOT` (`UInt32`): `46`

## Runtime Dependencies
- Detected runtime/API call usage:
- `console_read_key(...)`
- `console_status(...)`
- `init_status(...)`
- `run_runtime_minimum_set(...)`

## Integration Notes
- This module is documented as an application-level component intended for terminal/console workflows.
- It can be called directly by application launch surfaces in `xdv-shell`.
- Standard success code across `xdv-core` applications is typically `STATUS_OK` (`0`) when present.

## Example (DPL)
```dust
let status = keymap_status();
if status == STATUS_OK {
    emit "ok";
} else {
    emit "failed";
}
```

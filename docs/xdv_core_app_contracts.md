# XdvCoreAppContracts

- Source: `xdv-core/src/xdv_core_app_contracts.ds`
- Forge: `XdvCoreAppContracts`
- Summary: Stable contract registry for all xdv-core user applications.

## Contract Scope

This contract module defines:

- Stable app identity set (`APP_*` constants).
- Contract semantic version (`core_contract_pack_version`).
- App command and status boundaries (`core_contract_max_command_id`, `core_contract_max_status_code`).
- Validation APIs for command/status compliance.

## Public Procedures

- `core_contract_pack_version()`
- `core_contract_app_count()`
- `core_contract_max_command_id(app_id)`
- `core_contract_max_status_code(app_id)`
- `core_contract_is_known_app(app_id)`
- `core_contract_validate_command_id(app_id, command_id)`
- `core_contract_validate_status_code(app_id, status_code)`
- `core_contract_validate_registry()`

## Contract Invariants

- App registry size is fixed at `28` for this contract revision.
- Unknown app IDs resolve to `0` max command/status and fail validation.
- Command IDs are `1..max` for known apps.
- Status codes are `0..max` for known apps.

## Status Codes

- `CONTRACT_OK = 0`
- `CONTRACT_UNKNOWN_APP = 1`
- `CONTRACT_OUT_OF_RANGE = 2`

## Notes

This module is the normative app contract surface for `xdv-core` and is consumed by `xdv_core_app_tests.ds`.

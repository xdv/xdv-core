# XdvCoreAppTests

- Source: `xdv-core/src/xdv_core_app_tests.ds`
- Forge: `XdvCoreAppTests`
- Summary: Deterministic behavior tests for every xdv-core application module.

## Test Strategy

The suite prioritizes deterministic checks that work in bare-metal runtime paths:

- Invalid-input and invalid-command checks.
- Contract boundary validation checks.
- Range checks for runtime-dependent apps (`0/1` status acceptance where applicable).

## Coverage

The suite includes explicit tests for:

- Console, Init, IO, Memory, Process, Scheduler, String
- Runtime Admin, Sysmon, Service, Log, Storage, Security, Recovery
- CLI, Command Profile
- Contract, Boottrace, Preload, XDVFS, Task, Journal, Audit, Policy
- Keymap, Term, Diag, Repair, Pkg, EDXCTL, Snapshot
- App contract registry and metadata validators

## Public Procedures

- `run_all_tests()`

`run_all_tests()` returns:

- `0` for pass
- `1` for fail

## Execution

```bash
dust check xdv-core/src
```

Then invoke `run_all_tests()` from your integration runtime harness/shell command path.

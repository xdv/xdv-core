# xdv-core Application Documentation

This directory contains markdown documentation for each application module in `xdv-core/src`.

| App Module | Forge | Procedures | Summary |
|---|---|---:|---|
| `xdv_core_audit_app.ds` | `XdvCoreAuditApp` | 6 | xdv-core: audit stream and security evidence application |
| `xdv_core_boottrace_app.ds` | `XdvCoreBoottraceApp` | 5 | xdv-core: boot timeline and loader trace application |
| `xdv_core_cli.ds` | `XdvCoreCli` | 5 | xdv-core: shared CLI orchestration entrypoints |
| `xdv_core_console_app.ds` | `XdvCoreConsoleApp` | 7 | xdv-core: console administration application |
| `xdv_core_contract_app.ds` | `XdvCoreContractApp` | 6 | xdv-core: boot/runtime/shell contract validation application |
| `xdv_core_diag_app.ds` | `XdvCoreDiagApp` | 5 | xdv-core: unified runtime diagnostics application |
| `xdv_core_edxctl_app.ds` | `XdvCoreEdxCtlApp` | 6 | xdv-core: xdv-edx process and bridge control application |
| `xdv_core_init_app.ds` | `XdvCoreInitApp` | 7 | xdv-core: init lifecycle administration application |
| `xdv_core_io_app.ds` | `XdvCoreIoApp` | 6 | xdv-core: runtime I/O administration application |
| `xdv_core_journal_app.ds` | `XdvCoreJournalApp` | 5 | xdv-core: structured journal and log stream application |
| `xdv_core_keymap_app.ds` | `XdvCoreKeymapApp` | 5 | xdv-core: keyboard map and US-layout diagnostics application |
| `xdv_core_log_app.ds` | `XdvCoreLogApp` | 6 | xdv-core: logging administration application |
| `xdv_core_memory_app.ds` | `XdvCoreMemoryApp` | 6 | xdv-core: runtime memory administration application |
| `xdv_core_pkg_app.ds` | `XdvCorePkgApp` | 6 | xdv-core: package presence, install, and activation application |
| `xdv_core_policy_app.ds` | `XdvCorePolicyApp` | 6 | xdv-core: runtime command and profile policy application |
| `xdv_core_preload_app.ds` | `XdvCorePreloadApp` | 5 | xdv-core: preload package validation and synchronization application |
| `xdv_core_process_app.ds` | `XdvCoreProcessApp` | 7 | xdv-core: runtime process administration application |
| `xdv_core_recovery_app.ds` | `XdvCoreRecoveryApp` | 4 | xdv-core: diagnostics and recovery application |
| `xdv_core_repair_app.ds` | `XdvCoreRepairApp` | 6 | xdv-core: targeted runtime and filesystem repair workflows |
| `xdv_core_runtime_admin.ds` | `XdvCoreRuntimeAdmin` | 3 | xdv-core: runtime administration orchestration application |
| `xdv_core_scheduler_app.ds` | `XdvCoreSchedulerApp` | 7 | xdv-core: runtime scheduler administration application |
| `xdv_core_security_app.ds` | `XdvCoreSecurityApp` | 6 | xdv-core: security and permission administration application |
| `xdv_core_service_app.ds` | `XdvCoreServiceApp` | 6 | xdv-core: service and task control application |
| `xdv_core_snapshot_app.ds` | `XdvCoreSnapshotApp` | 6 | xdv-core: runtime/state snapshot capture and restore application |
| `xdv_core_storage_app.ds` | `XdvCoreStorageApp` | 9 | xdv-core: storage and filesystem administration application |
| `xdv_core_string_app.ds` | `XdvCoreStringApp` | 7 | xdv-core: runtime string administration application |
| `xdv_core_sysmon_app.ds` | `XdvCoreSysmonApp` | 4 | xdv-core: runtime and system telemetry application |
| `xdv_core_task_app.ds` | `XdvCoreTaskApp` | 5 | xdv-core: runtime task lifecycle management application |
| `xdv_core_term_app.ds` | `XdvCoreTermApp` | 6 | xdv-core: terminal rendering and interaction profile application |
| `xdv_core_xdvfs_app.ds` | `XdvCoreXdvFsApp` | 5 | xdv-core: xdvfs inspection and verification application |

## Notes
- Generated from source signatures/constants in `xdv-core/src`.
- Update docs after app API changes to keep signatures and status codes in sync.

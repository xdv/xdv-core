# xdv-core

Version: 0.1.0  
Status: Active  
Language: Dust Programming Language (DPL)

## Purpose

`xdv-core` contains XDV-specific system applications for base OS use and administration.

`xdv-shell` remains independent and is not part of `xdv-core`.

## Minimum Runtime Administration Set

The minimum app set covers administration of all required `xdv-runtime` domains:

- Console administration (`runtime_console`)
- Init and boot lifecycle administration (`runtime_init`)
- I/O administration (`runtime_io`)
- Memory administration (`runtime_memory`)
- Process administration (`runtime_process`)
- Scheduler administration (`runtime_scheduler`)
- String utilities administration (`runtime_string`)

## Additional Required Core Apps

Beyond the minimum runtime set, `xdv-core` includes additional applications needed for practical system administration:

- `sysmon`: runtime health and telemetry sampling
- `service`: service/task control workflows
- `log`: runtime/system log channel workflows
- `storage`: filesystem and storage administration workflows (via `xdv-xdvfs-utils`)
- `security`: permissions and ownership administration
- `recovery`: safe diagnostics and recovery workflows
- `runtime_admin`: orchestration entrypoints over all runtime admin apps

## Source Layout

`src/xdv_core_console_app.ds`  
Console administration.

`src/xdv_core_init_app.ds`  
Init and bootstrap administration.

`src/xdv_core_io_app.ds`  
I/O administration.

`src/xdv_core_memory_app.ds`  
Memory administration.

`src/xdv_core_process_app.ds`  
Process administration.

`src/xdv_core_scheduler_app.ds`  
Scheduler administration.

`src/xdv_core_string_app.ds`  
String utility administration.

`src/xdv_core_runtime_admin.ds`  
Runtime administration orchestration.

`src/xdv_core_sysmon_app.ds`  
Runtime telemetry and health.

`src/xdv_core_service_app.ds`  
Service/task control workflows.

`src/xdv_core_log_app.ds`  
Log channel administration.

`src/xdv_core_storage_app.ds`  
Storage and filesystem administration.

`src/xdv_core_security_app.ds`  
Permission and ownership administration.

`src/xdv_core_recovery_app.ds`  
Recovery and diagnostics.

`src/xdv_core_command_profile.ds`  
Command-oriented wrappers for each app (`console`, `init`, `io`, `memory`, `process`,
`scheduler`, `strings`, `runtime-admin`, `sysmon`, `service`, `log`, `storage`,
`security`, `recovery`, `cli`) mapped to runtime-relevant operations.

## Build

```bash
dust check xdv-core/src
```

---
scenario_id: scenario20
profile_name: scenario20_zombie_process_pid_exhaustion
domain_group: 🐧_4_LINUX_OS_FAILURES
environment_max_ram: 4GB
status: SCAFFOLDED
---

# Remediation Runbook: scenario20_zombie_process_pid_exhaustion

## Execution Vectors
1. **Trigger Fault Matrix:** Execute `chaos_injection.py` to breach normal state operational limits.
2. **Monitor Telemetry:** Verify that `watchdog_monitor.py` correctly reports anomalies.
3. **Enforce Remediation:** Invoke `automated_remediation.py` to restore baseline system operations.

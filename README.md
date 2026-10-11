# Multi-Vector Automated Chaos Orchestration Engine (`build_and_break`)

An enterprise-grade, zero-dependency Automated Chaos Orchestration platform engineered for systematic, programmatic failure injection and out-of-band real-time notification routing across isolated testing sandboxes.

## 🔬 System Target Layer & Runtime Environment
* **Host Architecture Context:** Apple Silicon M1 Pro Host
* **Guest Sandbox Runtime:** UTM Virtual Machine (Ubuntu ARM64 Server: `192.168.64.3`)
* **Compute Constraint Guardrail:** Hard hardware limit of **4GB RAM ceiling** for the virtual sandbox environment.
* **Supply Chain Surface Footprint:** **0% External Dependencies**. System utilizes strictly native Python 3 Standard Library primitives.

---

## 🛠️ Core Engine Architecture & Operational Components

```text
[ Infrastructure Core Management Plane ]
                    │
                    ▼ (Spawns background sub-process with unbuffered I/O)
 1. Local Isolated Sandboxes ➔ Watchdogs execute local POSIX filesystem polling.
                    │
                    ▼ (Dumps failure signatures directly to standard descriptors)
 2. Terminal Stream Pipe     ➔ Watchdog prints "[ERROR] CRITICAL_THRESHOLD_BREACHED".
                    │
                    ▼ (Dedicated non-blocking asynchronous listener thread)
 3. Central Core Engine      ➔ Interceptor thread extracts token line-by-line from memory buffer.
                    │
                    ▼ (Out-of-band native TCP socket handshake)
 4. Private Mail Gateway     ➔ Dispatches alert payload directly to internal intranet relay.
```

### 1. Management Plane Core (`build_and_break/core_engine/`)
* **`lab_generator.py`**: Handles dynamic directory scaffolding and configuration matrix asset generation.
* **`lab_orchestrator.py`**: Coordinates pipeline lifecycle execution, asynchronous background process stream monitoring, and centralized alert dispatch proxies.

### 2. Air-Gapped Notification Transport Layer
* **Network Target:** Internal Corporate Mail Gateway Relay (`192.168.64.10:25`).
* **Transport Protocol:** Native Python `smtplib` and `email.message` raw TCP sockets.
* **Network Isolation:** Fully air-gapped layout with **0% public WAN egress**, utilizing non-destructive socket validation handshakes to avoid port conflict vectors with active developer VS Code SSH remote tunnels.

---

## 📋 Standardized Domain Vector Taxonomy

The directory tree structure is systematically sorted alphanumeric-first to enforce flawless chronological sorting patterns natively across both local IDE sidebars and GitHub remote layouts:

```text
k3s-flux-chaos-labs/
└── build_and_break/
    ├── core_engine/
    │   ├── lab_generator.py
    │   └── lab_orchestrator.py
    └── Domain_Vector_Groups/
        ├── _1_NETWORKING_FAILURES/
        ├── _2_GITOPS_FAILURES/
        ├── _3_IAC_FAILURES/
        ├── _4_LINUX_OS_FAILURES/
        └── _5_SECURITY_FAILURES/
```

---

```text
>> Executing structural analysis checks...
Total Discovered Scenarios: 30 / 30
Total Conforming Sandboxes: 30 / 30
[PROCEED] Structural alignment verified. Pipeline ready for execution cycles. (Exit Code: 0)
```

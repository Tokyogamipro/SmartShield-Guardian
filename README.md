# SmartShield Guardian 🛡️

SmartShield Guardian is a high-performance security architecture eliminating the CPU lag vs. security trade-off via Zero-Baseline future tracking, GPU scan offloading, boot/external media checks, sandboxing, ransomware canary files, self-protection, and deep idle/shutdown scans.

---

## 🏗️ System Architecture & Core Pillars

SmartShield Guardian is built to resolve the traditional conflict between heavy system resource usage (CPU lag) and proactive threat protection through time-aware monitoring and hardware offloading:

* **Zero-Baseline (Future-Only) Strategy:** Skips massive initial scans of pre-existing files upon installation to prevent CPU bottlenecks, focusing live protection on future files and incoming data from the moment the shield is initialized.
* **GPU Acceleration:** Offloads scanning workloads and behavioral/pattern analysis to the GPU so the main CPU remains responsive for user tasks.
* **Scanning Lifecycle:**
  * **Startup Boot Scan:** Performs a fast, lightweight check of critical startup paths at boot time to verify a clean initial state.
  * **Real-Time & External Media Monitor:** Inspects new downloads, Bluetooth transfers, and external storage devices (such as USB flash drives) immediately as they enter the system, regardless of original file timestamps.
  * **Shutdown / Idle Deep Scan:** Runs a quiet background scan during system idle periods or shutdown to sanitize legacy disk content.
* **Advanced Security Layers:**
  * **Sandboxing:** Executes unknown or potentially suspicious files in an isolated environment to observe behavior before system release.
  * **Canary Files:** Places decoy files in sensitive locations to detect ransomware tampering immediately and trigger an emergency response.
  * **Self-Protection:** Protects the shield's own process and core integrity against unauthorized termination or tampering.

---

## 🗺️ System Architecture Workflow

```text
+-------------------------------------------------------------------+
|                     SMARTSHIELD GUARDIAN CORE                     |
+-------------------------------------------------------------------+
       |                                       |
       v                                       v
[STARTUP BOOT SCAN]                  [REAL-TIME FUTURE MONITOR]
- Verifies critical boot paths       - Tracks new files & media incoming
- Ensures clean initialization       - Offloads processing to GPU
       |                                       |
       +-------------------+-------------------+
                           |
                           v
          [EXTERNAL MEDIA & TRANSFERS MONITOR]
          - Instant inspection of USB drives, Bluetooth, Network
                           |
                           v
          [ADVANCED DEFENSE & DECEPTION LAYERS]
          - Sandbox: Isolates unknown zero-day file behaviors
          - Canary Files: Honeypots triggering instant ransomware lock
          - Self-Protection: Hardened kernel-level process integrity
                           |
                           v
          [SHUTDOWN / IDLE DEEP PAST-SCAN]
          - Quiet background sanitization of the entire disk
```

---

## 💻 Repository Structure & Prototypes

This repository provides two Python prototype implementations demonstrating the architectural workflow and defense logic, alongside a long-term roadmap toward low-level systems languages (**C++** or **Rust**) for kernel-level drivers and high-throughput OS integration:

| File | Role | Description |
| :--- | :--- | :--- |
| `guardian.py` | **Core Prototype** | Streamlined, zero-side-effect simulation illustrating the end-to-end defense lifecycle (boot check, Zero-Baseline tracking, GPU scan offloading, sandboxing, ransomware canary alert, and shutdown deep scan). |
| `guardian_extended.py` | **Extended Prototype** | Expanded object-oriented implementation featuring typed data structures (`dataclasses`, `Enum`), SHA-256 file hashing, local canary file deployment/verification, and quarantine staging. |

---

## ©️ Intellectual Property & Copyright

Copyright © 2026 **Brahim Hamlili**. All rights reserved.

This architecture, documentation, and associated prototype code are proprietary to **Brahim Hamlili** and governed by the repository's `LICENSE` terms.

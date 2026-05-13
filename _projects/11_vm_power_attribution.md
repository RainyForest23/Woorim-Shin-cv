---
layout: page
title: VM-level Power Attribution in Multi-tenant Environments
description: Capstone project measuring per-VM power consumption and interference effects in multi-tenant environments using hardware CT sensors, Intel RAPL, and KVM/QEMU
img: #
importance: 4
category: research
related_publications: false
---

## VM-level Power Attribution in Multi-tenant Environments

**2025 – 2026 | Python, Linux, KVM/QEMU | Capstone Project (Team 37 — OptimusPrime, Ewha Womans University)**

> [GitHub → Team37-OptimusPrime/vm-power-attribution](https://github.com/Team37-OptimusPrime/vm-power-attribution)

### Problem

Cloud billing models charge by resource allocation (vCPU, memory) regardless of actual energy consumed. But AI workloads and traditional workloads are not equal — running YOLO inference uses dramatically more power than a Node.js server, even with the same allocation. This project quantifies that gap and develops an attribution model to fairly assign energy costs to co-located VMs.

**Core hypothesis**: Resource-based billing ≠ Energy-based billing

### Key Findings

| Workload | Wall Power | Delta above idle |
|---|---|---|
| YOLO (AI) | 114.5W | +77W |
| Node.js (Non-AI) | 42.0W | +4W |

- **2.7× total power difference** and **18.3× delta difference** under identical 2-core / 4GB allocations
- Energy attribution error < 5% using hardware-level measurement stack

### What I Built

- **Hardware measurement stack**: RPICT4V3 CT sensor + Raspberry Pi for wall power, Intel RAPL for CPU, nvidia-smi for GPU
- **Workload isolation**: KVM/QEMU VMs with cgroup-based per-application energy measurement
- **Attribution algorithm**: Energy decomposition model assigning per-VM costs in concurrent multi-tenant scenarios
- **Analysis pipeline**: Python scripts for Phase 1 (host-level AI vs. non-AI) and Phase 1.5 (cgroup-based per-app measurement)

### Research Phases

- [x] **Phase 1**: Host-level AI vs. Non-AI power comparison
- [x] **Phase 1.5**: cgroup-based per-application energy measurement
- [ ] **Phase 2**: VM environment power attribution
- [ ] **Phase 3**: Energy-based billing model

### Hardware

- **Host**: Alienware Aurora R12 (Intel i7-11700F, RTX 3060)
- **Power Meter**: RPICT4V3 + Raspberry Pi
- **Virtualization**: KVM/QEMU + libvirt

### Technologies

**Measurement**: RPICT4V3 CT sensors, Intel RAPL, nvidia-smi
**Virtualization**: KVM/QEMU, libvirt, Linux cgroups
**Analysis**: Python (pandas, matplotlib), statistical modeling

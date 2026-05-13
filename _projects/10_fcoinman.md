---
layout: page
title: "fcoinman: Linux Server Compromise Detector"
description: Single-binary Linux compromise detector written in Rust — born from a real incident involving a CPU miner, GPU miner, and IRC botnet installed on my own server
img: #
importance: 3
category: systems
related_publications: false
---

## fcoinman: Linux Server Compromise Detector

**May 2026 | Rust | Independent Developer**

> [GitHub → RainyForest23/fcoinman](https://github.com/RainyForest23/fcoinman)

### Origin

My Ubuntu server started making loud fan noises at 3am. I logged in and found two processes I didn't recognize — `/usr/bin/socket` (XMRig CPU miner) and `/usr/bin/zsd` (Kaiten IRC bot) — quietly mining Monero and accepting shell commands from a C2 server at `d0wn.in`. The attacker had gotten in through SSH with password `password`.

fcoinman is the tool I wish I'd had running.

### What It Detects

| Category        | What it looks for                                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------------------------------ |
| **Processes**   | XMRig/P2PInfect cmdline signatures, high CPU since boot, execution from `/tmp` or `/dev/shm`                       |
| **Network**     | Connections to known mining pool IPs, stratum ports (3333/4444/5332), IRC ports (6667/6697)                        |
| **Persistence** | Systemd services with miner keywords, recently modified crons, `/etc/ld.so.preload` rootkits                       |
| **Files**       | SHA-256 matching against known malware IOC database, ELF strip detection, recently modified binaries in `/usr/bin` |
| **Accounts**    | UID-0 backdoor accounts in `/etc/passwd`, `root@root` SSH authorized_keys                                          |
| **Logs**        | Empty `auth.log` (evidence destruction), SSH brute force (>20 failures from same IP)                               |

### Sample Output

```
$ sudo fcoinman scan

[CRITICAL] UID-0 backdoor account detected
           Evidence: system:x:0:1001::/var/lib/system:/bin/sh

[CRITICAL] Systemd service contains miner signature
           Evidence: /etc/systemd/system/xorg.service: ExecStart=/usr/lib/xorg/Xorg --algo kawpow ...

[CRITICAL] Hash matches known malware (XMRig or Kaiten)
           /usr/bin/socket — SHA-256: 606ed3d826...

Results: LIKELY_COMPROMISED — 8 critical, 3 warnings
```

### Design Goals

Most Linux security tools (Wazuh, Falco, OSSEC) are designed for enterprise — complex agents, noisy output, steep setup. fcoinman is for the individual developer who notices something wrong and wants a straight answer in 5 seconds:

- No agents, no daemons, no config files
- Single static binary (~860KB), no dependencies
- JSON output mode for piping directly to AI assistants or scripts
- Verdict values: `LIKELY_COMPROMISED` / `SUSPICIOUS` / `CLEAN`

### Technologies

**Language**: Rust (cross-compiled to static x86_64 binary via musl-cross)
**Target**: Linux (x86_64), requires root for `/proc`, `/etc/passwd`, log access
**Distribution**: Single binary via GitHub Releases; curl-installable

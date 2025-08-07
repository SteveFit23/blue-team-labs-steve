# Blue-Team Labs — Stephen Simpkins

> Starter README for my cybersecurity home lab and portfolio. Day 1 publishes the lab architecture so I can iterate daily.

## Lab Architecture (v0)

```mermaid
flowchart TD
  HOST(Host PC) --> VB[VirtualBox]
  VB --> WIN[Win-Lab-1 (Windows 11)]
  VB --> UBU[Ubuntu-Atk-1 (Ubuntu 24.04 LTS)]
  WIN <-- Host-Only Network --> UBU
  WIN -->|NAT| Internet
  UBU -->|NAT| Internet
```
**Why two networks?**
- **NAT** gives both VMs safe internet access (updates/tools) without exposing them to your home network.
- **Host-Only** lets the VMs talk to each other privately for scans and detections.

## VM Plan
- **Win-Lab-1**: Windows 11, 2 vCPU, 4–6 GB RAM (use 2–4 GB if limited), 60 GB disk (dynamically allocated)
- **Ubuntu-Atk-1**: Ubuntu 24.04 LTS, 2 vCPU, 2–4 GB RAM, 30 GB disk
- VirtualBox Networks:  **Adapter 1 = NAT**, **Adapter 2 = Host-Only (vboxnet0)**

## Day 1 Log
- [x] Created GitHub repo `blue-team-labs-steve`
- [x] Installed VirtualBox
- [x] Downloaded Windows and Ubuntu ISOs
- [x] Published this architecture

## Next Up
Day 2–3: Build the Windows VM, enable logging (Security, PowerShell, Sysmon), and confirm events are visible.

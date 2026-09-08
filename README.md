# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP

## Week 1 – Cybersecurity Lab Setup

This project documents my Week 1 cybersecurity lab setup using VirtualBox and Kali Linux.

## Objectives

- Install and configure VirtualBox
- Import and configure Kali Linux
- Create a private NAT Network
- Configure Kali Linux network settings
- Verify network and internet connectivity
- Verify DNS resolution
- Create a clean VM snapshot
- Document the complete lab setup

## Lab Configuration

| Component | Configuration |
|---|---|
| Host OS | Windows 11 |
| Hypervisor | VirtualBox 7.2 |
| Guest OS | Kali Linux 2026.2 |
| Kali RAM | 2048 MB |
| Network Type | NAT Network |
| Network Name | NatNetwork |
| Network | 10.0.0.0/24 |
| Kali IP | 10.0.0.2/24 |
| Gateway | 10.0.0.1 |
| DNS | 8.8.8.8 |

## Network Verification

The following commands were used to verify the configuration:

```bash
ip a
ping 10.0.0.1
ping 8.8.8.8
nslookup networkwalks.com
nmap --version

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab environment for cybersecurity and ethical hacking practice**

![Kali Linux](https://img.shields.io/badge/Kali%20Linux-2026.2-557C94?style=flat-square)
![Linux](https://img.shields.io/badge/Skill-Linux-333333?style=flat-square)
![Penetration Testing](https://img.shields.io/badge/Penetration%20Testing-Lab-8A2BE2?style=flat-square)
![Virtualization](https://img.shields.io/badge/Skill-Virtualization-FF6600?style=flat-square)
![GitHub](https://img.shields.io/badge/Platform-GitHub-181717?style=flat-square)
![NetworkWalks](https://img.shields.io/badge/Training-NetworkWalks-00A86B?style=flat-square)
![Ethical Hacking](https://img.shields.io/badge/Focus-Ethical%20Hacking-B22222?style=flat-square)

---

## 📌 Project Overview

This project documents the setup of a controlled cybersecurity lab environment using VirtualBox and Kali Linux.

The purpose of this lab is to create a safe and isolated environment for learning cybersecurity concepts, networking, vulnerability assessment, penetration testing, and ethical hacking.

The lab uses a private NAT Network so that virtual machines can communicate with each other while maintaining a controlled network environment.

---

## 🎯 Objectives

The main objectives of this project are:

- Install and configure Oracle VirtualBox.
- Install and configure Kali Linux.
- Create a private NAT Network for the cybersecurity lab.
- Configure Kali Linux with a static IP address.
- Configure the correct gateway and DNS settings.
- Verify network connectivity.
- Verify DNS resolution and security tools.
- Create a clean snapshot of the configured Kali Linux machine.
- Document the complete lab setup process.
- Prepare the environment for future cybersecurity projects.

---

## 🛡️ Purpose of the Lab

The lab environment provides a controlled platform for practicing cybersecurity concepts without affecting unauthorized systems.

### Key purposes:

- 🖥️ Virtual machine management
- 🌐 Networking practice
- 🔍 Network scanning
- 🛡️ Vulnerability assessment
- 🧪 Penetration testing practice
- 🐧 Linux command-line practice
- 🔐 Security tool practice
- 📚 Cybersecurity learning

All activities performed in this environment are intended for educational and authorized security testing purposes only.

---

## 🏗️ Lab Architecture

The lab is designed using VirtualBox with Kali Linux connected to a private NAT Network.

```text
┌─────────────────────────────────────────────┐
│              Windows 11 Host                │
│                                             │
│        Intel Core i5-1135G7                 │
│              8 GB RAM                      │
│                                             │
│              VirtualBox 7.2.16              │
│                     │                       │
│                     ▼                       │
│              ┌──────────────┐               │
│              │  NatNetwork  │               │
│              │ 10.0.0.0/24  │               │
│              └──────┬───────┘               │
│                     │                       │
│                     ▼                       │
│            ┌─────────────────┐              │
│            │   Kali Linux    │              │
│            │   2026.2        │              │
│            │                 │              │
│            │ IP: 10.0.0.2    │              │
│            │ GW: 10.0.0.1    │              │
│            │ DNS: 8.8.8.8    │              │
│            └─────────────────┘              │
│                                             │
└─────────────────────────────────────────────┘
```

![Cybersecurity Lab Architecture](screenshots/1-lab-architecture.png)

---

## ⚙️ Lab Configuration

| **🧩 Component** | **⚙️ Configuration** |
|---|---|
| 🖥️ Host Operating System | Windows 11 |
| 💻 Processor | Intel Core i5-1135G7 |
| 🧠 Host RAM | 8 GB |
| 📦 Hypervisor | VirtualBox 7.2.16 |
| 🐧 Guest OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Network Type | NAT Network |
| 🔗 Network Name | `NatNetwork` |
| 📡 Network Range | `10.0.0.0/24` |
| 💻 Kali IP Address | `10.0.0.2/24` |
| 🚪 Gateway | `10.0.0.1` |
| 🌍 DNS | `8.8.8.8` |
| 📦 DHCP | Enabled |
| 🌐 IPv6 | Disabled |
| 🔢 Future VM Range | `10.0.0.3 – 10.0.0.99` |

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip can be used to extract the Kali Linux VirtualBox image if required.

Download and install 7-Zip on the Windows host system.

```text
7-Zip
https://www.7-zip.org/
```

---

## Step 2. Install VirtualBox

Oracle VirtualBox was installed as the virtualization platform for this cybersecurity lab.

The installed version is:

```text
VirtualBox 7.2.16
```

VirtualBox provides the environment required to run Kali Linux as a virtual machine.

```text
https://www.virtualbox.org/wiki/Downloads
```

---

## Step 3. Create the NAT Network

A private NAT Network named `NatNetwork` was configured in VirtualBox.

### Network configuration

```text
Name:              NatNetwork
IPv4 Prefix:       10.0.0.0/24
DHCP Enabled:      Yes
IPv6:              Disabled
```

The network provides the following addressing structure:

```text
Network:           10.0.0.0/24
Gateway:           10.0.0.1
Kali Linux:        10.0.0.2
Future VMs:        10.0.0.3 - 10.0.0.99
```

> 📸 **VirtualBox NAT Network Screenshot**  
> Screenshot will be added here.

---

## Step 4. Import Kali Linux

The official Kali Linux VirtualBox image was imported into VirtualBox.

The Kali Linux version used for this lab is:

```text
Kali Linux 2026.2
```

The virtual machine was configured with:

```text
RAM:             2048 MB
Network Adapter: Adapter 1
Attached to:     NAT Network
Network Name:    NatNetwork
Adapter Type:    Intel PRO/1000 MT Desktop (82540EM)
```

> 📸 **Kali Linux Virtual Machine Screenshot**  
> Screenshot will be added here.

---

## Step 5. Configure Kali Linux Network

The Kali Linux network interface was configured to use the private NAT Network.

### Network configuration

```text
IP Address:       10.0.0.2/24
Subnet Mask:      255.255.255.0
Gateway:          10.0.0.1
DNS:              8.8.8.8
```

The network interface used by Kali Linux is:

```text
eth0
```

The configuration was verified using:

```bash
ip a
```

The default route was verified using:

```bash
ip route
```

Expected route:

```text
default via 10.0.0.1 dev eth0
```

> 📸 **Kali Linux Network Settings Screenshot**  
> Screenshot will be added here.

---

## Step 6. Verify Network Connectivity

The connection between Kali Linux and the NAT Network gateway was tested.

### Test Gateway

```bash
ping -c 4 10.0.0.1
```

### Test Internet Connectivity

```bash
ping -c 4 8.8.8.8
```

### Test DNS Resolution

```bash
nslookup networkwalks.com
```

### Verify Nmap

```bash
nmap --version
```

These tests help confirm that the Kali Linux network configuration is working correctly.

---

## Step 7. Create a Clean VM Snapshot

After completing the basic configuration, a clean snapshot can be created so that the configured Kali Linux environment can be restored later.

Recommended snapshot name:

```text
Clean Kali - Network Setup
```

The snapshot provides a clean starting point for future cybersecurity exercises.

> 📸 **Snapshot Screenshot**  
> Screenshot will be added here.

---

# 🔎 Lab Verification

| **🔍 Test** | **📋 Command** | **✅ Expected Result** |
|---|---|---|
| Interface Check | `ip a` | `eth0` has `10.0.0.2/24` |
| Gateway Test | `ping -c 4 10.0.0.1` | Gateway responds |
| Internet Test | `ping -c 4 8.8.8.8` | Internet connectivity works |
| DNS Test | `nslookup networkwalks.com` | Domain resolves |
| Nmap Check | `nmap --version` | Nmap version displayed |
| Route Check | `ip route` | Default route via `10.0.0.1` |

### Verification Commands

```bash
ip a
ip route
ping -c 4 10.0.0.1
ping -c 4 8.8.8.8
nslookup networkwalks.com
nmap --version
```

---

# 🐞 Problems Encountered & Solutions

## Problem 1. Kali Linux Network Connectivity

During the lab setup, network connectivity required checking the VirtualBox NAT Network and Kali Linux network configuration.

### Solution

The following configuration was checked and corrected:

```text
VirtualBox Network:
NAT Network → NatNetwork

Network:
10.0.0.0/24

Kali IP:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

After correcting the network configuration, the Kali Linux interface was able to communicate through the configured NAT Network.

---

## Problem 2. Network Interface Verification

The Kali Linux network interface was checked to ensure that the correct interface was active.

The interface was verified using:

```bash
ip a
```

The active interface was:

```text
eth0
```

The configured IP address was:

```text
10.0.0.2/24
```

---

# 💡 What I Learned

Through this lab setup, I learned the fundamentals of building a controlled cybersecurity environment.

### 1. Virtualization

I learned how VirtualBox can be used to create and manage virtual machines for cybersecurity practice.

### 2. Kali Linux

I learned how to install and configure Kali Linux as a cybersecurity testing platform.

### 3. Virtual Networking

I learned how to create and configure a NAT Network using VirtualBox.

### 4. IP Addressing

I learned how IP addresses, subnet masks, gateways, and DNS work together in a network.

### 5. Linux Networking Commands

I practiced commands such as:

```bash
ip a
ip route
ping
nslookup
```

### 6. Network Verification

I learned how to verify connectivity between Kali Linux, the gateway, and external network resources.

### 7. Cybersecurity Lab Preparation

I learned how to prepare a controlled environment for future vulnerability assessment and penetration testing activities.

### 8. Documentation

I learned how to document a technical cybersecurity project using GitHub and Markdown.

---

# 🔐 Security & Ethical Use

This cybersecurity lab is intended strictly for educational and authorized security testing.

All scanning, vulnerability assessment, penetration testing, and other security activities should only be performed on:

- Systems owned by me
- Systems for which I have explicit permission
- Intentionally vulnerable training environments
- Authorized cybersecurity labs

Unauthorized scanning or exploitation of systems may be illegal and unethical.

**Always follow responsible disclosure and applicable cybersecurity laws.**

---

# 🔗 Tools & Resources

### Tools

- Oracle VirtualBox
- Kali Linux
- Nmap
- 7-Zip
- GitHub

### Official Resources

- [VirtualBox](https://www.virtualbox.org/)
- [Kali Linux](https://www.kali.org/)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)
- [7-Zip](https://www.7-zip.org/)
- [GitHub](https://github.com/)

---

# 📸 Screenshots

The following screenshots will be added to document the lab setup:

1. **Title / Lab Environment**
2. **VirtualBox NAT Network Configuration**
3. **Kali Linux Virtual Machine**
4. **Kali Linux Network Configuration**
5. **Clean Snapshot**
6. **Network Verification**

> Screenshots will be added after completing the GitHub image upload process.

---

# 👤 Author

**Srinivas Kalyan**

Information Technology Graduate  
Cybersecurity Learner

---

## 📌 Project Information

| **📋 Field** | **📄 Details** |
|---|---|
| 🎓 Training | NetworkWalks Cybersecurity Internship |
| 📅 Week | Week 1 |
| 📚 Project | Cybersecurity Lab Environment Setup |
| 👨‍💻 Batch | B083 |
| 🐧 Operating System | Kali Linux 2026.2 |
| 🖥️ Hypervisor | VirtualBox 7.2.16 |
| 🌐 Network | `10.0.0.0/24` |
| 💻 Kali IP | `10.0.0.2` |
| 🚪 Gateway | `10.0.0.1` |
| 🌍 DNS | `8.8.8.8` |
| 📂 Platform | GitHub |

---

## 🏁 Conclusion

This project successfully documents the creation of a controlled cybersecurity lab environment using VirtualBox and Kali Linux.

The configured environment provides a safe foundation for practicing networking, reconnaissance, vulnerability assessment, penetration testing, and other cybersecurity activities in future projects.

---

**🔐 Learn • Practice • Secure**

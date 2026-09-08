# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP

## Week 1 – Cybersecurity Lab Setup

This project documents my Week 1 cybersecurity lab setup using Oracle VirtualBox and Kali Linux.

The purpose of this lab is to build a controlled cybersecurity environment for learning networking, system configuration, vulnerability assessment, and future security projects.

---

## Project Overview

This project is part of the Networkwalks Cybersecurity Internship – Week 1.

The lab focuses on building a basic cybersecurity environment using Oracle VirtualBox and Kali Linux. The environment includes a private NAT Network, static IPv4 configuration, connectivity verification, DNS testing, and a clean virtual machine snapshot.

---

## Objectives

The main objectives of this Week 1 lab are:

- Install and configure Oracle VirtualBox
- Import and configure Kali Linux
- Create a private NAT Network
- Configure Kali Linux network settings
- Assign a static IP address
- Configure gateway and DNS
- Verify network connectivity
- Verify internet connectivity
- Verify DNS resolution
- Verify Nmap installation
- Create a clean virtual machine snapshot
- Document the complete lab setup

---

## Purpose of the Lab

This lab provides a controlled environment for cybersecurity learning and future practical exercises.

Kali Linux is used as the primary cybersecurity workstation, while Oracle VirtualBox provides the virtualization environment.

The private NAT Network provides controlled communication between virtual machines while keeping the laboratory environment separated from the physical network.

---

## Lab Architecture

The basic laboratory architecture is:

```text
                    Internet
                       |
                       |
                Windows 11 Host
                       |
                       |
                Oracle VirtualBox
                       |
                       |
                   NatNetwork
                  10.0.0.0/24
                       |
                       |
                  Kali Linux
                 10.0.0.2/24
                       |
             -------------------
             |                 |
        Gateway              DNS
        10.0.0.1           8.8.8.8




Lab Configuration
Component	Configuration
Host Operating System	Windows 11
Hypervisor	Oracle VirtualBox 7.2
Guest Operating System	Kali Linux 2026.2
Kali RAM	2048 MB
Network Type	NAT Network
Network Name	NatNetwork
Network Address	10.0.0.0/24
Kali IP Address	10.0.0.2/24
Subnet Mask	255.255.255.0
Gateway	10.0.0.1
DNS Server	8.8.8.8
Adapter Type	Intel PRO/1000 MT Desktop
Lab Setup Procedure
Step 1 – Install Oracle VirtualBox

Oracle VirtualBox was installed on the Windows 11 host system.

VirtualBox is used to create and manage the Kali Linux virtual machine.

Step 2 – Import Kali Linux

The Kali Linux 2026.2 VirtualBox image was imported into Oracle VirtualBox.

The virtual machine was configured with 2048 MB of RAM and the Intel PRO/1000 MT Desktop network adapter.

Step 3 – Create NAT Network

A private NAT Network named NatNetwork was created in VirtualBox.

The following configuration was used:

Setting	Value
Network Name	NatNetwork
IPv4 Prefix	10.0.0.0/24
DHCP	Enabled
IPv6	Disabled
Step 4 – Configure Kali Linux Network

Kali Linux was configured with the following IPv4 settings:

Setting	Value
Method	Manual
IP Address	10.0.0.2
Netmask	255.255.255.0
Gateway	10.0.0.1
DNS	8.8.8.8

The Kali Linux network adapter was connected to the NatNetwork.

Step 5 – Verify Network Configuration

The network configuration was checked using:

ip a

The routing configuration was checked using:

ip route

Gateway connectivity was tested using:

ping -c 4 10.0.0.1

Internet connectivity was tested using:

ping -c 4 8.8.8.8

DNS resolution was tested using:

nslookup networkwalks.com

Nmap installation was checked using:

nmap --version
Step 6 – Create a Clean Snapshot

A clean snapshot was created after completing the basic Kali Linux and network configuration.

The snapshot provides a known baseline that can be restored before future cybersecurity exercises.

Snapshot name:

Clean Kali - Network Setup

Lab Verification

The following commands were used to verify the laboratory configuration:

ip a
ip route
ping -c 4 10.0.0.1
ping -c 4 8.8.8.8
nslookup networkwalks.com
nmap --version
Verification Checklist
 Kali network interface is up
 Kali has IP address 10.0.0.2
 Gateway 10.0.0.1 is reachable
 Internet connectivity is working
 DNS resolution is working
 Nmap is installed
 Clean snapshot is created
Problems Encountered & Solutions
Problem – Network Connectivity

During the initial network configuration, connectivity to the configured gateway and internet required troubleshooting.

The VirtualBox NAT Network configuration and Kali Linux IPv4 settings were checked to ensure that the network, IP address, gateway, and DNS settings matched.

Solution

The NAT Network was configured as:

Network: 10.0.0.0/24
Gateway: 10.0.0.1
Kali IP: 10.0.0.2
DNS: 8.8.8.8

The Kali Linux network adapter was connected to the correct NatNetwork.

After correcting the configuration, network connectivity was restored.

What I Learned

During this Week 1 lab, I learned:

How virtualization works using Oracle VirtualBox
How to import and configure a Kali Linux virtual machine
The difference between NAT and NAT Network
How to create a private virtual network
Basic IPv4 configuration
Static IP address configuration
Gateway and DNS configuration
Basic network connectivity testing
DNS resolution testing
Basic Nmap verification
How VM snapshots can be used for recovery
The importance of documenting cybersecurity lab configurations
Security & Ethical Use

This cybersecurity laboratory is intended for educational and authorized security testing only.

All scanning, testing, and security activities should be performed only against systems and networks that I own or have explicit permission to test.

Unauthorized security testing of third-party systems or networks is not permitted.

Tools & Resources
Tools Used
Oracle VirtualBox
Kali Linux
Nmap
NetworkManager
Linux Terminal
Technologies
IPv4
NAT Network
DNS
Virtualization
TCP/IP Networking
Resources
Kali Linux Documentation
Oracle VirtualBox Documentation
Networkwalks Cybersecurity Internship Lab Instructions
Screenshots

Screenshots documenting the actual laboratory configuration will be added to this repository.

The screenshots will include:

VirtualBox configuration
NAT Network configuration
Kali Linux environment
Kali Linux IPv4 configuration
Network verification
Virtual machine snapshot
Author

Srinivas Kalyan

Information Technology Graduate
Cybersecurity Learner

Project Information
Item	Details
Project	Cybersecurity Lab Setup
Week	Week 1
Batch	B083
Environment	Oracle VirtualBox + Kali Linux
Network	10.0.0.0/24
Kali IP	10.0.0.2
Purpose	Cybersecurity Training Lab
Conclusion

The Week 1 cybersecurity laboratory environment was configured using Oracle VirtualBox and Kali Linux.

The completed environment provides a controlled foundation for practicing networking and cybersecurity concepts and for conducting future authorized cybersecurity exercises.

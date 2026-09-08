# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP

## Week 1 – Cybersecurity Lab Setup

This project documents my Week 1 cybersecurity lab setup using Oracle VirtualBox and Kali Linux.

The purpose of this lab is to build a controlled cybersecurity environment for learning networking, system configuration, vulnerability assessment, and future security projects.

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
- Verify DNS resolution
- Verify Nmap installation
- Create a clean virtual machine snapshot
- Document the complete lab setup

---

## Purpose of the Lab

This lab provides a controlled environment for cybersecurity learning.

Kali Linux is configured as the primary cybersecurity workstation, while VirtualBox provides the virtualization environment.

The private NAT Network allows virtual machines to communicate within the configured network while maintaining separation from the physical network.

---

## Lab Architecture

The lab uses the following basic network design:

```text
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
       |
 Gateway: 10.0.0.1
 DNS: 8.8.8.8
 LAB CONFIGURATION
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
Step 1 – Install VirtualBox

Oracle VirtualBox was installed on the Windows 11 host system.

VirtualBox is used to create and manage the Kali Linux virtual machine.

Step 2 – Import Kali Linux

The Kali Linux virtual machine was imported into Oracle VirtualBox.

The Kali Linux virtual machine was configured with approximately 2048 MB of RAM.

Step 3 – Create NAT Network

A NAT Network named NatNetwork was created in VirtualBox.

The following IPv4 configuration was used:

Network: 10.0.0.0/24
DHCP: Enabled
IPv6: Disabled

The NAT Network provides a private network for the virtual machines.

Step 4 – Configure Kali Linux

Kali Linux was configured with the following IPv4 settings:

IP Address: 10.0.0.2
Netmask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8

The network adapter was connected to the NatNetwork.

Step 5 – Verify Network Configuration

The network configuration was checked using:

ip a

The routing configuration can be checked using:

ip route

Connectivity to the gateway can be tested using:

ping 10.0.0.1

Internet connectivity can be tested using:

ping 8.8.8.8

DNS resolution can be tested using:

nslookup networkwalks.com

Nmap installation can be checked using:

nmap --version
Step 6 – Create a Clean Snapshot

A clean snapshot of the Kali Linux virtual machine was created after completing the basic network configuration.

The snapshot can be used to restore the virtual machine to a known working state before future cybersecurity exercises.

Network Verification

The following commands were used to verify the lab configuration:

ip a
ping 10.0.0.1
ping 8.8.8.8
nslookup networkwalks.com
nmap --version

The results of these commands were used to verify the Kali Linux network configuration and basic connectivity.

Problems Encountered & Solutions
Problem 1 – Network Connectivity

During the initial network configuration, connectivity to the gateway and internet required troubleshooting.

The VirtualBox NAT Network configuration and Kali Linux IPv4 settings were checked to ensure that the network, IP address, gateway, and DNS settings matched.

Solution

The NAT Network was configured as:

Network: 10.0.0.0/24
Gateway: 10.0.0.1
Kali IP: 10.0.0.2
DNS: 8.8.8.8

The Kali network adapter was connected to the correct NatNetwork.

What I Learned

During this lab, I learned:

How virtualization works using VirtualBox
How to import and configure a Kali Linux virtual machine
Difference between NAT and NAT Network
How to create a private virtual network
Basic IPv4 configuration
Static IP address configuration
Gateway and DNS configuration
Basic network connectivity testing
DNS resolution testing
Basic Nmap verification
How VM snapshots can be used for recovery
Importance of documenting cybersecurity lab configurations
Security & Ethical Use

This cybersecurity lab is intended for educational purposes.

All scanning, testing, and security activities should only be performed on systems and networks that I own or have explicit permission to test.

Unauthorized security testing of systems or networks is not permitted.

Tools & Resources
Tools Used
Oracle VirtualBox
Kali Linux
Nmap
NetworkManager
Terminal
Technologies
IPv4
NAT Network
DNS
Virtualization
TCP/IP networking
Screenshots

Screenshots documenting the actual lab configuration will be added to this repository.

The screenshots include:

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

The Week 1 cybersecurity lab environment was configured using Oracle VirtualBox and Kali Linux.

The lab provides a controlled environment for practicing networking and cybersecurity concepts and will be used as the foundation for future cybersecurity projects.

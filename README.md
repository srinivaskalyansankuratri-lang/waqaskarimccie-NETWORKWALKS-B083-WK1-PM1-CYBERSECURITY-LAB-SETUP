🔐 Cybersecurity Lab Environment Setup
Week 1 – Networkwalks Cybersecurity Internship | Batch B083

Building an isolated virtual laboratory using Oracle VirtualBox and Kali Linux for cybersecurity learning, networking, vulnerability assessment, and authorized security-testing practice.

📌 Project Overview

This project documents my Week 1 Cybersecurity Lab Setup using Oracle VirtualBox and Kali Linux.

The purpose of this lab is to create a controlled and isolated cybersecurity environment where networking concepts, system configuration, vulnerability assessment, reconnaissance, and future security-testing activities can be performed safely.

The laboratory uses a private NAT Network so that additional virtual machines can be added later as targets for authorized cybersecurity exercises.

🎯 Objectives

The main objectives of this Week 1 lab are:

Install and configure Oracle VirtualBox.
Install/import Kali Linux as a virtual machine.
Create a private NAT Network.
Configure Kali Linux network settings.
Assign a consistent/static IP address.
Configure the default gateway and DNS.
Verify network connectivity.
Verify Internet connectivity.
Verify DNS resolution.
Verify Nmap installation.
Create a clean virtual-machine snapshot.
Document the complete laboratory setup.
Prepare the environment for future cybersecurity projects.
🛡️ Purpose of the Lab

This laboratory provides a controlled environment for cybersecurity learning and authorized security testing.

The environment can be used for future activities such as:

Network reconnaissance
Port scanning
Vulnerability assessment
Packet analysis
Web security testing
Exploitation practice
Security-tool experimentation

⚠️ Ethical Use: This laboratory must only be used against systems and networks that I own or have explicit permission to test. Unauthorized security testing of third-party systems or networks is not permitted.

🏗️ Lab Architecture

The current laboratory consists of a Windows 11 host system running Oracle VirtualBox with a Kali Linux virtual machine connected to a private NAT Network.

Additional target virtual machines can be added to the same network in future cybersecurity projects.

                         Internet
                            │
                            │
                     Windows 11 Host
                            │
                            │
                    Oracle VirtualBox
                            │
                            │
                      NatNetwork
                     10.0.0.0/24
                            │
                            │
                      Kali Linux
                    10.0.0.2/24
                       /         \
                      /           \
                 Gateway          DNS
                10.0.0.1        8.8.8.8

⚙️ Lab Configuration
Component	Configuration
🖥️ Host Operating System	Windows 11
🧰 Hypervisor	Oracle VirtualBox 7.2
🐉 Guest Operating System	Kali Linux 2026.2
🧠 Kali RAM	2048 MB
🌐 Network Type	NAT Network
📡 Network Name	NatNetwork
🌍 Network Address	10.0.0.0/24
🐧 Kali IP Address	10.0.0.2/24
🔢 Subnet Mask	255.255.255.0
🚪 Default Gateway	10.0.0.1
🌎 DNS Server	8.8.8.8
🔌 Adapter Type	Intel PRO/1000 MT Desktop
🔮 Future VM Range	10.0.0.3–10.0.0.99
🪜 Lab Setup Procedure
Step 1 – Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive.

Tool: 7-Zip

Step 2 – Install Oracle VirtualBox

Oracle VirtualBox was installed on the Windows 11 host system.

VirtualBox is used to create and manage the Kali Linux virtual machine and the virtual networking environment required for the cybersecurity laboratory.

Step 3 – Create the NAT Network

A dedicated NAT Network named NatNetwork was created in Oracle VirtualBox.

NAT Network Configuration
Setting	Value
Network Name	NatNetwork
IPv4 Prefix	10.0.0.0/24
DHCP	Enabled
IPv6	Disabled

A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with each other while also having outbound network connectivity.

This provides a suitable foundation for future attacker and target virtual machines.

Step 4 – Import Kali Linux

The Kali Linux 2026.2 virtual machine was imported into Oracle VirtualBox.

The VM was configured with:

Setting	Value
RAM	2048 MB
Network	NAT Network
Network Name	NatNetwork
Adapter Type	Intel PRO/1000 MT Desktop
VirtualBox Network Adapter
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop


A shared folder was also configured for transferring required files between the Windows host and Kali Linux VM.

Step 5 – Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

IPv4 Configuration
Setting	Value
Method	Manual
IP Address	10.0.0.2
Subnet Mask	255.255.255.0
Gateway	10.0.0.1
DNS	8.8.8.8

A consistent IP address makes it easier to document the laboratory and reference the Kali Linux machine during future cybersecurity exercises.

Step 6 – Verify the Network Configuration

The Kali Linux network configuration was verified using the following commands.

Check IP Address
ip a


This command was used to verify the assigned IP address and network interface status.

Check Routing Table
ip route


This command was used to verify the configured default gateway and routing information.

Test Gateway Connectivity
ping -c 4 10.0.0.1


The gateway was tested to confirm communication between Kali Linux and the NAT Network gateway.

Test Internet Connectivity
ping -c 4 8.8.8.8


Internet connectivity was tested using Google's public DNS server.

Test DNS Resolution
nslookup networkwalks.com


DNS resolution was tested to confirm that domain names could be resolved successfully.

Verify Nmap Installation
nmap --version


The Nmap installation and version were verified.

🔄 Step 7 – Create a Clean VM Snapshot

After completing the initial Kali Linux and network configuration, a clean VirtualBox snapshot was created.

Snapshot Name
Clean Kali - Network Setup


The snapshot provides a known-good baseline for the cybersecurity laboratory.

If future cybersecurity exercises modify or damage the virtual machine configuration, the VM can be restored to this clean baseline.

🔎 Lab Verification

The following tests were used to verify the laboratory configuration.

Test	Command	Expected Result
🌐 Check IP address	ip a	Correct Kali IP displayed
📡 Check routing	ip route	Correct gateway displayed
🚪 Test gateway	ping -c 4 10.0.0.1	Successful replies
🌍 Test Internet	ping -c 4 8.8.8.8	Successful replies
🔎 Test DNS	nslookup networkwalks.com	Domain resolves successfully
🧰 Verify Nmap	nmap --version	Nmap version displayed
✅ Verification Checklist
 Kali Linux network interface configured
 Kali Linux assigned IP address 10.0.0.2
 Gateway configured as 10.0.0.1
 DNS configured as 8.8.8.8
 Gateway connectivity tested
 Internet connectivity tested
 DNS resolution tested
 Nmap installation verified
 Clean VM snapshot created
🛠️ Problems Encountered & Solutions
Problem – Network Connectivity

During the initial network configuration, connectivity to the configured gateway and Internet required troubleshooting.

The VirtualBox NAT Network configuration and Kali Linux IPv4 settings were checked to ensure that the network, IP address, gateway, and DNS settings matched.

Solution

The NAT Network was configured as follows:

Network:   10.0.0.0/24
Gateway:   10.0.0.1
Kali IP:   10.0.0.2
DNS:       8.8.8.8


The Kali Linux network adapter was connected to the correct NatNetwork.

After correcting the configuration, network connectivity was restored.

📚 What I Learned

During this Week 1 laboratory setup, I learned:

How virtualization works using Oracle VirtualBox.
How to import and configure a Kali Linux virtual machine.
The difference between NAT and NAT Network.
How to create a private virtual network.
Basic IPv4 network configuration.
Static IP address configuration.
Gateway and DNS configuration.
Basic network connectivity testing.
DNS resolution testing.
Basic Nmap verification.
How VM snapshots can be used for recovery.
The importance of documenting cybersecurity laboratory configurations.
🔐 Security & Ethical Use

This cybersecurity laboratory is intended for educational and authorized security testing only.

All scanning, testing, and security activities should be performed only against systems and networks that I own or have explicit permission to test.

Unauthorized security testing of third-party systems or networks is not permitted.

🧰 Tools & Technologies
Tools Used
Oracle VirtualBox 7.2
Kali Linux 2026.2
Nmap
NetworkManager
Linux Terminal
7-Zip
Technologies
IPv4
NAT Network
DNS
TCP/IP Networking
Virtualization
📸 Screenshots

Screenshots documenting the actual laboratory configuration will be added to this repository.

The following evidence will be included:

VirtualBox configuration
NAT Network configuration
Kali Linux virtual machine
Kali Linux IPv4 configuration
Network verification
VM snapshot

📌 Screenshots will be added in the next step.

👤 Author

Srinivas Kalyan

Information Technology Graduate
Cybersecurity Learner

📋 Project Information
Item	Details
Project	Cybersecurity Lab Setup
Week	Week 1
Batch	B083
Environment	Oracle VirtualBox + Kali Linux
Network	10.0.0.0/24
Kali IP	10.0.0.2
Purpose	Cybersecurity Training Lab
🏁 Conclusion

The Week 1 cybersecurity laboratory environment was configured using Oracle VirtualBox and Kali Linux.

The completed environment provides a controlled foundation for practicing networking and cybersecurity concepts and for conducting future authorized cybersecurity exercises.

The laboratory is designed to be expanded with additional virtual machines and security-testing scenarios in future projects.

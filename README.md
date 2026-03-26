# Virtual Enterprise Homelab – Proxmox Infrastructure

## Overview
This project is a virtual enterprise homelab built using Proxmox virtualization.  
The purpose of this lab is to gain hands-on experience with system administration, networking, Active Directory, and infrastructure management by simulating a small business network environment.

The lab currently includes a Proxmox host, Windows Server Domain Controller, and Windows client virtual machines. Future plans include file servers, Linux servers, monitoring, and firewall configuration.

---

## Network Diagram
*(Insert network diagram image here later)*

Example topology:

Router (192.168.1.1)  
│  
Proxmox Host (192.168.1.82)  
│  
├── DC01 – Windows Server Domain Controller (192.168.1.10)  
└── W10-ADM – Windows Admin Workstation (192.168.1.30)  

---

## Technologies Used
- Proxmox VE (Virtualization)
- Windows Server 2022
- Active Directory Domain Services
- DNS
- Windows 10
- VirtIO Drivers
- Linux (Proxmox Host)
- Networking (Static IP, DNS, Domain Join)

---

## Configuration Steps

### Proxmox Setup
- Installed Proxmox VE on physical server
- Configured network bridge and static IP
- Accessed Proxmox web interface
- Uploaded ISO images for Windows Server and Windows 10
- Created virtual machines for servers and clients

### Windows Server / Active Directory
- Installed Windows Server 2022
- Installed VirtIO storage and network drivers
- Configured static IP address
- Installed Active Directory Domain Services
- Promoted server to Domain Controller
- Created domain: homelab.local
- Configured DNS

### Windows 10 Admin Workstation
- Created Windows 10 virtual machine
- Installed VirtIO drivers
- Configured static IP and DNS
- Connected workstation to Domain Controller network
- Preparing workstation for domain join and RSAT tools

---

## Troubleshooting Log (Challenges Faced)

| Issue | Cause | Solution |
|------|------|---------|
| Could not access Proxmox web interface | Network configuration issue | Verified IP settings and network bridge configuration |
| Proxmox booted into emergency mode | Invalid mount entry in fstab | Edited /etc/fstab and removed invalid mount |
| Windows Server installer could not detect disk | Missing VirtIO storage drivers | Loaded VirtIO drivers during installation |
| Windows Server had no network adapter | Missing VirtIO network drivers | Installed NetKVM driver |
| VM booted into PXE instead of ISO | Boot order misconfigured | Changed boot order in VM settings |
| Windows 10 could not join domain | Windows 10 Home edition | Upgraded to Windows 10 Pro |
| DNS name homelab.local not resolving | DNS configuration issue | Verified DC DNS settings and client DNS configuration |

---

## Skills Demonstrated
- Virtualization (Proxmox)
- Windows Server Administration
- Active Directory
- DNS Configuration
- Windows Client Administration
- Networking (IP, Gateway, DNS)
- Linux Server Basics
- Troubleshooting Infrastructure Issues

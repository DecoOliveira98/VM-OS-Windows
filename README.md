# 🖥️ Active Directory Virtual Lab - Domain-214.abc

This repository documents the creation and configuration of a virtual lab using VirtualBox to simulate an Active Directory environment with two Windows Server 2022 machines.

## ⚙️ Environment Overview

- **Virtualization:** VirtualBox
- **Operating System:** Windows Server 2022 (GUI)
- **VMs Created:**
  - `DC-2024214`: Domain Controller
  - `Web-2024214`: Web Server (domain-joined)

## 🌐 Network Configuration

Both VMs have two network adapters:
- **Adapter 1 (NAT):** Internet access via DHCP
- **Adapter 2 (Internal Network - `intnet`):** Static IP for domain communication

| VM Name       | IP Address     | Subnet Mask   | Gateway      | DNS               |
|--------------|----------------|---------------|--------------|-------------------|
| DC-2024214   | 172.16.0.100   | 255.255.0.0   | 172.16.0.1   | 127.0.0.1         |
| Web-2024214  | 172.16.0.200   | 255.255.0.0   | 172.16.0.1   | 172.16.0.100      |

## 🛠️ Configuration Steps

### Domain Controller (`DC-2024214`)
- Renamed the machine using PowerShell
- Set static IP on internal adapter
- Installed **Active Directory Domain Services (AD DS)**
- Promoted to Domain Controller with domain name:




### Web Server (`Web-2024214`)
- Renamed the machine using Server Manager
- Set static IP on internal adapter
- Joined the domain `Domain-214.abc` using the domain admin account

### Active Directory Setup
- Created two Organizational Units (OUs):
- `Accounting-Dublin`
- `Sales-Dublin`
- Created users and assigned them to appropriate groups within their OUs

## ✅ Validation

- Verified connectivity between VMs using `ping`
- Confirmed domain join from Web Server
- Successfully logged in with domain credentials
- Users and OUs visible and manageable in ADUC

## 📌 Notes

- Internet access handled through NAT (DHCP)
- Internal domain traffic isolated via `intnet`
- `.vdi` files are not included in this repository

---

## 👤 Author

Active Directory Lab – OS CA1  
Student: Andre Luiz Oliveira 


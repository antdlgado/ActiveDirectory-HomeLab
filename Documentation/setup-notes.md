# Active Directory Home Lab Setup

## Project Overview
Created a home lab environment to practice Active Directory administration and help desk support scenarios.

## Lab Environment
- **Hypervisor**: Oracle VirtualBox 7.0
- **Domain Controller OS**: Windows Server 2022 Standard Evaluation
- **Domain Name**: homelab.local
- **Domain Controller Name**: DC01-Server2022
- **DC IP Address**: 192.168.1.10
- **DNS Server**: 127.0.0.1 (localhost)

## Objectives
- Set up a functional Active Directory domain controller
- Practice enterprise networking configuration
- Learn domain management fundamentals
- Prepare for help desk scenarios involving user/computer management

---

## Step 1: Environment Setup

### ISO Files Preparation
Downloaded Windows Server 2022 evaluation ISO from Microsoft Evaluation Center for the 180-day free trial.

![ISO Files](../Screenshots/01-iso-files.png)

### VirtualBox VM Configuration
Created a new virtual machine with the following specifications:
- **Name**: DC01-Server2022
- **Type**: Microsoft Windows
- **Version**: Windows 2022 (64-bit)
- **Memory**: 4096 MB (4 GB)
- **Storage**: 50 GB (dynamically allocated VDI)

![VM Settings](../Screenshots/02-vm-settings.png)

---

## Step 2: Windows Server Installation

### Server Edition Selection
Installed Windows Server 2022 Standard Evaluation (Desktop Experience) on the virtual machine.

![Server Edition Selection](../Screenshots/03-server-edition.png)

### Initial Server Setup
Successfully completed installation and reached the Server Manager dashboard.

![Server OS Setup](../Screenshots/04-server-os-setup.png)

![Server Desktop](../Screenshots/05-server-desktop.png)

---

## Step 3: Network Configuration

### Static IP Assignment
Configured static IP addressing for the domain controller to ensure stable DNS and AD services:
- IP: 192.168.1.10
- Subnet: 255.255.255.0
- Gateway: 192.168.1.1
- DNS: 127.0.0.1 (points to itself for AD integration)

![Static IP Configuration](../Screenshots/06-static-ip.png)

**Why static IP?** Domain controllers require static IPs because they provide DNS services to the domain. Clients need a consistent IP to find the DC.

---

## Step 4: Active Directory Domain Services Installation

### Adding the AD DS Role
Used Server Manager to add the Active Directory Domain Services role to the server.

![Add Roles Wizard](../Screenshots/07-add-roles-wizard.png)

![AD DS Role Selected](../Screenshots/08-ad-role-selected.png)

Installation completed successfully.

![Installation Complete](../Screenshots/09-installation-complete.png)

---

## Step 5: Domain Controller Promotion

### Promoting to Domain Controller
Promoted the server to a domain controller by creating a new Active Directory forest.

![Promotion Notification](../Screenshots/10-promote-notification.png)

Configured the domain with name "homelab.local" and set the DSRM recovery password.

![Domain Configuration](../Screenshots/11-domain-config.png)

All prerequisites passed successfully, and the installation proceeded.

![Prerequisites Check](../Screenshots/12-prerequisites-check.png)

---

## Step 6: Verification and Testing

### Successful Domain Controller Deployment
After automatic restart, the login screen now displays "HOMELAB\Administrator" confirming the domain was created successfully.

![Login Screen](../Screenshots/13-login-screen.png)

Server Manager displays both AD DS and DNS roles active on the server.

![Server Manager with Roles](../Screenshots/14-server-manager-roles.png)

### Active Directory Console Access
Successfully accessed Active Directory Users and Computers, showing the homelab.local domain structure with default organizational units.

![AD Users and Computers](../Screenshots/15--ad-users-computers.png)

---

## Key Learnings

### Technical Concepts
- **Domain Controller vs Member Server**: Learned the critical differences between a domain controller (which hosts AD DS and authenticates users) and a regular member server
- **DNS Integration**: Understood why domain controllers must also run DNS and why DNS is pointed to localhost (127.0.0.1)
- **Static IP Requirements**: Learned that DCs require static IPs to provide reliable services to domain members
- **Forest vs Domain**: Understood that "homelab.local" is both a forest root domain and a domain in this single-domain environment

### Practical Skills Gained
- Virtual machine creation and configuration
- Windows Server installation and initial setup
- Network adapter configuration for enterprise environments
- Role-based installation using Server Manager
- Domain controller promotion process
- Active Directory console navigation

### Help Desk Relevance
This lab provides the foundation for common help desk tasks:
- Understanding domain user accounts vs local accounts
- Troubleshooting domain join issues
- Resetting domain passwords
- Managing user permissions and group memberships
- Understanding why users need to be on the domain network to authenticate

---

## Next Steps

1. Create organizational units (OUs) for different departments
2. Add domain user accounts
3. Create a Windows 10 client VM and join it to the domain
4. Practice common help desk scenarios:
   - Password resets
   - Account unlocks
   - Group membership changes
   - User creation/deletion
5. Implement Group Policy for security settings
6. Document troubleshooting procedures

---

## Challenges Encountered

- Initial confusion about which Windows Server edition to choose (learned that "Desktop Experience" provides the GUI)
- Understanding the relationship between DNS and Active Directory
- Ensuring proper network configuration before promoting to DC

---

## Resources Used

- Microsoft Evaluation Center for Windows Server 2022 ISO
- Oracle VirtualBox documentation
- Microsoft documentation on Active Directory Domain Services

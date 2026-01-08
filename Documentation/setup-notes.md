# Active Directory Home Lab Setup

## Project Overview
Created a comprehensive home lab environment to practice Active Directory administration and help desk support scenarios. This project demonstrates both infrastructure deployment and day-to-day user management tasks that are essential for IT support roles.

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
- Create and manage user accounts across multiple departments
- Implement organizational units (OUs) for departmental structure
- Configure security groups for access management
- Practice common help desk scenarios
- Demonstrate technical documentation skills

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

## Step 7: Creating Organizational Structure

### Organizational Units (OUs)
Created departmental OUs to organize users by business function, mirroring real-world enterprise AD structures.

![Create OU Dialog](../Screenshots/16-create-ou-dialog.png)

Created four organizational units:
- IT_Department
- Sales_Department
- HR_Department
- Management

![All OUs Created](../Screenshots/17-all-ous-created.png)

**Why use OUs?** Organizational Units allow administrators to apply Group Policies, delegate administrative permissions, and organize objects logically by department, location, or function.

---

## Step 8: User Account Management

### Creating Domain Users
Practiced creating user accounts with proper naming conventions and security settings.

![New User Menu](../Screenshots/18-new-user-menu.png)

![User Creation Dialog](../Screenshots/19-john-smith-user-dialog.png)

![Password Settings](../Screenshots/20-user-password-settings.png)

### IT Department Users
Created three user accounts in the IT_Department OU:
- John Smith (jsmith)
- Sarah Johnson (sjohnson)
- Mike Williams (mwilliams)

![IT Department Users](../Screenshots/21-it-department-users.png)

### Sales Department Users
Created three user accounts in the Sales_Department OU:
- Emily Davis (edavis)
- Robert Brown (rbrown)
- Lisa Martinez (lmartinez)

![Sales Department Users](../Screenshots/22-sales-department-users.png)

### HR Department Users
Created two user accounts in the HR_Department OU:
- Jennifer Taylor (jtaylor)
- David Anderson (danderson)

![HR Department Users](../Screenshots/23-hr-department-users.png)

### Management Users
Created two user accounts in the Management OU:
- Michael Chen (mchen)
- Patricia Wilson (pwilson)

![Management Users](../Screenshots/24-management-users.png)

### Complete User Overview
Total of 10 domain user accounts created across all departments.

![All Departments Overview](../Screenshots/25-all-departments-overview.png)

---

## Step 9: Security Group Management

### Creating Security Groups
Implemented security groups for department-based access control and permission management.

![Create Group Dialog](../Screenshots/26-create-group-dialog.png)

### Adding Group Members
Added users to their respective departmental security groups.

![Add Group Members](../Screenshots/27-add-group-members-dialog.png)

![IT Team Members](../Screenshots/28-it-team-members.png)

### Groups and Users Together
Each department now contains both user accounts and a corresponding security group.

![IT Department with Group](../Screenshots/29-it-department-with-group.png)

**Why security groups?** Groups allow administrators to assign permissions to multiple users simultaneously rather than managing each user individually. This is critical for efficient access control in enterprise environments.

---

## Step 10: Help Desk Scenario Simulations

### Scenario 1: Password Reset
Practiced resetting a user's password and requiring them to change it at next logon - one of the most common help desk tasks.

![Reset Password Dialog](../Screenshots/30-reset-password-dialog.png)

**Real-world application:** Users frequently forget passwords or need them reset for security reasons. This demonstrates the standard password reset procedure.

### Scenario 2: Account Property Management
Reviewed user account properties including the unlock account option, which is used when users are locked out after too many failed login attempts.

![Account Properties Tab](../Screenshots/31-account-properties-tab.png)

**Real-world application:** Account lockouts are a common help desk call. Understanding where to find and use the unlock function is essential.

### Scenario 3: Disabling User Accounts
Practiced disabling a user account (used when employees leave the company or accounts need to be temporarily suspended).

![Disabled User Icon](../Screenshots/32-disabled-user-icon.png)

**Real-world application:** When employees leave, IT must disable their accounts immediately to prevent unauthorized access. The visual indicator (down arrow) helps administrators quickly identify disabled accounts.

### Scenario 4: Cross-Department Group Membership
Added a user from Management to the IT_Team group, demonstrating how users can have permissions across multiple departments.

![Member of Multiple Groups](../Screenshots/33-member-of-multiple-groups.png)

![IT Team with Cross-Department Member](../Screenshots/37-member-of-multiple-groups-2.png.png)

**Real-world application:** Users often need access to resources outside their primary department. Managers might need IT access, or project teams might span departments.

### Scenario 5: User Information Management
Reviewed user general properties where contact information, job titles, and other details are stored.

![User General Properties](../Screenshots/34-user-general-properties.png)

**Real-world application:** Help desk staff often need to update user information or look up contact details when assisting with tickets.

---

## Step 11: Final Configuration Overview

### Complete Active Directory Structure
Successfully implemented a fully functional Active Directory environment with organized departmental structure, user accounts, and security groups.

![Final AD Structure](../Screenshots/35-final-ad-structure.png)

![Sales Department Final View](../Screenshots/36-sales-department-final.png)

---

## Key Learnings

### Technical Concepts Mastered
- **Domain Controller vs Member Server**: Understanding the critical differences between a domain controller (which hosts AD DS and authenticates users) and a regular member server
- **DNS Integration**: Learned why domain controllers must also run DNS and why DNS is pointed to localhost (127.0.0.1)
- **Static IP Requirements**: Domain controllers require static IPs to provide reliable services to domain members
- **Forest vs Domain**: "homelab.local" is both a forest root domain and a domain in this single-domain environment
- **Organizational Units**: Using OUs to logically organize users and apply policies by department
- **Security Groups vs Distribution Groups**: Security groups control access; distribution groups are for email lists
- **Group Scope**: Global groups can contain users from the same domain and be used anywhere in the forest

### Practical Skills Gained
- Virtual machine creation and configuration
- Windows Server installation and initial setup
- Network adapter configuration for enterprise environments
- Role-based installation using Server Manager
- Domain controller promotion process
- Active Directory console navigation
- Creating and organizing organizational units
- User account creation with proper naming conventions
- Security group creation and member management
- Password reset procedures
- Account lockout troubleshooting
- Disabling/enabling user accounts
- Managing group memberships across departments
- Understanding user account properties and settings

### Help Desk Relevance
This lab provides hands-on experience with the most common help desk tasks:

**Daily Tasks:**
- Password resets (performed dozens of times per day in most help desks)
- Account unlocks after failed login attempts
- Adding users to security groups for resource access
- Looking up user information and contact details
- Verifying user account status

**Occasional Tasks:**
- Creating new user accounts for new employees
- Disabling accounts for departing employees
- Modifying group memberships for role changes
- Managing cross-departmental access

**Troubleshooting Skills:**
- Understanding domain user accounts vs local accounts
- Identifying why users can't log in (disabled account, expired password, locked account)
- Recognizing domain connectivity issues vs credential problems
- Understanding the authentication flow in enterprise environments

---

## Challenges Encountered and Solutions

### Challenge 1: Windows Server Edition Selection
**Problem:** Initial confusion about which Windows Server edition to install.

**Solution:** Learned that "Desktop Experience" provides the GUI, while the standard edition is command-line only. Desktop Experience is essential for learning and most help desk environments.

### Challenge 2: DNS and Active Directory Relationship
**Problem:** Understanding why DNS must point to localhost (127.0.0.1).

**Solution:** Active Directory relies on DNS for service location records (SRV records). The domain controller must be able to find itself via DNS for AD to function properly.

### Challenge 3: Network Configuration Timing
**Problem:** Ensuring proper network configuration before promoting to domain controller.

**Solution:** Learned that static IP and DNS configuration must be completed before AD DS installation to avoid connectivity issues.

### Challenge 4: Password Policy Conflicts
**Problem:** "User must change password at next logon" checkbox was grayed out during password reset.

**Solution:** Discovered that "Password never expires" and "Must change password" are mutually exclusive settings. Modified the account properties to enable the password change requirement.

---

## Real-World Applications

### Enterprise Environment Parallels
This lab mirrors real enterprise Active Directory implementations:

- **Multiple Departments**: Organizations use OUs to separate departments, locations, or business units
- **Security Groups**: Access to file shares, applications, and resources is controlled through group membership
- **Naming Conventions**: Username format (first initial + last name) is standard in many organizations
- **Help Desk Workflows**: The scenarios practiced are the exact tasks performed daily in IT support roles

### Interview Preparation
This project provides concrete examples for interview questions:

- "Have you worked with Active Directory?" → Yes, I built a domain from scratch
- "Can you reset passwords?" → Yes, I practiced this in my home lab
- "Do you understand OUs and groups?" → Yes, I created a departmental structure with security groups
- "Have you managed user accounts?" → Yes, I created 10 accounts and managed their properties

---

## Technical Documentation Skills Demonstrated

### Throughout This Project:
- Clear step-by-step procedures
- Visual documentation with screenshots
- Explanation of "why" behind technical decisions
- Real-world context for each skill
- Troubleshooting documentation
- Professional formatting and organization

These documentation skills are valuable for:
- Creating knowledge base articles
- Writing standard operating procedures (SOPs)
- Training new help desk staff
- Maintaining department documentation

---

## Future Enhancements

### Phase 2 Planned Additions:
- [ ] Create a Windows 10 client VM and join it to the domain
- [ ] Configure and test domain user login from client machine
- [ ] Implement Group Policy Objects (GPOs) for:
  - Password policies
  - Screen lock timeouts
  - Software deployment
  - Desktop wallpaper standardization
- [ ] Set up file shares with NTFS permissions
- [ ] Practice mapped network drives
- [ ] Configure printer deployment via Group Policy

### Phase 3 Advanced Topics:
- [ ] Implement DHCP server role
- [ ] Configure DNS forwarding
- [ ] Create multiple sites and subnets
- [ ] Practice Active Directory backup and restore
- [ ] Implement fine-grained password policies
- [ ] Set up Active Directory Recycle Bin
- [ ] Configure auditing and security logs

---

## Lessons Learned

### Technical Growth:
- Hands-on practice is far more valuable than just reading about concepts
- Breaking complex projects into smaller steps makes them manageable
- Documentation during the process is easier than trying to recreate it later
- Understanding the "why" behind configurations aids in troubleshooting

### Professional Development:
- Portfolio projects demonstrate initiative and self-directed learning
- Real-world scenarios in labs translate directly to job competencies
- Clear documentation showcases communication skills valued by employers
- GitHub provides a professional platform to display technical work

---

## Resources Used

- Microsoft Evaluation Center for Windows Server 2022 ISO
- Oracle VirtualBox documentation
- Microsoft Active Directory documentation
- Best practices for AD organizational structure
- Help desk standard operating procedures research

---

## Conclusion

This Active Directory home lab project successfully demonstrates the core competencies required for help desk and IT support roles. From infrastructure deployment to daily user management tasks, the hands-on experience gained directly translates to workplace scenarios.

The project showcases technical ability, problem-solving skills, attention to detail, and the capacity to learn complex enterprise systems independently. Most importantly, it provides concrete evidence of practical skills that employers are seeking in IT support candidates.

**Project Status**: Complete and ready for expansion
**Total Time Investment**: Approximately 8-10 hours
**Skills Demonstrated**: 15+ core IT support competencies
**Documentation**: Comprehensive with 37 screenshots

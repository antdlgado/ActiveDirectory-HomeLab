# Active Directory Home Lab

![Project Status](https://img.shields.io/badge/status-complete-success.svg)
![Windows Server](https://img.shields.io/badge/Windows%20Server-2022-blue.svg)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Configured-green.svg)

## Overview
A comprehensive hands-on home lab project demonstrating Active Directory deployment, configuration, and administration. This project showcases both infrastructure setup and day-to-day user management tasks essential for help desk and IT support roles.

## Project Highlights
- ✅ Deployed Windows Server 2022 domain controller from scratch
- ✅ Configured Active Directory Domain Services with proper DNS integration
- ✅ Created organizational structure with 4 departmental OUs
- ✅ Managed 10 user accounts across multiple departments
- ✅ Implemented security groups for access control
- ✅ Practiced common help desk scenarios (password resets, account management)
- ✅ Documented entire process with 37 detailed screenshots

## Technologies Used
- **Virtualization**: Oracle VirtualBox 7.0
- **Operating System**: Windows Server 2022 Standard Evaluation
- **Services**: Active Directory Domain Services (AD DS), DNS
- **Networking**: Static IP configuration, TCP/IP fundamentals
- **Administration Tools**: Active Directory Users and Computers, Server Manager

## Lab Environment

### Infrastructure
- **Domain**: homelab.local
- **Domain Controller**: DC01-Server2022 (192.168.1.10)
- **Forest Functional Level**: Windows Server 2016
- **DNS Configuration**: Self-hosted on domain controller

### Organizational Structure
```
homelab.local
├── IT_Department (3 users + IT_Team security group)
├── Sales_Department (3 users + Sales_Team security group)
├── HR_Department (2 users + HR_Team security group)
└── Management (2 users)
```

### User Accounts Created
- **IT Department**: John Smith, Sarah Johnson, Mike Williams
- **Sales Department**: Emily Davis, Robert Brown, Lisa Martinez
- **HR Department**: Jennifer Taylor, David Anderson
- **Management**: Michael Chen, Patricia Wilson

## Skills Demonstrated

### Infrastructure & Configuration
- Virtual machine deployment and resource allocation
- Windows Server 2022 installation and initial configuration
- Static IP addressing for enterprise environments
- DNS server configuration and integration
- Active Directory Domain Services role installation
- Domain controller promotion and forest creation

### User & Access Management
- Creating organizational units (OUs) for departmental structure
- User account creation with naming conventions
- Security group creation and management
- Adding users to multiple groups
- Cross-departmental access configuration

### Help Desk Operations
- Password reset procedures
- Account unlock capabilities
- Disabling/enabling user accounts
- Managing user properties and contact information
- Understanding account lockout scenarios
- Group membership modifications

### Documentation & Communication
- Step-by-step technical documentation
- Visual documentation with screenshots
- Explaining technical concepts in clear language
- Creating reference materials for future use

## Real-World Applications

This lab directly mirrors enterprise IT environments and prepares for:

**Daily Help Desk Tasks:**
- Resetting forgotten passwords
- Unlocking accounts after failed login attempts
- Adding users to security groups for resource access
- Looking up user information
- Verifying account status

**Periodic Administrative Tasks:**
- Creating accounts for new employees
- Disabling accounts for departing employees
- Modifying access when employees change roles
- Managing cross-departmental permissions

**Troubleshooting Scenarios:**
- Identifying why users cannot log in
- Understanding domain vs. local authentication
- Recognizing DNS-related AD issues
- Diagnosing account lockout causes

## Documentation

Comprehensive documentation with detailed explanations and 37 screenshots can be found in the [Documentation](./Documentation/) folder.

The documentation includes:
- Complete setup procedures
- Network configuration details
- User and group management workflows
- Help desk scenario demonstrations
- Troubleshooting notes and lessons learned
- Real-world application context

## What I Learned

### Technical Knowledge
- How Active Directory authentication works in enterprise environments
- The critical relationship between DNS and Active Directory
- Why domain controllers require static IP addresses
- The difference between security groups and distribution groups
- How organizational units enable policy management and delegation
- The significance of forest and domain functional levels

### Practical Experience
- Deploying enterprise infrastructure from scratch
- Following best practices for AD naming and structure
- Managing user lifecycles (creation, modification, disabling)
- Understanding the full authentication flow
- Troubleshooting common AD issues
- Creating maintainable documentation

### Professional Skills
- Self-directed learning and problem-solving
- Breaking complex projects into manageable steps
- Technical writing and documentation
- Thinking from a help desk perspective
- Understanding end-user impact of administrative changes

## Future Enhancements

### Planned Next Steps
- [ ] Deploy Windows 10 client VM and join to domain
- [ ] Test domain authentication from client machine
- [ ] Implement Group Policy Objects (GPOs) for security settings
- [ ] Configure file shares with NTFS permissions
- [ ] Set up mapped network drives via Group Policy
- [ ] Deploy printer objects through Active Directory
- [ ] Practice Group Policy troubleshooting with gpresult

### Advanced Topics to Explore
- [ ] DHCP server role configuration
- [ ] Active Directory backup and restore procedures
- [ ] Fine-grained password policies
- [ ] Active Directory Recycle Bin
- [ ] Multi-site Active Directory topology
- [ ] Active Directory auditing and reporting

## Challenges Overcome

**Challenge**: Password policy checkbox was grayed out during reset
**Solution**: Learned about conflicting password policies ("never expires" vs. "must change at next logon") and modified account settings accordingly

**Challenge**: Understanding DNS configuration for domain controller
**Solution**: Researched the relationship between AD and DNS, learned why DC points DNS to itself (127.0.0.1) for proper service location

**Challenge**: Selecting correct Windows Server edition
**Solution**: Learned the difference between standard and "Desktop Experience" editions, understanding when GUI vs. command-line is appropriate

## Why This Project Matters

This project demonstrates:
- **Initiative**: Self-directed learning outside of formal employment
- **Practical Skills**: Hands-on experience with enterprise technologies
- **Job Readiness**: Direct preparation for help desk responsibilities
- **Problem-Solving**: Ability to troubleshoot and research solutions
- **Documentation**: Professional communication of technical processes
- **Commitment**: Invested 8-10 hours to build comprehensive skills

## Project Metrics
- **Time Investment**: 8-10 hours
- **User Accounts Created**: 10
- **Organizational Units**: 4
- **Security Groups**: 3
- **Help Desk Scenarios Practiced**: 5
- **Screenshots Documented**: 37
- **Lines of Documentation**: 600+

## Contact & Connect

**Anthony Lombardo**
- 📧 Email: anthonylombardodelgado@gmail.com
- 💼 LinkedIn: [linkedin.com/in/anthony-lombardo](https://www.linkedin.com/in/anthony-lombardo)
- 📍 Location: Palm Bay, FL
- 🎓 Education: A.A. in Information Technology (Expected Dec 2026)
- 🏆 Certifications: CompTIA Security+ (March 2025)

---

## Acknowledgments

This project was built as part of my portfolio development to demonstrate hands-on IT skills for help desk and system administration roles. Special thanks to the IT community for sharing knowledge and best practices that guided this implementation.

---

*This is a personal educational project. All work was completed independently to develop practical IT support skills.*

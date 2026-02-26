# Windows-Active-Directory-Labs
📌 Here I take you through the different work arounds while setting up, configuring and working with windows active directory domain services.

### 📌 Overview
This repository contains hands-on labs demonstrating the deployment, configuration, and management of a Windows Server Active Directory enterprise environment.

#### The labs simulate a small enterprise infrastructure including:
- Active Directory Domain Services (AD DS)
- Organizational Unit (OU) design
- Domain security policies
- DHCP & Routing configuration
- Network Address Translation (NAT)
- Domain client onboarding
- PowerShell automation for bulk user provisioning

#### This lab environment was built to strengthen practical skills in:
- Windows Server Administration
- Active Directory Management
- Enterprise Network Services
- Infrastructure Automation
- Security-focused AD configuration

#### 🖥 Lab Environment

  | Component            | Technology Used            |
|----------------------|----------------------------|
| Domain Controller    | Windows Server 2019        |
| Client Systems       | Windows 10                 |
| Virtualization       | VirtualBox / VMware        |
| Services Deployed    | AD DS, DHCP, Routing, NAT  |
| Automation           | PowerShell      
  
#### 🧱 Lab Structure
* ##### 🔹 01 – Core AD Deployment
- Network adapter configuration
- Active Directory installation
- Domain Controller promotion
- OU hierarchy design
- Admin user delegation
- Password policy configuration
- Client domain join verification

#### 📂 01-Core-AD-Deployment/
* ##### 🔹 02 – Networking, DHCP & Routing
- Internal network design
- Static IP assignment
- DHCP role installation
- DHCP scope configuration
- Scope activation
- Client IP validation
- Multi-client connectivity testing
  
#### 📂 02-Networking-DHCP-Routing/
* ##### 🔹 03 – AD Automation & Remote Access
- Remote Access role installation
- Routing and NAT configuration
- PowerShell bulk user creation
- Automated OU assignment
- Verification of scripted provisioning

#### 📂 03-Automation-Scripting/
* ##### 🎯 Skills Demonstrated
- Active Directory infrastructure deployment
- Enterprise OU design and delegation
- Group Policy configuration
- Windows Server role management
- DHCP implementation
- NAT & routing configuration
- PowerShell scripting for automation
- Domain client onboarding and validation

#### 🔐 Security Focus
This lab was designed with security awareness in mind:
* Strong password enforcement
* Structured administrative OU separation
* Controlled domain access testing
* Service role segmentation

#### Future enhancements may include:
+ AD attack surface testing
+ Kerberos abuse simulations
+ Misconfiguration detection labs
+ Defensive monitoring exercises

### 📎 Author
Built as part of hands-on infrastructure and cybersecurity practice.

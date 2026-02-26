# ⚙️ Lab 03 – Active Directory Automation & Remote Access Configuration

---

## 📌 Objective

Enhance the Active Directory infrastructure by:

- Installing and configuring Remote Access services
- Enabling Routing and NAT functionality
- Automating bulk user provisioning using PowerShell
- Assigning users to specific Organizational Units (OUs)
- Validating automated object creation in Active Directory

This lab demonstrates administrative automation and infrastructure service consolidation within a Windows Server environment.

---

## 🖥 Lab Environment

| Component | Configuration |
|------------|--------------|
| Server Role | Windows Server 2019 |
| Services Configured | Remote Access, RRAS, NAT |
| Automation Tool | PowerShell |
| Directory Structure | Multiple OUs for user segregation |

---

# 🧱 Infrastructure Enhancement

The Domain Controller was extended to provide:

- Routing between internal and external networks
- Network Address Translation (NAT)
- Automated user account provisioning

This reflects real-world small to mid-sized enterprise deployments where a single server may perform multiple roles.

---

# 🔧 Implementation Steps

---

## 1️⃣ Install Remote Access Role

Installed the Remote Access role to enable routing services.

![Remote Access Role Installation](screenshots/01-remote-access-role-install.png)

---

## 2️⃣ Configure Routing and Remote Access (RRAS)

Enabled LAN routing to allow packet forwarding between network interfaces.

![RRAS Configuration](screenshots/02-rras-configuration.png)

---

## 3️⃣ Configure NAT

Configured NAT to:

- Use external adapter for internet access
- Translate private internal IP addresses
- Allow internal clients outbound internet connectivity

![NAT Configuration](screenshots/03-nat-configuration.png)

---

# 🤖 Active Directory Automation

---

## 4️⃣ PowerShell Bulk User Creation Script

Created a PowerShell script to automate user account provisioning.

The script:

- Creates multiple users
- Assigns default passwords
- Forces password change at first login
- Places users in designated OUs

Script example:

```powershell
Import-Module ActiveDirectory

$Users = @(
    @{Name="John Doe"; Sam="jdoe"; OU="OU=Users,DC=lab,DC=local"},
    @{Name="Jane Smith"; Sam="jsmith"; OU="OU=HR,DC=lab,DC=local"}
)

foreach ($User in $Users) {
    New-ADUser `
        -Name $User.Name `
        -SamAccountName $User.Sam `
        -UserPrincipalName "$($User.Sam)@lab.local" `
        -Path $User.OU `
        -AccountPassword (ConvertTo-SecureString "P@ssw0rd123" -AsPlainText -Force) `
        -Enabled $true `
        -ChangePasswordAtLogon $true
}


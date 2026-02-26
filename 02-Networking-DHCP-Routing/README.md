# 🌐 Lab 02 – Networking, DHCP & Routing Configuration

---

## 📌 Objective

Configure core network infrastructure services to support the Active Directory environment, including:

- Internal network configuration
- Routing role installation
- NAT configuration
- DHCP deployment
- DHCP scope configuration
- Client IP address validation

This lab enables automated IP addressing and controlled network routing within the enterprise lab environment.

---

## 🖥 Lab Environment

| Component | Configuration |
|------------|--------------|
| Domain Controller | Windows Server 2019 |
| Clients | Windows 10 |
| Network Design | Internal + External Adapter |
| DHCP Server | Hosted on Domain Controller |
| Routing & NAT | Enabled on Domain Controller |

---

# 🧱 Network Architecture Overview

The Domain Controller performs multiple infrastructure roles:

- Active Directory
- DNS
- DHCP Server
- Routing & NAT

The setup includes:

- One External Adapter (Internet Access)
- One Internal Adapter (Enterprise Network)
- Multiple domain-connected clients receiving IP via DHCP

---

# 🔧 Implementation Steps

---

## 1️⃣ Configure Internal Network Adapter (Static IP)

Configured the internal adapter with a static IP address to serve as:

- Gateway for internal clients
- DHCP server address
- DNS server address

![Internal Adapter Configuration](screenshots/01-internal-adapter-config.png)

---

## 2️⃣ Install Routing Role (Remote Access)

Installed the Remote Access role to enable routing and NAT services.

![Routing Role Installation](screenshots/02-routing-role-install.png)

---

## 3️⃣ Configure Routing & NAT

Configured Routing and Remote Access (RRAS):

- Enabled LAN routing
- Configured NAT
- Assigned external adapter for internet translation
- Assigned internal adapter for private network

![Routing Configuration](screenshots/03-routing-config.png)

---

## 4️⃣ Install DHCP Server Role

Installed the DHCP role via Server Manager.

![DHCP Role Installation](screenshots/04-dhcp-role-install.png)

---

## 5️⃣ Configure DHCP Scope

Created DHCP scope for internal network:

- Defined IP address range
- Configured subnet mask
- Assigned default gateway (DC internal IP)
- Set DNS server to Domain Controller

![DHCP Scope Configuration](screenshots/05-dhcp-scope-config.png)

---

## 6️⃣ Activate DHCP Scope

Activated the configured DHCP scope to allow address distribution.

![DHCP Scope Activated](screenshots/06-dhcp-scope-active.png)

---

## 7️⃣ Validate Client IP Assignment

Verified client receives IP address automatically via DHCP using:

```bash
ipconfig /all


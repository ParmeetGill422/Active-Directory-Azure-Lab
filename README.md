# 🏢 Active Directory Azure Lab

> **Hybrid Identity Lab** — On-premises Active Directory deployed on Azure VM, synced to Microsoft Entra ID using Entra Connect Sync with GPO enforcement and user provisioning across IT, HR, and Security OUs.

![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![OS](https://img.shields.io/badge/OS-Windows%20Server%202025-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![AD](https://img.shields.io/badge/Active%20Directory-Hybrid%20Identity-orange?style=for-the-badge)

---

## 📌 Project Overview

This project simulates a real **enterprise hybrid identity environment** from the ground up. An Azure Virtual Machine running Windows Server 2025 was configured as a Domain Controller for the `parmeet.local` domain. Active Directory was built out with Organizational Units, users, and security groups across IT, HR, and Security departments.

Group Policy Objects were created to enforce password complexity and account lockout policies across the domain. Microsoft Entra Connect Sync was then installed to synchronize all on-premises identities to Microsoft Entra ID using Password Hash Synchronization — completing a full hybrid identity setup that mirrors what enterprises use in production today.

This type of architecture is used by companies like **Amazon, Microsoft, Boeing, and most Fortune 500 organizations**.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Microsoft Azure | Cloud platform hosting the VM infrastructure |
| Windows Server 2025 | Operating system for the Domain Controller |
| Active Directory Domain Services (AD DS) | On-premises identity and access management |
| Microsoft Entra ID (Azure AD) | Cloud-based identity platform |
| Microsoft Entra Connect Sync | Hybrid identity synchronization tool |
| Group Policy Management (GPMC) | Policy enforcement across the domain |
| DNS Server | Domain name resolution for parmeet.local |

---

## 🏗️ What Was Built

### Phase 1 — Azure Virtual Machine
- Deployed a VM named **DC01** running **Windows Server 2025 Datacenter**
- Region: Canada Central
- Size: Standard B2ls v2 (2 vCPUs, 4 GiB RAM)
- Resource Group: Personal-Project

### Phase 2 — Active Directory Domain Services
- Installed the AD DS role via Server Manager
- Promoted DC01 to a **Domain Controller**
- Created the domain: **parmeet.local**
- DNS and AD DS services confirmed live

### Phase 3 — Organizational Units, Users, and Groups

| Organizational Unit | Users | Security Group |
|---|---|---|
| IT | 2 users | IT-Admins |
| HR | 2 users | HR-Staff |
| Security | 2 users | Security-Analysts |

- Created **6 user accounts** across all OUs
- Created **3 security groups** with users assigned as members
- Followed enterprise naming conventions throughout

### Phase 4 — Group Policy Objects (GPOs)

**Password-Policy GPO** — linked to parmeet.local
| Setting | Value |
|---|---|
| Minimum password length | 12 characters |
| Complexity requirements | Enabled |
| Maximum password age | 90 days |
| Enforce password history | 10 passwords |

**Account-Lockout-Policy GPO** — linked to parmeet.local
| Setting | Value |
|---|---|
| Account lockout threshold | 5 invalid attempts |
| Account lockout duration | 30 minutes |
| Reset lockout counter after | 15 minutes |

### Phase 5 — Microsoft Entra Connect Sync
- Downloaded and installed **Microsoft Entra Connect Sync** on DC01
- Selected **Password Hash Synchronization** as the sign-in method
- Connected on-premises `parmeet.local` to **Microsoft Entra ID**
- All 6 on-premises users successfully synced to the cloud
- Sync status: **Enabled** — Last sync: confirmed successful

---

## 📸 Screenshots

### Active Directory Users and Computers — parmeet.local Domain
![AD Users and Computers](<https://github.com/user-attachments/assets/82cdcb18-0e74-4f9f-884f-7611b4f26493>)

---

### Microsoft Entra ID — Synced Users from On-Premises AD
![Entra ID Synced Users](<https://github.com/user-attachments/assets/55b4abb7-c343-45ea-adda-b8f53cdb0249>)

---

### Group Policy Management — Password-Policy GPO
![Group Policy Management](<https://github.com/user-attachments/assets/c9b2f9d3-9962-4ebb-a9b7-be113fd3389a>)

---

### Microsoft Entra Connect — Sync Status Enabled
![Entra Connect Sync](<https://github.com/user-attachments/assets/f08b9aaf-2be1-4f3f-b3bb-6d0c803af176>)

---

### Azure Portal — DC01 VM Running
![DC01 VM](<https://github.com/user-attachments/assets/0226a21f-3b37-4297-9463-91534ef99b7a>)

---

## 🔑 Key Concepts Demonstrated

- **Hybrid Identity Architecture** — connecting on-prem AD to cloud Entra ID
- **Identity Provisioning** — creating and managing users and groups in AD
- **Group Policy Enforcement** — applying security policies across a domain
- **Password Policy Management** — enforcing complexity, age, and history rules
- **Account Lockout Policy** — protecting against brute force attacks
- **Directory Synchronization** — syncing identities using Password Hash Sync
- **Role-Based Access Control** — organizing users into security groups by department
- **Azure VM Management** — deploying and managing Windows Server in Azure

---

## 🔗 Related Projects

- [LogSentinel](https://github.com/ParmeetGill422/LogSentinel) — Python log analysis and incident report automation tool

---

## 👤 Author

**Parmeet Gill**
- LinkedIn: [linkedin.com/in/parmeet-gill-gill5757](https://linkedin.com/in/parmeet-gill-gill5757)
- GitHub: [github.com/ParmeetGill422](https://github.com/ParmeetGill422)
- Email: parmeetgill422@gmail.com

---

*Built as part of a cybersecurity portfolio targeting SOC Analyst and IAM Analyst roles.*

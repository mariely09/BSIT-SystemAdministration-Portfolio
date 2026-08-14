# 🏢 ABC Startup Solutions — Enterprise IT Infrastructure Plan

**Week 2 Portfolio Project: Enterprise Infrastructure Planning for a Startup Company**

> **Prepared by:** [Your Name] — Junior System Administrator  
> **Institution:** Laguna State Polytechnic University  
> **Location:** Province of Laguna, Philippines  
> **Date:** August 2026  

[![Status](https://img.shields.io/badge/Status-Complete-brightgreen)](#) [![Platform](https://img.shields.io/badge/Platform-Windows%2011%20Pro%20%7C%20Ubuntu%20Server-blue)](#) [![Diagram](https://img.shields.io/badge/Diagram-Draw.io-orange)](#)

---

## 📑 Table of Contents

- [Project Overview](#project-overview)
- [Learning Objectives](#learning-objectives)
- [Company Scenario](#company-scenario)
- [Hardware Inventory Summary](#hardware-inventory-summary)
- [Software Inventory Summary](#software-inventory-summary)
- [Network Diagram](#network-diagram)
- [Technologies Used](#technologies-used)
- [Challenges Encountered](#challenges-encountered)
- [Reflection](#reflection)
- [References](#references)

---

## 📋 Project Overview

This project documents the complete, from-scratch design of an enterprise IT infrastructure for **ABC Startup Solutions**, a newly established 20-employee software development company. The plan covers company profiling, enterprise hardware and software inventories, network topology design, system administration role research, and strategic infrastructure recommendations — including security, backup, and password policies aligned with industry standards such as **NIST SP 800-63B** and the **3-2-1 backup rule**.

---

## 🎯 Learning Objectives

| # | Objective |
|---|-----------|
| 1 | Design enterprise hardware and software inventories aligned with departmental business needs. |
| 2 | Create a logical, professional network topology using industry-standard diagramming tools. |
| 3 | Apply core networking concepts (VLANs, PoE, structured CAT6 cabling, firewall segmentation). |
| 4 | Research system administration roles, responsibilities, tools, and certifications. |
| 5 | Formulate security, backup, and password policies based on recognized industry frameworks. |
| 6 | Document infrastructure professionally using Markdown, tables, and GitHub conventions. |

---

## 🏢 Company Scenario

ABC Startup Solutions occupies a **single office floor** and currently has **no computers, no server, no network, no internet infrastructure, and no security policies**. The entire IT environment must be designed from zero (greenfield deployment).

| Department | Employees | Primary IT Needs |
|------------|----------:|------------------|
| Information Technology | 5 | Developer workstations, virtualization, server administration |
| Human Resources | 4 | Records management, payroll, document processing |
| Finance | 5 | Accounting, budgeting, secure financial reporting |
| Sales | 6 | Mobile laptops, presentations, CRM, client meetings |
| **TOTAL** | **20** | |

---

## 🖥️ Hardware Inventory Summary

| # | Hardware | Qty | Deployment / Purpose |
|---|----------|----:|----------------------|
| 1 | Standard Office Desktops (i5 / 16GB / 512GB SSD) | 9 | Finance & HR daily operations |
| 2 | Developer Workstations (i7 / 32GB / 1TB NVMe) | 5 | IT development, testing, virtualization |
| 3 | Business Laptops | 6 | Sales mobility and client visits |
| 4 | Loaner / Travel Laptop | 1 | Spare coverage for repairs and travel |
| 5 | Tower Server (Xeon / 64GB ECC / RAID) | 1 | Ubuntu Server: DNS, DHCP, file, backup, auth |
| 6 | Business Router | 1 | Edge routing, VPN, QoS |
| 7 | Next-Generation Firewall | 1 | UTM, IPS, web filtering |
| 8 | 48-Port PoE+ Managed Switch | 1 | Wired backbone and AP power delivery |
| 9 | Wi-Fi 6 Access Points | 2 | Wireless coverage, capacity, redundancy |
| 10 | Multifunction Network Printer | 1 | Shared print / scan / copy |
| 11 | UPS Units (1500VA / 1000VA) | 2 | Power protection for critical equipment |
| 12 | 4-Bay NAS (RAID) | 1 | Centralized storage and local backups |
| 13 | 8TB External Backup Drives | 2 | Offline rotation (3-2-1 strategy) |
| 14 | 24" Monitors | 40 | Dual-display productivity for all staff |

---

## 💿 Software Inventory Summary

| Software | Version | License | Primary Purpose |
|----------|---------|---------|-----------------|
| [Windows 11 Pro](https://www.microsoft.com/en-us/windows/business/windows-11-pro) | 25H2 | OEM / Device | Client OS, BitLocker, domain support |
| [Ubuntu Server](https://ubuntu.com/server/docs) | 24.04 LTS | Open Source | Server OS and core services |
| Microsoft Office (M365 Apps) | Current Channel | Subscription (20 users) | Productivity suite |
| [VS Code](https://code.visualstudio.com/docs) | Latest Stable | Free | Code editing and scripting |
| [Git](https://git-scm.com/doc) | Latest Stable | Open Source | Distributed version control |
| [GitHub Desktop](https://docs.github.com/en/desktop) | Latest Stable | Free | GUI Git client |
| [VirtualBox](https://www.virtualbox.org/manual/) | Latest Stable | Open Source (GPL) | Virtualization and lab testing |
| Google Chrome | Latest Stable | Free | Browsing and web app testing |
| [Microsoft Defender](https://learn.microsoft.com/en-us/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-antivirus) | Latest | Included with Win 11 Pro | Endpoint protection |
| [AnyDesk](https://anydesk.com/en/features/security) | Latest Stable | Commercial | Remote support |
| 7-Zip | Latest Stable | Open Source (LGPL) | Compression and archiving |

---

## 🌐 Network Diagram

<p align="center">
  <img src="./assets/network-diagram.png" alt="ABC Startup Solutions Enterprise Network Topology" width="850"/>
</p>
<p align="center"><em>Figure 1: Enterprise Network Topology (Draw.io export — <a href="./assets/network-diagram.pdf">PDF version</a>)</em></p>

<details>
<summary>📐 View text-based topology (Mermaid)</summary>

```mermaid
flowchart TD
    Internet(((INTERNET)) --> Modem[ISP Modem / ONT]
    Modem --> Router[Edge Router]
    Router --> Firewall[Hardware Firewall]
    Firewall --> Switch{48-Port Core Switch}

    Switch --> Server[Ubuntu Server & NAS]
    Switch --> Printer[Network Printer]
    Switch --> WAP[Wireless Access Points]
    Switch --> IT[IT Dept - 5 Desktops]
    Switch --> HR[HR Dept - 4 Desktops]
    Switch --> Finance[Finance Dept - 5 Desktops]
    WAP --> Sales[Sales Dept - 6 Laptops]
```

</details>

---

## 🛠️ Technologies Used

| Category | Technology | Role in Project |
|----------|------------|-----------------|
| Operating Systems | Windows 11 Pro, Ubuntu Server 24.04 LTS | Client and server platforms |
| Networking | [FortiGate NGFW](https://www.fortinet.com/products/next-generation-firewall), [Ubiquiti UniFi](https://ui.com/networking), [Cisco Switches](https://www.cisco.com/c/en/us/products/switches/index.html) | Edge security, switching, wireless |
| Servers & Storage | [Dell PowerEdge](https://www.dell.com/en-us/shop/servers), Synology NAS, APC UPS | Compute, centralized storage, power protection |
| Development | VS Code, Git, GitHub Desktop, VirtualBox | Software development and testing workflow |
| Security & Policy | Microsoft Defender, [NIST SP 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html) | Endpoint protection and password policy |
| Backup | [Veeam 3-2-1 Guidance](https://www.veeam.com/blog/321-backup-rule.html) | Backup and disaster recovery strategy |
| Documentation | [Draw.io](https://app.diagrams.net/), Markdown | Network diagramming and project documentation |

---

## ⚠️ Challenges Encountered

- **Balancing budget vs. enterprise standards** — Selecting hardware that meets professional requirements without overspending for a 20-person startup required careful justification of every line item.
- **Designing VLAN segmentation** — Deciding how to isolate IT, HR/Finance, Sales, and Guest traffic while keeping shared resources (server, printer) accessible demanded critical thinking about both connectivity and security.
- **Translating theory into a visual topology** — Building the Draw.io diagram required converting abstract networking concepts (PoE, trunks, WAN/LAN flow) into a clean, logical, and labeled schematic.
- **Sizing cabling and PoE budgets** — Estimating CAT6 cable runs, patch panel ports, and PoE power budgets for current use plus future expansion was difficult but essential.
- **License and version compliance** — Ensuring every software item had a legitimate license model and up-to-date stable version required cross-checking multiple vendor documentations.

---

## 💭 Reflection

Designing a complete IT infrastructure from scratch for ABC Startup Solutions has been one of the most eye-opening experiences in my journey toward becoming a System Administrator. Through this project, I learned that enterprise IT is not merely about purchasing computers and connecting them to the internet; it is about strategically aligning technology with the specific operational needs of every department. I gained practical knowledge in selecting enterprise hardware, managing software licensing, structuring VLANs, and establishing robust security and backup policies. Most importantly, I learned how each individual component—from the ISP modem to the end-user's dual monitors—must work together seamlessly to create a secure, scalable, and efficient working environment.

The most challenging task for me was designing the Enterprise Network Diagram and formulating the Infrastructure Recommendations. Translating theoretical networking concepts into a logical, visual topology required careful consideration of traffic flow, security boundaries, and physical cabling limits. Deciding how to segment the IT, HR, Finance, and Sales departments into different VLANs while ensuring they could still securely access the central server forced me to think critically about both connectivity and data isolation. Additionally, justifying the hardware specifications and backup strategies required me to balance ideal enterprise standards with the realistic financial constraints and growth projections of a 20-person startup.

This project deeply reinforced the fact that planning is absolutely critical before deployment. In a real-world scenario, deploying hardware without a comprehensive blueprint often leads to costly rework, network bottlenecks, and severe security vulnerabilities. By planning ahead, we can accurately forecast budgets, ensure IP address scalability, and establish disaster recovery protocols before a crisis actually occurs. A well-documented plan acts as a roadmap that minimizes downtime during installation and provides a reliable baseline for future troubleshooting. I realized that a reactive approach to IT is exhausting and expensive, whereas a proactive, planned approach builds organizational trust and operational stability.

Ultimately, this project will help me become a significantly better System Administrator by shifting my mindset from that of a reactive troubleshooter to a strategic infrastructure architect. I now understand that technical skills alone are not enough; a great administrator must also understand business workflows, risk management, and user experience. The ability to document, justify, and design systems from the ground up will allow me to approach future enterprise projects with confidence, ensuring that the technology I manage not only keeps the company running today but is fully prepared to support its long-term growth tomorrow.

---

## 📚 References

**Certifications and Roles Research**
- CompTIA A+ — https://www.comptia.org/certifications/a
- CompTIA Network+ — https://www.comptia.org/certifications/network
- Cisco CCNA — https://www.cisco.com/site/us/en/learn/training-certifications/certifications/enterprise/ccna/index.html
- Red Hat RHCSA — https://www.redhat.com/en/services/training/rhcsa-red-hat-certified-system-administrator
- AWS SysOps Administrator — https://aws.amazon.com/certification/certified-sysops-admin-associate/
- Microsoft Azure Administrator — https://learn.microsoft.com/en-us/credentials/certifications/azure-administrator/
- LPIC-1 — https://www.lpi.org/our-certifications/lpic-1-overview/

**Security and Software**
- Microsoft Defender Antivirus — https://learn.microsoft.com/en-us/windows/security/operating-system-security/virus-and-threat-protection/microsoft-defender-antivirus
- Ubuntu Server Documentation — https://ubuntu.com/server/docs
- Git Documentation — https://git-scm.com/doc
- NIST SP 800-63B (Password Guidelines) — https://pages.nist.gov/800-63-3/sp800-63b.html
- Veeam 3-2-1 Backup Rule — https://www.veeam.com/blog/321-backup-rule.html

**Hardware and Networking**
- FortiGate 40F Datasheet — https://www.fortinet.com/products/next-generation-firewall
- Ubiquiti UniFi Dream Machine Pro — https://ui.com/cloud-gateways
- Dell PowerEdge Servers — https://www.dell.com/en-us/shop/servers
- Draw.io / Diagrams.net — https://app.diagrams.net/

---

<p align="center"><em>© 2026 ABC Startup Solutions IT Infrastructure Plan • Prepared for academic portfolio purposes</em></p>

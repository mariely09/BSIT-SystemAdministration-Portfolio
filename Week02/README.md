# Week 2 Portfolio Project: Enterprise Infrastructure Planning for a Startup Company

> **Prepared by:** Mariely Ann Tolentino  
> **Course & Section:** BSIT-4D WAMD
> 
> **Instructor:** John Randolf M. Penaredondo, MIT  

---

## Project Overview

This project documents the complete, from-scratch design of an enterprise IT infrastructure for **ABC Startup Solutions**, a newly established 20-employee software development company. The plan covers company profiling, enterprise hardware and software inventories, network topology design, system administration role research, and strategic infrastructure recommendations including security, backup, and password policies aligned with industry standards such as **NIST SP 800-63B** and the **3-2-1 backup rule**.

---

## Learning Objectives

| # | Objective |
|---|-----------|
| 1 | Design enterprise hardware and software inventories aligned with departmental business needs. |
| 2 | Create a logical, professional network topology using industry-standard diagramming tools. |
| 3 | Apply core networking concepts (VLANs, PoE, structured CAT6 cabling, firewall segmentation). |
| 4 | Research system administration roles, responsibilities, tools, and certifications. |
| 5 | Formulate security, backup, and password policies based on recognized industry frameworks. |
| 6 | Document infrastructure professionally using Markdown, tables, and GitHub conventions. |

---

## Company Scenario

ABC Startup Solutions occupies a **single office floor** and currently has **no computers, no server, no network, no internet infrastructure, and no security policies**. The entire IT environment must be designed from zero (greenfield deployment).

| Department | Employees |
|------------|----------:|
| Information Technology | 5 |
| Human Resources | 4 | 
| Finance | 5 | 
| Sales | 6 
| **TOTAL** | **20** |

---

## Hardware Inventory Summary

| ASSET ID | HARDWARE | QUANTITY | DEPARTMENT | PURPOSE |
|:---------|:---------|:--------:|:-----------|:--------|
| HW-001 | Desktop Computers | 14 | Finance, HR, and IT | Used for daily office tasks such as document processing, spreadsheets, payroll, accounting, email, and internal file access. |
| HW-002 | Laptops | 7 | Sales and IT | Used by sales employees for client meetings, presentations, proposals, customer follow-ups, remote work, and cloud-based applications. |
| HW-003 | Server | 1 | IT | Hosts company server services such as file storage support, backups, DNS, DHCP, authentication, monitoring, and internal tools. |
| HW-004 | Router | 1 | IT | Provides internet connection, firewall protection, VPN support, network routing, and basic network security. |
| HW-005 | Switch | 1 | IT | Connects all wired devices and provides Power over Ethernet for wireless access points and future network devices. |
| HW-006 | Printer | 1 | All Departments | Provides printing, scanning, and copying services for all employees in the office. |
| HW-007 | UPS | 2 | IT and Finance | Provides backup power for the server, router, switch, and NAS during power interruptions. |
| HW-008 | Wireless Access Point | 2 | IT | Provides reliable Wi-Fi coverage for laptops, mobile devices, and guest users across the office floor. |
| HW-009 | NAS Storage | 1 | IT | Provides centralized file storage, departmental shared folders, backup storage, and file recovery support. |
| HW-010 | External Backup Drive | 2 | IT | Used for offline backup rotation and disaster recovery protection. |
| HW-011 | Monitors | 40 | All departments | Provides dual-monitor setup for each employee to improve productivity and multitasking. |

---

## Software Inventory Summary

| SOFTWARE | VERSION | LICENSE | PURPOSE |
|:---------|:--------|:--------|:--------|
| Windows 11 Pro | 25H2 or latest stable build | OEM / Device license for company desktops and laptops | Primary operating system for employee computers; provides domain support, BitLocker encryption, security features, and compatibility with business software |
| Ubuntu Server | 24.04 LTS | Open-source / Free | Server operating system for file services, backups, DNS, DHCP, authentication support, monitoring, and internal tools |
| Microsoft Office | Microsoft 365 Apps for Business, Current Channel | Subscription, per user | Productivity suite for documents, spreadsheets, presentations, email, and cloud collaboration |
| VS Code | Latest stable version | Free / Microsoft license | Code editor for software development, scripting, configuration files, and documentation |
| Git | Latest stable version | Open-source | Distributed version control system for tracking code changes and supporting collaborative development |
| GitHub Desktop | Latest stable version | Free | Graphical Git client for easier repository management and simplified version control tasks |
| VirtualBox | Latest stable version | Open-source / GPL | Virtualization software for testing operating systems, applications, and network configurations in a safe environment |
| Google Chrome | Latest stable version | Free / Chrome Enterprise | Web browser for cloud applications, online tools, research, and web application testing |
| Microsoft Defender | Latest platform and signature updates | Included with Windows 11 Pro | Endpoint protection against viruses, malware, ransomware, and other security threats |
| AnyDesk | Latest stable version | Commercial remote-support license | Secure remote access and technical support tool for troubleshooting user computers |
| 7-Zip | Latest stable version | Open-source / LGPL | File compression and extraction tool for archives, installers, logs, and backup files |

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

## Technologies Used

- Markdown and GitHub for documentation
- Draw.io for network diagramming
- Microsoft Word for the portfolio report
- Concepts: TCP/IP, VLANs, DHCP, RAID, 3-2-1 backup strategy

---

## Challenges Encountered

- **Balancing budget vs. enterprise standards** — Selecting hardware that meets professional requirements without overspending for a 20-person startup required careful justification of every line item.
- **Designing VLAN segmentation** — Deciding how to isolate IT, HR/Finance, Sales, and Guest traffic while keeping shared resources (server, printer) accessible demanded critical thinking about both connectivity and security.
- **Translating theory into a visual topology** — Building the Draw.io diagram required converting abstract networking concepts (PoE, trunks, WAN/LAN flow) into a clean, logical, and labeled schematic.
- **Sizing cabling and PoE budgets** — Estimating CAT6 cable runs, patch panel ports, and PoE power budgets for current use plus future expansion was difficult but essential.
- **License and version compliance** — Ensuring every software item had a legitimate license model and up-to-date stable version required cross-checking multiple vendor documentations.

---

## Reflection

Designing a complete IT infrastructure from scratch for ABC Startup Solutions has been one of the most eye-opening experiences in my journey toward becoming a System Administrator. Through this project, I learned that enterprise IT is not merely about purchasing computers and connecting them to the internet; it is about strategically aligning technology with the specific operational needs of every department. I gained practical knowledge in selecting enterprise hardware, managing software licensing, structuring VLANs, and establishing robust security and backup policies. Most importantly, I learned how each individual component—from the ISP modem to the end-user's dual monitors—must work together seamlessly to create a secure, scalable, and efficient working environment.

The most challenging task for me was designing the Enterprise Network Diagram and formulating the Infrastructure Recommendations. Translating theoretical networking concepts into a logical, visual topology required careful consideration of traffic flow, security boundaries, and physical cabling limits. Deciding how to segment the IT, HR, Finance, and Sales departments into different VLANs while ensuring they could still securely access the central server forced me to think critically about both connectivity and data isolation. Additionally, justifying the hardware specifications and backup strategies required me to balance ideal enterprise standards with the realistic financial constraints and growth projections of a 20-person startup.

This project deeply reinforced the fact that planning is absolutely critical before deployment. In a real-world scenario, deploying hardware without a comprehensive blueprint often leads to costly rework, network bottlenecks, and severe security vulnerabilities. By planning ahead, we can accurately forecast budgets, ensure IP address scalability, and establish disaster recovery protocols before a crisis actually occurs. A well-documented plan acts as a roadmap that minimizes downtime during installation and provides a reliable baseline for future troubleshooting. I realized that a reactive approach to IT is exhausting and expensive, whereas a proactive, planned approach builds organizational trust and operational stability.

Ultimately, this project will help me become a significantly better System Administrator by shifting my mindset from that of a reactive troubleshooter to a strategic infrastructure architect. I now understand that technical skills alone are not enough; a great administrator must also understand business workflows, risk management, and user experience. The ability to document, justify, and design systems from the ground up will allow me to approach future enterprise projects with confidence, ensuring that the technology I manage not only keeps the company running today but is fully prepared to support its long-term growth tomorrow.

---

## References

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

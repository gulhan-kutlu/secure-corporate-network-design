# secure-corporate-network-design

###  Secure Corporate Network Architecture Design
This repository presents a **security-focused enterprise network architecture**
designed for a mid-size corporate environment.

> The project demonstrates a **defense-in-depth approach**, incorporating perimeter
security, DMZ segmentation, internal VLAN isolation, identity-based access control,
intrusion detection, and continuous vulnerability scanning.


> This is a **network security architecture case study**, not a software development project.


### Design Frameworks & References
> The architecture aligns with industry best practices and established frameworks:

- NIST SP 800-41 – Firewalls and Firewall Policy
- NIST SP 800-94 – Intrusion Detection and Prevention Systems
- NIST SP 800-115 – Security Testing and Assessment
- Cisco SAFE Secure Edge & DMZ Design
- Microsoft Defender for Endpoint Architecture Guidance



### Architecture Overview
> The design evolves from a high-level logical topology into a **policy-driven,
enterprise-grade architecture** defining:

- Device roles and placement
- Network segmentation and IP ranges
- Security boundaries and traffic flows
- Monitoring and vulnerability management


### Network Flow Overview
Inbound traffic follows a controlled inspection path:

Internet → Edge Router → NGFW → DMZ / Internal Network


### Figure 1. Initial Network Diagram
<img width="329" height="232" alt="image" src="https://github.com/user-attachments/assets/461e97ee-6909-4521-9d54-12a7c722e444" />


> Security controls are enforced at each layer to minimize attack surface and lateral movement.


### DMZ Architecture
The DMZ hosts all public-facing services:

- Remote Access VPN Gateway
- Web Server (Nginx)
- Secure FTP / SFTP Service
- IDS Sensor

Key design principles:
- No direct access from VPN to internal VLANs
- North–south traffic monitored via IDS
- Strict port exposure and NAT controls



### Figure 2. Final Network Diagram
<img width="468" height="124" alt="image" src="https://github.com/user-attachments/assets/1519f5f0-a6a1-4faf-9553-b505952a2a16" />





## Internal Network Segmentation
Internal routing and switching provide Layer-3 connectivity to departmental VLANs:

- Engineering: `10.0.10.0/24`
- Finance: `10.0.20.0/24`
- IT: `10.0.100.0/24`

Security controls include:
- Inter-VLAN ACLs blocking Engineering ↔ Finance traffic
- Segmentation firewall enforcing east–west traffic policies
- Least-privilege access enforcement



### Management, Monitoring & Security
A dedicated management and security subnet hosts:

- Active Directory (LDAPS)
- Microsoft Defender for Endpoint
- Proxy Services
- Nessus / OpenVAS Vulnerability Scanner

Credentialed vulnerability scans run daily, collecting telemetry from:
- Endpoints
- IDS sensors
- Network devices



### Key Security Objectives Achieved
- DMZ and internal network separation
- Restricted VPN access boundaries
- Departmental isolation
- Continuous vulnerability scanning
- Centralized monitoring and visibility


### Notes
- This project was developed in an academic environment and is presented as a
  **professional enterprise network security design case study**
- No proprietary configurations, credentials, or production systems are included
- The focus is on **architecture, security design, and system reasoning**, not implementation scripts


### Disclaimer
> This repository is shared for **educational and portfolio purposes only** and does
> not expose confidential or operational enterprise infrastructure.




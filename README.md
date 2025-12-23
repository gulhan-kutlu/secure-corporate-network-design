# secure-corporate-network-design

# Secure Corporate Network Architecture Design

This repository presents a **security-focused network architecture design** for a mid-size corporate environment.

The design demonstrates a **defense-in-depth approach**, incorporating perimeter security, DMZ segmentation, internal VLAN isolation, identity-based access control, endpoint protection, intrusion detection, and continuous vulnerability scanning.

###  Overview

The architecture is structured around industry best practices and widely accepted security frameworks, including:
- NIST SP 800-41 (Firewalls and Firewall Policy)
- NIST SP 800-94 (Intrusion Detection and Prevention Systems)
- NIST SP 800-115 (Security Testing and Assessment)
- Cisco SAFE Secure Edge and DMZ design principles
- Microsoft Defender for Endpoint architecture guidance

The solution balances **security, usability, and operational practicality**, reflecting real-world enterprise constraints.

###  Key Design Elements

- Edge router and next-generation firewall (NGFW)
- DMZ with public-facing services (VPN, Web, SFTP)
- Internal segmentation with departmental VLANs
- Identity and authentication using Active Directory
- Endpoint protection and EDR
- IDS sensors in both DMZ and internal network
- Daily authenticated vulnerability scanning
- Strict VPN and inter-VLAN access controls

###  Network Diagrams

- Initial high-level topology
- Final policy-driven architecture with device placement and IP segmentation


###  Notes

This project was developed in an academic context but is presented here as a **professional network security design case study** aligned with enterprise best practices.







### Initial Network Architecture (High-Level Design)

### Figure 1 presents the initial high-level network architecture for a secure mid-size corporate environment.

### This diagram focuses on the core structural components required for a secure enterprise network, including:

Edge router and perimeter firewall

Demilitarized Zone (DMZ)

Internal routing and switching

Authentication and identity services

Endpoint protection and vulnerability scanning

Segmented user VLANs

The design intentionally avoids low-level configuration details and instead emphasizes logical segmentation and traffic flow, following common best practices outlined in NIST SP 800-41 and NIST SP 800-94, as well as Cisco SAFE secure edge and DMZ patterns.




### Traffic Flow Overview

### Inbound traffic follows a controlled inspection path:

Internet → Edge Router → Edge Firewall → DMZ / Internal Network

### DMZ Design Rationale

The DMZ hosts services that must be reachable from external networks, including:

VPN gateway

Web server

FTP/SFTP service

Web proxy

An IDS sensor monitors north–south traffic entering and leaving the DMZ, providing early detection of malicious activity before traffic reaches internal segments.


Internal Network Segmentation

Behind the perimeter, internal routing and switching provide Layer-3 connectivity to multiple departmental VLANs, including:

Engineering (10.0.10.0/24)

Finance (10.0.20.0/24)

IT (10.0.100.0/24)

Separating departments into distinct subnets establishes the foundation for:

Fine-grained access control

Reduced lateral movement

Clear enforcement of least-privilege principles

A dedicated management and security subnet hosts identity services, endpoint protection management, and vulnerability scanning tools. This subnet can securely reach all VLANs for monitoring and authentication without being exposed to standard user traffic.


Design Intent

The purpose of this initial architecture is not to define every access control list or firewall rule, but to present a clean, logically segmented topology that satisfies core security requirements and aligns with accepted enterprise design standards.

This structure serves as the baseline for more detailed, policy-driven controls implemented in the final architecture, including VPN restrictions, departmental isolation, and continuous vulnerability scanning.

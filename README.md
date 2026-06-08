# School Network Infrastructure Design and Security Implementation

## Overview

This project demonstrates the design, implementation, and security hardening of a scalable school network using Cisco Packet Tracer. The network was built using a three-tier architecture and incorporates enterprise networking concepts including VLAN segmentation, DHCP, DNS, wireless networking, firewall deployment, HSRP redundancy, SSH management, ACLs, and port security.

The design supports a school environment with over 300 students and 21 faculty/staff members while maintaining network performance, availability, and security.

---

## Network Architecture

### Three-Tier Architecture

The network follows a hierarchical design consisting of:

- Core Layer
- Distribution Layer
- Access Layer

### Core Layer

- CORE-SW1 (Primary Core)
- CORE-SW2 (Secondary Core)

Features:
- Inter-VLAN Routing
- HSRP Gateway Redundancy
- Spanning Tree Root Configuration
- Connection to Firewall

### Distribution Layer

- DSW-1
- DSW-2

Responsibilities:
- VLAN Aggregation
- Trunking
- Redundant Connectivity to Core

### Access Layer

- ASW-1 (Admin Office)
- ASW-2 (Leadership Offices)
- ASW-3 (Teachers/Staff)
- ASW-4 (Student Computer Lab)

Responsibilities:
- End Device Connectivity
- Port Security
- VLAN Assignment

---

## Network Segments

| VLAN | Department | Subnet |
|--------|-----------|-----------|
| 10 | Admin Office | 192.168.10.0/27 |
| 20 | Leadership | 192.168.20.0/28 |
| 30 | Staff WiFi | 192.168.30.0/26 |
| 40 | Student Lab & Student WiFi | 192.168.40.0/26 |
| 50 | Servers | 192.168.50.0/27 |
| 99 | Management | 192.168.99.0/27 |

---

## Departments Supported

### Administration

- Clerk
- Bursar

### Leadership

- Headmaster
- Deputy Headmaster

### Teachers

- Wireless Connectivity
- Personal Devices

### Students

- Computer Lab
- Wireless Connectivity

---

## Services Implemented

### DHCP

A centralized DHCP server provides dynamic IP address allocation for all VLANs.

Features:
- Multiple DHCP Scopes
- Automatic Gateway Assignment
- Automatic DNS Assignment

### DNS

A centralized DNS server provides hostname resolution.

Example records:

- school.local
- fileserver.school.local
- admin.school.local

### Wireless Networking

Two wireless networks were deployed:

#### STAFF-WIFI

- VLAN 30
- WPA2 Security

#### STUDENT-WIFI

- VLAN 40
- WPA2 Security

---

## Security Controls

### Access Control Lists (ACLs)

Security policies were implemented to control inter-VLAN communication.

Examples:

- Students cannot access:
  - Admin VLAN
  - Leadership VLAN
  - Management VLAN

- Staff cannot access:
  - Management VLAN

### SSH Remote Administration

Secure management access is enabled on all switches.

Features:

- SSH Version 2
- Local User Authentication
- Management VLAN

### Port Security

Port Security was implemented on access ports.

Features:

- Sticky MAC Address Learning
- Maximum MAC Enforcement
- Restrict Mode Violations

### Firewall

An edge firewall/router was deployed between the internal network and the simulated internet.

Features:

- NAT/PAT
- Traffic Filtering
- Perimeter Security

---

## High Availability

### Redundant Core

A second core switch was introduced to eliminate single points of failure.

### HSRP

Hot Standby Router Protocol was configured to provide gateway redundancy.

Benefits:

- Automatic Failover
- Increased Availability
- Minimal Network Downtime

### Spanning Tree

Configured to prevent Layer 2 loops and support redundant links.

---

## Technologies Used

- Cisco Packet Tracer
- VLANs
- Inter-VLAN Routing
- DHCP
- DNS
- ACLs
- HSRP
- SSH
- Port Security
- NAT/PAT
- Wireless Access Points
- Spanning Tree Protocol

---

## Project Objectives

The project demonstrates:

- Enterprise Network Design
- Campus Network Architecture
- Network Segmentation
- Security Hardening
- High Availability
- Infrastructure Redundancy
- Network Management Best Practices

---

## Skills Demonstrated

### Networking

- VLAN Design
- Routing and Switching
- Trunk Configuration
- Redundancy Design

### Cybersecurity

- Network Segmentation
- Access Control Lists
- Firewall Configuration
- Port Security
- Secure Remote Administration

### Infrastructure

- DHCP Deployment
- DNS Deployment
- Wireless Network Design
- High Availability Configuration

---

## Future Improvements

Potential enhancements include:

- Syslog Server
- SNMP Monitoring
- NTP Server
- VPN Access
- Intrusion Detection System (IDS)
- Intrusion Prevention System (IPS)
- Network Monitoring Dashboard
- Splunk Integration
- Cisco ASA Firewall
- EtherChannel Implementation

---

## Author

Solomon Runzonza

MS Cybersecurity – Quinnipiac University

Certifications:
- AWS Certified Solutions Architect – Associate
- CompTIA Security+
- Cisco CCNA

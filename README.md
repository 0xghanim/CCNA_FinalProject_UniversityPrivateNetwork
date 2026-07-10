````markdown
# 🎓 University Private Network Infrastructure - Cisco Packet Tracer

A complete Cisco Packet Tracer project simulating a university network infrastructure based on CCNA networking concepts. The project demonstrates network segmentation, redundancy, security, and centralized network services.

---

## 📌 Project Overview

This project simulates a university campus network consisting of multiple faculty buildings connected through a redundant distribution layer. The design focuses on scalability, availability, and security using Cisco networking technologies.

---

## 🏛️ Network Topology

The network consists of:

- 2 Cisco 2911 Routers
- 2 Distribution Switches
- 4 Faculty Access Switches
- Data Center Switch
- Multiple PCs
- Printer
- DHCP Server
- DNS Server
- Web Server
- NTP Server

### Faculty Buildings

- Computer Science
- Engineering
- Business
- Data Center

Each faculty contains:

- 2 Staff PCs
- 2 Student PCs
- 1 Admin PC
- 1 Network Printer

---

# 🖥️ Network Architecture

```
                 R1 (Active)
                    |
                 Router-on-a-Stick
                    |
                 +--------+
                 | SW1    |
                 +--------+
                 ||      ||
          EtherChannel (LACP)
                 ||      ||
                 +--------+
                 | SW2    |
                 +--------+
            /   /   |   \    \
         CS   ENG  BUS  DC
```

R2 acts as the Standby Router using HSRP.

---

# 🌐 VLAN Design

| VLAN | Name | Network |
|------|------|----------------|
| 10 | STAFF | 192.168.10.0/24 |
| 20 | STUDENTS | 192.168.20.0/24 |
| 30 | ADMIN | 192.168.30.0/24 |
| 40 | SERVERS | 192.168.40.0/24 |

### VLAN Verification

![VLANs](Screenshots/VLAN.jpg)

---

# 🚀 Features

## Layer 2

- VLAN Segmentation
- Access Ports
- 802.1Q Trunking
- EtherChannel (LACP)
- Rapid Spanning Tree Protocol (RSTP)

---

## Layer 3

- Router-on-a-Stick
- Inter-VLAN Routing
- HSRP (First Hop Redundancy)

---

## Network Services

- DHCP Server
- DNS Server
- Web Server
- NTP Server

---

## Security

- ACL Firewall
- Port Security
- Sticky MAC Addresses
- DHCP Relay (ip helper-address)

---

# 🔄 High Availability

The project implements:

- HSRP
- Active Router (R1)
- Standby Router (R2)
- Automatic Failover
- EtherChannel Redundancy
- STP Loop Prevention

---

# 🔐 Security Policy

### Students

✅ Access Staff

✅ Access Students

❌ Cannot access Admin Network

❌ Cannot access Servers

---

### Staff

✅ Access Staff

✅ Access Students

✅ Access Admin

❌ Cannot access Servers

---

### Admin

✅ Full Network Access

---

# 📡 Network Services

## DHCP

Dynamic IP assignment for:

- Staff
- Students
- Admin

---

## DNS

Hostname Resolution

Example:

```
www.university.local
```

---

## Web Server

Hosts the university homepage.

---

## NTP

Provides synchronized time across routers and switches.

---

## Syslog

Collects logs from:

- Routers
- Switches

Examples:

- Interface Up/Down
- Configuration Changes
- HSRP Events
- Port Security Violations

---

# 🛡️ Port Security

Configured on all access ports.

- Maximum 1 MAC Address
- Sticky MAC Learning
- Shutdown on Violation

---

# ⚙️ Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- VLAN
- Trunking
- EtherChannel
- STP
- Router-on-a-Stick
- HSRP
- DHCP
- DNS
- HTTP
- ACL
- NTP
- Port Security

---

# 🧪 Verification Commands

## VLAN

```bash
show vlan brief
```

## Trunk

```bash
show interfaces trunk
```

## EtherChannel

```bash
show etherchannel summary
```

## STP

```bash
show spanning-tree
```

## Router Interfaces

```bash
show ip interface brief
```

## HSRP

```bash
show standby brief
```

## ACL

```bash
show access-lists
```

## Port Security

```bash
show port-security
```

---

# 📂 Project Objectives

- Design a scalable university network.
- Implement network segmentation using VLANs.
- Configure Inter-VLAN routing.
- Provide gateway redundancy using HSRP.
- Implement secure access using ACLs.
- Protect access ports using Port Security.
- Deploy centralized network services.
- Ensure high availability and redundancy.

---

# 📸 Screenshots

Add screenshots of:

- Network Topology
- VLAN Configuration
- HSRP Verification
- DHCP Configuration
- Web Server
- Syslog Logs
- Successful Ping Tests

---

# 📖 Skills Demonstrated

- Cisco Switching
- Cisco Routing
- Network Segmentation
- High Availability
- Network Security
- DHCP Relay
- ACL Configuration
- EtherChannel
- Spanning Tree
- Cisco IOS Administration
- Enterprise Network Design

---

# 👨‍💻 Author

**Abdallah Ghanim**

Cybersecurity Student | Network & Web Penetration Testing Enthusiast

- GitHub: https://github.com/0xghanim
- LinkedIn: https://www.linkedin.com/in/abdallah-ghanim-527326393/
- Portofolio: https://0xghanim.github.io/portfolio/

---

## ⭐ If you found this project useful, consider giving it a star!
````

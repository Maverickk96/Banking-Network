# 🏦 Bank Network Security Architecture

A secure, scalable, and resilient banking network architecture designed and simulated using **Cisco Packet Tracer**. The project focuses on protecting banking infrastructure through network segmentation, access control, secure inter-branch communication, redundancy, and DMZ isolation.

## 📌 Project Overview

Banks handle highly sensitive financial and customer information, making their networks a high-value target for cyberattacks. This project presents a practical banking network architecture covering a **central server site, main branch, three sub-branches, and ISP connectivity**.

The architecture combines:

* VLAN-based departmental segmentation
* Inter-VLAN routing
* Access Control Lists (ACLs)
* Firewall and DMZ security
* NAT
* OSPF dynamic routing
* HSRP-based redundancy
* Site-to-site VPN simulation
* Dual-ISP / SD-WAN integration
* Network monitoring and logging

The complete architecture was designed and validated in **Cisco Packet Tracer**.

## 🎯 Objectives

* Ensure high availability through redundancy and failover.
* Provide secure and reliable communication between branches.
* Segment departmental traffic using VLANs.
* Protect public-facing services using a DMZ.
* Restrict unauthorized communication using ACLs.
* Provide encrypted communication through VPN simulation.
* Maintain private internal addressing using NAT.
* Enable efficient routing using OSPF.
* Provide a scalable architecture for future expansion.

## 🏗️ Network Scope

The simulated infrastructure consists of:

```text
                    ┌─────────────────┐
                    │      Internet   │
                    │      / ISP      │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │   Server Site   │
                    │ Firewall / DMZ  │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │   Main Branch   │
                    │ Core Network    │
                    └─────┬────┬──────┘
                          │    │
              ┌───────────┘    └───────────┐
              ▼                            ▼
      ┌──────────────┐              ┌──────────────┐
      │ Sub Branch 1 │              │ Sub Branch 2 │
      └──────────────┘              └──────────────┘
                                           │
                                    ┌──────▼───────┐
                                    │ Sub Branch 3 │
                                    └──────────────┘
```

The project covers a main branch, three sub-branches, a central server site, and ISP integration.

## 🔐 Security Architecture

### VLAN Segmentation

Departmental traffic is separated using VLANs to isolate sensitive resources and reduce unnecessary broadcast traffic.

Example departments include:

* HR
* Finance
* IT
* Customer Service
* Loans / Operations

IEEE 802.1Q trunking is used to carry multiple VLANs between network devices.

### Access Control Lists

ACLs are applied at VLAN gateways and firewall interfaces to control traffic between departments.

For example:

```text
HR VLAN ──X──> Restricted IT Resources
HR VLAN ─────> Required Business Services
Finance ─────> Authorized Banking Services
```

### DMZ

Public-facing services are isolated inside a DMZ.

The documented DMZ includes services such as:

* Online banking portal
* Public email
* Customer support interface

Firewall policies prevent direct access from public-facing services into protected internal VLANs.

### VPN

Site-to-site VPN tunnels provide encrypted communication between branches and the central server site.

### NAT

NAT allows private internal addresses to access external networks while keeping internal addressing private.

### HSRP

HSRP provides router redundancy. If the active router fails, the standby router takes over to maintain connectivity.

### OSPF

OSPF is used as the dynamic routing protocol between branches for efficient route selection and faster convergence.

## 🌐 IP Addressing

| Location     | Network           |   Devices |
| ------------ | ----------------- | --------: |
| Main Branch  | `192.168.20.0/24` |   9 + ATM |
| Sub Branch 1 | `192.168.10.0/24` |   6 + ATM |
| Sub Branch 2 | `192.168.11.0/24` |   6 + ATM |
| Sub Branch 3 | `192.168.12.0/24` |   7 + ATM |
| Server Site  | `192.168.30.0/24` | 4 servers |

The project uses six VLANs for network segmentation.

## 🧰 Technologies & Components

### Hardware / Network Components

* Cisco Layer 3 Switches
* Layer 2 Switches
* Routers
* Firewalls
* Servers
* PCs
* Printers
* Wireless Access Points
* Laptops
* Smartphones / Tablets
* ATM devices

### Networking Technologies

* Cisco Packet Tracer
* VLAN
* IEEE 802.1Q Trunking
* Inter-VLAN Routing
* ACL
* NAT
* HSRP
* OSPF
* VPN
* DHCP
* SD-WAN
* DMZ
* Firewall

The documented design specifically uses Layer 3 switching, firewalls, routers, VLANs, ACLs, NAT, HSRP, OSPF, and secure wireless access.

## 🧪 Testing & Results

The complete network was tested in Cisco Packet Tracer.

### Tests Performed

| Test                    | Result       |
| ----------------------- | ------------ |
| Same-VLAN communication | ✅ Successful |
| Inter-VLAN routing      | ✅ Successful |
| ACL enforcement         | ✅ Successful |
| DMZ isolation           | ✅ Successful |
| Public DMZ services     | ✅ Successful |
| Site-to-site VPN        | ✅ Successful |
| HSRP failover           | ✅ Successful |
| NAT                     | ✅ Successful |
| Branch connectivity     | ✅ Successful |

Testing confirmed VLAN communication, ACL restrictions, DMZ isolation, VPN tunnels, HSRP failover, and NAT functionality.

## 📂 Suggested Repository Structure

```text
Bank-Network/
│
├── README.md
├── Cisco-Packet-Tracer/
│   └── bank-network.pkt
│
├── Documentation/
│   ├── Network-Architecture.png
│   ├── IP-Addressing.md
│   └── Network-Design.pdf
│
├── Configurations/
│   ├── Routers/
│   ├── Switches/
│   └── Firewalls/
│
└── Screenshots/
    ├── VLAN.png
    ├── DMZ.png
    ├── VPN.png
    └── HSRP-Failover.png
```

## 🚀 How to Use

1. Install **Cisco Packet Tracer**.
2. Clone or download this repository.
3. Open the `.pkt` project file.
4. Inspect the network topology.
5. Review VLAN, routing, ACL, NAT, VPN, and redundancy configurations.
6. Run connectivity tests using Packet Tracer's simulation or command-line tools.
7. Test failure scenarios such as router failure to verify HSRP behavior.

## 📈 Future Enhancements

Potential future improvements include:

* SD-WAN expansion
* 5G integration
* Advanced network monitoring
* Automated threat detection
* SIEM integration
* Enhanced intrusion prevention
* Cloud-based banking infrastructure
* Expansion to additional branches

## 🎓 Academic Project

**Project:** Bank Network
**Institution:** Sri Sri University
**Faculty:** Faculty of Engineering and Technology
**Domain:** Banking Network Security

### Team

* Amrutanshu Puhan
* Aayush Nanda
* Ankit Das
* Nikita Priyadarshini

### Guides

* Dr. Prabhudutta Pradhan
* Ms. Neha Bagle

## ⚠️ Disclaimer

This project is an **academic network security simulation** developed for educational and research purposes. It does not represent a production banking infrastructure.

## ⭐ Key Takeaway

The project demonstrates how **segmentation + access control + encryption + redundancy + secure public-service isolation** can be combined to create a resilient banking network architecture.

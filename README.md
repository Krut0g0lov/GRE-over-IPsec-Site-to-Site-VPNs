# 🔐 GRE over IPsec Site-to-Site VPN Lab

![Cisco](https://img.shields.io/badge/Cisco-Networking-blue)
![VPN](https://img.shields.io/badge/VPN-GRE%20over%20IPsec-green)
![Routing](https://img.shields.io/badge/Routing-OSPF-orange)
![Platform](https://img.shields.io/badge/Platform-Cisco%20CML-lightgrey)

---

## 📚 Overview

This lab demonstrates how to build a **Site-to-Site VPN using GRE over IPsec** between two remote enterprise sites connected through an ISP network.

The tunnel allows dynamic routing using **OSPF**, enabling internal networks to be advertised securely across the VPN.

The topology simulates a real-world enterprise architecture with encrypted communication over an untrusted service provider network.

---

## 🗺️ Topology

![Topology](./Topology.png)

---

## 🧱 Lab Components

| Device | Role |
|------|------|
| **D1** | Distribution Switch / L3 Gateway (Site A) |
| **R1 – Antalya** | Edge Router (Site A) |
| **R2 – ISP** | Service Provider Router |
| **R3 – Sofia** | Edge Router (Site B) |
| **D2** | Distribution Switch / L3 Gateway (Site B) |
| **PC1 / PC2** | Clients in Site A |
| **PC3 / PC4** | Clients in Site B |

---

# 🌐 Network Addressing

## Site A

| Network | Description |
|------|------|
| 10.10.1.0/24 | PC2 LAN |
| 10.10.2.0/24 | PC1 LAN |
| 10.10.0.0/30 | D1 ↔ R1 |

---

## Site B

| Network | Description |
|------|------|
| 10.10.3.0/24 | PC3 LAN |
| 10.10.5.0/24 | PC4 LAN |
| 10.10.4.0/30 | R3 ↔ D2 |

---

## ISP Links

| Network | Description |
|------|------|
| 64.100.0.0/30 | R1 ↔ R2 |
| 64.100.1.0/30 | R2 ↔ R3 |

---

## GRE Tunnel Network

| Network |
|------|
| 172.16.1.0/30 |

---

# 🔐 VPN Architecture

The solution uses a **layered VPN design**.


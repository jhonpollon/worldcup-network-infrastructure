# World Cup Intercontinental Network Infrastructure Design

> 🌐 **Looking for the Spanish version? / ¿Buscás la versión en español?** > [Click aquí para leer la versión en Español](./README-es.md)

---

## 📝 Project Description
This project focuses on the design and implementation of a large-scale intercontinental WAN/LAN network topology to interconnect stadiums and headquarters across multiple countries (Canada, USA, and Mexico) to a central backbone node (World Router). The primary objective was to ensure full end-to-end connectivity, logical redundancy, and efficient international traffic distribution under strict IP addressing constraints.

---

## 🛠️ Technologies & Protocols Used
* **Simulator:** Cisco Packet Tracer.
* **IP Addressing:** Strict Classless scheme using **FLSM with a /14 subnet mask**, optimizing global IP address space allocations.
* **Dynamic Routing:** Global **OSPF (Area 0)** for automatic WAN and LAN route convergence powered by Dijkstra's algorithm.
* **Switching (Layer 2):** Cascaded Core and Access switches configuration, department-based **VLAN** segmentation (Servers, Logistics, Players, Public), and **802.1Q Trunking** links.
* **Network Services:** Inter-VLAN Routing (Router-on-a-Stick), **DNS Server** (Type A records for distributed name resolution), and **HTTP/HTTPS Servers** to host the official tournament platform (`www.mundial.com`).

---

## 🗺️ Network Architecture (Topology)
The global backbone core and base subnet allocations are structured as follows:

* **World Router (Central Backbone)**
* **Canada Core Network:** `10.64.0.0/14`
* **USA Core Network:** `10.128.0.0/14`
* **Mexico Core Network:** `10.192.0.0/14`

<img width="2334" height="775" alt="image" src="https://github.com/user-attachments/assets/410afc87-cdc5-4063-8a14-de27d1214d68" />

---

## 🔬 Connectivity Testing & Verification
The system's correct behavior was verified through the following successful deployment tests:
1. **OSPF Verification:** Checked the global routing table on the World Router , confirming OSPF neighbor adjacencies and successful remote subnet learning.
2. **DNS Resolution & Web Access:** Interactive end-to-end simulation from user hosts in remote stadiums (Mexico/USA), running `nslookup www.mundial.com` and successfully loading the web page hosted in the Vancouver Server.
3. **Layer 3 Verification (ICMP):** Packet tracing verified the seamless integration of Default Gateways and subinterfaces across the entire infrastructure.

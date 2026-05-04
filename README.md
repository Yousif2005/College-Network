<img width="1366" height="768" alt="College Network" src="https://github.com/user-attachments/assets/f27ef5ef-d872-4dc4-a4cd-1ca1cf33e5c7" />

# 🏫 College Network — Cisco Packet Tracer

A simulated multi-building college campus network designed and implemented using **Cisco Packet Tracer**. The topology covers the core infrastructure of a real-world academic environment, including administrative offices, faculty departments, student labs, a library, and a data center — all interconnected with proper segmentation, routing, and security policies.

---

## 📁 File

| File | Description |
|---|---|
| `College_Network.pkt` | Full Packet Tracer simulation file (open with Cisco Packet Tracer 7.x or later) |

---

## 🗺️ Network Overview

The network is divided into distinct zones reflecting the physical layout of a college campus:

- **Admin Block** — Management workstations, HR, and finance PCs
- **Faculty/Staff Block** — Department offices with wired access
- **Student Labs** — High-density PC labs with controlled internet access
- **Library** — Mixed wired and wireless access
- **Data Center** — Servers (DNS, DHCP, Web, Email)
- **Core Layer** — Central Layer 3 switching for inter-VLAN routing

---

## 🧱 Topology & Technologies Used

### Devices
- Cisco Routers (e.g., 2911 / 4331)
- Cisco Multilayer Switches (e.g., 3650 / 3560)
- Cisco Access Switches (e.g., 2960)
- Wireless Access Points
- End devices: PCs, Laptops, Servers, Printers, IP Phones

### Protocols & Features

| Feature | Details |
|---|---|
| **VLANs** | Separate VLANs per department/zone (Admin, Faculty, Students, Servers, Management) |
| **Inter-VLAN Routing** | Configured on the multilayer switch (SVI) or Router-on-a-Stick |
| **DHCP** | Centralized DHCP server; DHCP relay (ip helper-address) configured on SVIs |
| **DNS** | Internal DNS server resolving local hostnames |
| **Routing Protocol** | OSPF / Static routing between core and edge routers |
| **Spanning Tree** | STP/RSTP configured to prevent Layer 2 loops; PortFast on access ports |
| **Trunking** | 802.1Q trunk links between switches and routers |
| **Wireless** | SSID configured per zone (student/staff) with WPA2 security |
| **ACLs** | Access Control Lists to restrict student VLAN from reaching admin/server subnets |
| **NAT/PAT** | Overload NAT on the edge router for internet simulation |
| **SSH** | Remote management enabled on all network devices (SSH v2, local auth) |

---

## 🌐 IP Addressing Scheme

> Addresses are illustrative — open the `.pkt` file for the exact configuration.

| VLAN | Name | Subnet | Gateway |
|---|---|---|---|
| VLAN 10 | Admin | 192.168.10.0/24 | 192.168.10.1 |
| VLAN 20 | Faculty | 192.168.20.0/24 | 192.168.20.1 |
| VLAN 30 | Students | 192.168.30.0/24 | 192.168.30.1 |
| VLAN 40 | Library | 192.168.40.0/24 | 192.168.40.1 |
| VLAN 50 | Servers | 192.168.50.0/24 | 192.168.50.1 |
| VLAN 99 | Management | 192.168.99.0/24 | 192.168.99.1 |

---

## 🔒 Security Measures

- **Port Security** — MAC address limiting on access switch ports
- **ACLs** — Students blocked from accessing Admin and Server VLANs directly
- **SSH-only management** — Telnet disabled on all devices
- **Unused port shutdown** — All unused switch ports administratively disabled
- **VLAN segmentation** — Limits broadcast domain and lateral movement

---

## 🚀 How to Open

1. Download and install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (free with a Cisco NetAcad account).
2. Clone or download this repository.
3. Open `College_Network.pkt` in Packet Tracer.
4. Use **Simulation Mode** to trace packet flows between devices.
5. Click any device → **CLI** tab to inspect running configurations.

---

## 🧪 Testing Connectivity

Once the file is open, you can verify the network using the following:

```
# From any PC — ping default gateway
ping 192.168.X.1

# Cross-VLAN ping (Faculty → Server)
ping 192.168.50.10

# Test DNS resolution
nslookup college.local

# Access the web server
http://192.168.50.10   (via PC browser in Packet Tracer)
```

Use **Packet Tracer's PDU tool** (the envelope icon) for visual end-to-end connectivity tests.

---

## 📚 Learning Objectives

This project demonstrates practical skills in:

- Hierarchical network design (Core / Distribution / Access)
- VLAN design and inter-VLAN routing
- DHCP and DNS server configuration
- Routing protocol implementation (OSPF)
- Network security with ACLs and port security
- Wireless network setup
- NAT/PAT for simulated internet connectivity

---

## 🛠️ Tools

- [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) — v7.3 or later recommended

---

## 👤 Author

**Youssef AbdElmoaty**  
Cybersecurity & Networking Student  
[LinkedIn](#) · [GitHub](#)

---

## 📄 License

This project is for educational purposes. Feel free to use it as a reference or starting point for your own network design projects.

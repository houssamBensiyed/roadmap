# 🌐 THE ULTIMATE NETWORKING ROADMAP
### From Zero to Network Architect

> **Structure:** Phase → Modules → Sections
> **Estimated Duration:** ~6-9 Months (Dedicated Study)

---

## ⚡ PHASE 0 — FOUNDATIONS & PREREQUISITES
> *"You can't build a skyscraper without understanding physics."*

### Module 0.1: Computing Fundamentals
  - How computers communicate (hardware level)
  - Binary, Hexadecimal & Data Representation
  - Understanding Bits, Bytes, and Data Units (Kbps, Mbps, Gbps)

### Module 0.2: Operating System Basics
  - File systems & processes
  - Linux CLI essentials (`ls`, `cd`, `cat`, `grep`, `chmod`, `pipes`)
  - Windows Networking Utilities (Control Panel, `ncpa.cpl`, Services)

### Module 0.3: Essential Terminology
  - Node, Host, Client, Server, Peer
  - LAN, WAN, MAN, PAN, SAN
  - Bandwidth vs. Throughput vs. Latency vs. Jitter

> ### 🛠️ Phase 0 Project: **"My Network Journal"**
> Document your home network — identify every device, its IP, its MAC address, the router model, ISP details, and draw a physical + logical topology diagram using **draw.io**. Export it as a PDF.

---

## ⚡ PHASE 1 — NETWORK FUNDAMENTALS & THE OSI/TCP-IP MODELS
> *"The backbone of every networking conversation."*

### Module 1.1: Network Topologies & Types
  - Physical Topologies: Bus, Star, Ring, Mesh, Hybrid
  - Logical Topologies
  - Unicast, Broadcast, Multicast, Anycast

### Module 1.2: The OSI Model (Deep Dive — All 7 Layers)
  - **Layer 1 — Physical:** Cables (UTP, STP, Fiber, Coax), Connectors (RJ-45, LC, SC), Signaling, Hubs, Repeaters
  - **Layer 2 — Data Link:** Frames, MAC Addresses, Switches, ARP, Spanning Tree (STP), VLANs intro
  - **Layer 3 — Network:** IP Addressing, Packets, Routers, ICMP, TTL
  - **Layer 4 — Transport:** TCP vs UDP, Ports, 3-Way Handshake, Flow Control, Windowing
  - **Layer 5 — Session:** Session establishment, NetBIOS, PPTP
  - **Layer 6 — Presentation:** Encoding, Encryption overview, MIME, SSL/TLS intro
  - **Layer 7 — Application:** HTTP, FTP, SMTP, DNS, DHCP, SNMP

### Module 1.3: TCP/IP Model
  - Mapping OSI to TCP/IP (4 Layers)
  - Encapsulation & De-encapsulation (PDU lifecycle)
  - Packet dissection with **Wireshark** (first look)

### Module 1.4: Network Hardware
  - Hubs vs. Switches vs. Routers (core differences)
  - Firewalls, Access Points, Modems
  - Network Interface Cards (NICs)
  - Patch Panels, Media Converters

> ### 🛠️ Phase 1 Project: **"OSI Packet Tracer Lab"**
> Using **Cisco Packet Tracer**, build a network with 3 subnets connected by routers. Capture and label each PDU at every OSI layer as it travels from Host A to Host B. Create a visual PDF explaining encapsulation.

---

## ⚡ PHASE 2 — IP ADDRESSING & SUBNETTING MASTERY
> *"If you can't subnet, you can't network. Period."*

### Module 2.1: IPv4 Addressing
  - Binary to Decimal conversion (drill it)
  - IP Address structure: Network vs. Host portion
  - Classes: A, B, C, D (Multicast), E (Reserved)
  - Private vs. Public IPs (RFC 1918)
  - Loopback, APIPA, Link-Local addresses

### Module 2.2: Subnet Masking
  - Default Subnet Masks
  - ANDing process
  - Identifying Network ID, Broadcast Address, Usable Host Range
  - CIDR Notation (`/8`, `/16`, `/24`, `/27`, etc.)

### Module 2.3: Subnetting (The Hard Stuff)
  - Fixed-Length Subnet Masking (FLSM)
  - Variable-Length Subnet Masking (VLSM)
  - Supernetting / Route Summarization (CIDR)
  - Subnetting speed drills (you MUST be able to subnet in your head)

### Module 2.4: IPv6 Fundamentals
  - Why IPv6? Address exhaustion problem
  - IPv6 Address Format (128-bit, Hex)
  - Types: Global Unicast, Link-Local, Multicast, Anycast
  - EUI-64, SLAAC, DHCPv6
  - Dual Stack, Tunneling (6to4, Teredo), NAT64

> ### 🛠️ Phase 2 Project: **"The Subnetting Engine"**
> Build a **Python CLI tool** that takes an IP address and CIDR prefix as input and outputs: Network Address, Broadcast Address, Usable Range, Number of Hosts, Wildcard Mask, and Binary representation. Add a "quiz mode" that generates random subnetting questions.

---

## ⚡ PHASE 3 — CORE PROTOCOLS & SERVICES
> *"Protocols are the languages of the network."*

### Module 3.1: Address Resolution
  - ARP (Address Resolution Protocol) — how it works, ARP table, Gratuitous ARP
  - RARP, Proxy ARP
  - NDP (Neighbor Discovery Protocol — IPv6)

### Module 3.2: IP Configuration Services
  - DHCP: DORA Process (Discover, Offer, Request, Acknowledge)
  - DHCP Relay Agent
  - Static vs. Dynamic IP Assignment

### Module 3.3: Domain Name System (DNS) — Deep Dive
  - DNS Hierarchy: Root → TLD → Authoritative
  - Record Types: A, AAAA, CNAME, MX, NS, PTR, SRV, TXT, SOA
  - Recursive vs. Iterative queries
  - Forward vs. Reverse Lookup Zones
  - DNS Caching, TTL
  - Tools: `nslookup`, `dig`, `host`

### Module 3.4: Network Address Translation (NAT)
  - Static NAT, Dynamic NAT, PAT (Port Address Translation / NAT Overload)
  - NAT inside/outside, local/global
  - NAT traversal challenges

### Module 3.5: HTTP/HTTPS & Web Protocols
  - HTTP Methods (GET, POST, PUT, DELETE, PATCH)
  - Status Codes (1xx–5xx)
  - HTTP/1.1 vs HTTP/2 vs HTTP/3 (QUIC)
  - TLS Handshake (deep dive)
  - Certificates, CAs, Certificate Chains

### Module 3.6: Other Essential Protocols
  - FTP / SFTP / TFTP
  - SMTP / POP3 / IMAP
  - SNMP (v1, v2c, v3) & MIBs
  - NTP (Network Time Protocol)
  - Syslog
  - ICMP (Ping, Traceroute mechanics)
  - Telnet vs SSH

> ### 🛠️ Phase 3 Project: **"NetProbe — Protocol Analyzer"**
> Write a **Python script** using the `scapy` library that:
> 1. Sends ARP requests to discover all hosts on the local subnet
> 2. Performs DNS lookups for a list of domains and maps them
> 3. Captures and parses DHCP and ICMP traffic
> Display results in a clean tabular format using `rich` or `prettytable`.

---

## ⚡ PHASE 4 — SWITCHING & VLANs
> *"Layer 2 is where the real magic happens in enterprise networks."*

### Module 4.1: Ethernet Switching
  - How switches learn MAC addresses (MAC Address Table)
  - Store-and-Forward vs. Cut-Through switching
  - Collision Domains vs. Broadcast Domains
  - Duplex modes: Half vs Full

### Module 4.2: VLANs (Virtual LANs)
  - Why VLANs? Segmentation, Security, Performance
  - Access Ports vs. Trunk Ports
  - 802.1Q Tagging (VLAN Tagging)
  - Native VLAN & its security implications
  - VLAN Trunking Protocol (VTP) — Modes: Server, Client, Transparent
  - Inter-VLAN Routing (Router-on-a-Stick, SVIs / Layer 3 Switches)

### Module 4.3: Spanning Tree Protocol (STP)
  - The problem: Layer 2 Loops & Broadcast Storms
  - STP (802.1D): Root Bridge Election, Port Roles (Root, Designated, Blocked)
  - RSTP (802.1W): Faster convergence
  - MSTP (802.1S)
  - PortFast, BPDU Guard, Root Guard

### Module 4.4: EtherChannel / Link Aggregation
  - LACP (802.3ad) vs. PAgP
  - Configuration & Load Balancing methods

> ### 🛠️ Phase 4 Project: **"Enterprise Campus Network Simulation"**
> In **Cisco Packet Tracer / GNS3**, design a 3-floor office building network:
> - Floor 1: Sales VLAN (VLAN 10), Floor 2: Engineering VLAN (VLAN 20), Floor 3: Management VLAN (VLAN 30)
> - Configure trunking between switches, Inter-VLAN routing via a Layer 3 switch
> - Implement STP with a designated Root Bridge
> - Set up EtherChannel between core switches
> - Verify with `show vlan`, `show spanning-tree`, `show etherchannel`

---

## ⚡ PHASE 5 — ROUTING
> *"Routing is the art of choosing the best path."*

### Module 5.1: Routing Fundamentals
  - How routers make forwarding decisions
  - Routing Table anatomy (`show ip route`)
  - Connected, Static & Dynamic routes
  - Administrative Distance & Metrics
  - Default Route / Gateway of Last Resort
  - Floating Static Routes

### Module 5.2: Static Routing
  - Next-hop vs. Exit-interface
  - Default static route (`0.0.0.0/0`)
  - Use cases and limitations

### Module 5.3: Dynamic Routing — Distance Vector
  - RIP (v1 & v2): Hop Count, Timers, Split Horizon, Poison Reverse
  - EIGRP: Successor, Feasible Successor, DUAL Algorithm, Composite Metric (Bandwidth + Delay)

### Module 5.4: Dynamic Routing — Link State
  - OSPF (Single Area & Multi-Area)
    - LSAs, Areas, ABR, ASBR
    - DR/BDR Election
    - OSPF Cost, SPF Algorithm (Dijkstra)
    - OSPF Neighbor States (Down → Full)
  - IS-IS (Intermediate System to Intermediate System) — overview

### Module 5.5: Dynamic Routing — Path Vector
  - BGP (Border Gateway Protocol)
    - iBGP vs. eBGP
    - AS Numbers, Path Attributes
    - BGP Route Selection Process
    - Peering, Route Reflectors, Confederations
    - Why BGP runs the Internet

### Module 5.6: Route Redistribution & Filtering
  - Redistributing between protocols
  - Route Maps, Prefix Lists, ACLs for route filtering
  - Policy-Based Routing (PBR)

> ### 🛠️ Phase 5 Project: **"Multi-Protocol Routing Lab"**
> In **GNS3 / EVE-NG**, build a network with 4 routers:
> - Router 1-2: OSPF Area 0
> - Router 2-3: EIGRP AS 100
> - Router 3-4: Simulated ISP via static/BGP
> - Perform mutual redistribution between OSPF and EIGRP
> - Verify with `show ip route`, `show ip ospf neighbor`, `show ip eigrp topology`
> - Document the routing table of each router and explain path selection

---

## ⚡ PHASE 6 — NETWORK SECURITY
> *"A network without security is an invitation."*

### Module 6.1: Security Fundamentals
  - CIA Triad (Confidentiality, Integrity, Availability)
  - AAA Framework (Authentication, Authorization, Accounting)
  - Threat Landscape: Malware, Phishing, Social Engineering
  - Zero Trust Architecture (overview)

### Module 6.2: Access Control Lists (ACLs)
  - Standard ACLs (based on source IP)
  - Extended ACLs (source, destination, port, protocol)
  - Named ACLs
  - ACL placement rules (Standard: close to destination; Extended: close to source)
  - Wildcard Masks

### Module 6.3: Firewalls & IDS/IPS
  - Stateless vs. Stateful Firewalls
  - Next-Generation Firewalls (NGFW)
  - IDS vs. IPS (Intrusion Detection / Prevention)
  - DMZ Architecture
  - UTM (Unified Threat Management)

### Module 6.4: VPN (Virtual Private Networks)
  - Site-to-Site VPN vs. Remote Access VPN
  - IPsec: AH, ESP, IKE (Phase 1 & Phase 2), SA
  - SSL/TLS VPN
  - GRE Tunnels, GRE over IPsec
  - WireGuard (modern VPN)

### Module 6.5: Wireless Security
  - WEP (broken) → WPA → WPA2 (AES/CCMP) → WPA3 (SAE)
  - EAP, RADIUS, 802.1X Authentication
  - Rogue APs, Evil Twin, Deauthentication Attacks

### Module 6.6: Layer 2 Security
  - DHCP Snooping
  - Dynamic ARP Inspection (DAI)
  - Port Security (sticky MAC, violation modes)
  - 802.1X Port-Based Authentication
  - VLAN Hopping attacks & mitigation
  - MAC Flooding & MAC Spoofing

### Module 6.7: Cryptography Essentials for Networking
  - Symmetric vs. Asymmetric Encryption
  - Hashing (MD5, SHA-256, SHA-3)
  - Digital Signatures & Certificates
  - PKI (Public Key Infrastructure)
  - TLS 1.3 Deep Dive

> ### 🛠️ Phase 6 Project: **"Fortress Network"**
> Build a secure network in **GNS3/EVE-NG + pfSense**:
> - Configure a pfSense firewall with DMZ, LAN, and WAN zones
> - Set up ACLs to restrict inter-zone traffic
> - Deploy a Site-to-Site IPsec VPN between two branch networks
> - Enable DHCP Snooping & DAI on switches
> - Set up a RADIUS server (FreeRADIUS) for 802.1X authentication
> - Run a vulnerability scan using **Nmap** and document findings

---

## ⚡ PHASE 7 — WIRELESS NETWORKING
> *"The invisible wire."*

### Module 7.1: Wireless Fundamentals
  - Radio Frequency (RF) Basics: Frequency, Wavelength, Amplitude
  - 802.11 Standards: a/b/g/n (Wi-Fi 4) / ac (Wi-Fi 5) / ax (Wi-Fi 6/6E) / be (Wi-Fi 7)
  - 2.4 GHz vs. 5 GHz vs. 6 GHz bands
  - Channels, Channel Bonding, Channel Overlap

### Module 7.2: Wireless Architecture
  - Autonomous APs vs. Lightweight APs + WLC (Wireless LAN Controller)
  - CAPWAP Protocol
  - BSS, ESS, SSID, BSSID
  - Roaming (Layer 2 & Layer 3)

### Module 7.3: Wireless Design & Site Surveys
  - Heat Maps, Signal-to-Noise Ratio (SNR)
  - AP Placement, Power Levels
  - High-Density Deployments
  - Mesh Networking

> ### 🛠️ Phase 7 Project: **"Wireless Audit Toolkit"**
> Using a **Linux laptop with a compatible wireless adapter**:
> 1. Perform a wireless site survey of your location using **Ekahau / NetSpot**
> 2. Use `aircrack-ng` suite (in a lab!) to understand WPA2 handshake captures
> 3. Generate a heat map and write a report recommending optimal AP placement
> 4. Document all SSIDs, channels, signal strengths, and security modes in your area

---

## ⚡ PHASE 8 — NETWORK SERVICES & INFRASTRUCTURE
> *"The services that make the network usable."*

### Module 8.1: DHCP (Advanced)
  - DHCP Failover & High Availability
  - DHCP Scopes, Reservations, Options (Option 43, 150)
  - DHCPv6 Prefix Delegation

### Module 8.2: DNS (Advanced)
  - DNSSEC (DNS Security Extensions)
  - DNS over HTTPS (DoH) / DNS over TLS (DoT)
  - Split-Horizon DNS
  - DNS Load Balancing
  - Setting up **BIND9** / **Unbound** from scratch

### Module 8.3: Load Balancing & High Availability
  - Layer 4 vs. Layer 7 Load Balancing
  - Algorithms: Round Robin, Least Connections, IP Hash, Weighted
  - Health Checks & Failover
  - HSRP, VRRP, GLBP (First Hop Redundancy Protocols)
  - HAProxy / Nginx as load balancers

### Module 8.4: Proxy Servers & Caching
  - Forward Proxy vs. Reverse Proxy
  - Transparent Proxy
  - Squid, Nginx, Envoy
  - CDN concepts (Content Delivery Networks)

### Module 8.5: Directory Services
  - LDAP (Lightweight Directory Access Protocol)
  - Active Directory basics
  - RADIUS & TACACS+

> ### 🛠️ Phase 8 Project: **"Production-Grade Infrastructure Stack"**
> On **2-3 Linux VMs** (VirtualBox/Proxmox):
> - Set up **BIND9** as a primary + secondary DNS server with zone transfers
> - Configure **ISC DHCP Server** with multiple scopes and reservations
> - Deploy **HAProxy** as a load balancer in front of 2 Nginx web servers
> - Configure **VRRP** (using `keepalived`) for gateway redundancy
> - Test failover scenarios and document recovery times

---

## ⚡ PHASE 9 — NETWORK MONITORING, TROUBLESHOOTING & AUTOMATION
> *"You can't fix what you can't see."*

### Module 9.1: Network Monitoring
  - SNMP (v2c, v3): Agents, Managers, MIBs, OIDs, Traps
  - NetFlow / sFlow / IPFIX for traffic analysis
  - Monitoring Tools: **Zabbix**, **Nagios**, **PRTG**, **LibreNMS**, **Prometheus + Grafana**
  - Syslog Servers (Graylog, rsyslog, ELK Stack)

### Module 9.2: Packet Analysis & Deep Inspection
  - **Wireshark** mastery: Capture filters vs. Display filters
  - Following TCP streams
  - Analyzing TLS handshakes
  - Detecting anomalies (retransmissions, resets, malformed packets)
  - **tcpdump** for CLI-based captures

### Module 9.3: Troubleshooting Methodology
  - The 7-Layer approach: bottom-up, top-down, divide-and-conquer
  - Essential commands:
    - `ping`, `traceroute`/`tracert`, `pathping`
    - `ipconfig`/`ifconfig`/`ip addr`
    - `netstat`/`ss`
    - `arp -a`, `route print`/`ip route`
    - `nslookup`, `dig`
    - `mtr`, `iperf3`, `curl`, `telnet`
  - Cable testing, PoE troubleshooting

### Module 9.4: Network Automation & Programmability
  - Why automate? (Scale, Consistency, Speed)
  - **Python** for networking: `paramiko`, `netmiko`, `napalm`, `scapy`
  - REST APIs & network device APIs (Cisco DNA Center, Meraki API)
  - NETCONF / RESTCONF / gNMI / YANG Models
  - **Ansible** for network automation (playbooks, inventories, modules for IOS/NXOS/Junos)
  - Infrastructure as Code (IaC) for networking: **Terraform** for cloud networking

### Module 9.5: Configuration Management
  - Version-controlled configs (Git for network configs)
  - Configuration backup strategies
  - Compliance checking (Batfish, Oxidized)

> ### 🛠️ Phase 9 Project: **"NetOps Dashboard & Automation Suite"**
> 1. Deploy **LibreNMS** or **Zabbix** to monitor 5+ network devices (real or virtual in GNS3)
> 2. Write **Ansible playbooks** to:
>    - Backup running configs of all routers/switches to a Git repo
>    - Push VLAN configurations to multiple switches simultaneously
>    - Generate compliance reports
> 3. Build a **Python + Flask** web dashboard that:
>    - Displays live device status (up/down via ICMP)
>    - Shows interface statistics (via SNMP using `pysnmp`)
>    - Integrates with **Grafana** for traffic visualization
> 4. Set up **Syslog** aggregation with the **ELK Stack**

---

## ⚡ PHASE 10 — CLOUD & SOFTWARE-DEFINED NETWORKING
> *"The future of networking is programmable."*

### Module 10.1: Cloud Networking
  - AWS VPC: Subnets, Route Tables, IGW, NAT GW, Security Groups, NACLs
  - Azure VNet / GCP VPC (parallels)
  - Cloud Load Balancers (ALB, NLB, GLB)
  - VPC Peering, Transit Gateway, PrivateLink
  - Hybrid Cloud Connectivity: Direct Connect / ExpressRoute / Cloud Interconnect

### Module 10.2: Software-Defined Networking (SDN)
  - Traditional vs. SDN Architecture
  - Control Plane vs. Data Plane vs. Management Plane (separation)
  - OpenFlow Protocol
  - SDN Controllers (OpenDaylight, ONOS, Floodlight)
  - SD-WAN: Concepts, Architectures, Vendors (Cisco Viptela, Fortinet, VMware VeloCloud)

### Module 10.3: Network Functions Virtualization (NFV)
  - Virtual Routers, Virtual Firewalls, Virtual Load Balancers
  - VNF, MANO, NFVI
  - Relationship between SDN & NFV

### Module 10.4: Container Networking
  - Docker Networking: Bridge, Host, Overlay, Macvlan
  - Kubernetes Networking Model
    - Pod-to-Pod, Service-to-Pod, External-to-Service
    - CNI Plugins (Calico, Cilium, Flannel)
    - Ingress Controllers, Network Policies
  - Service Mesh (Istio, Linkerd) — overview

### Module 10.5: Modern Networking Paradigms
  - SASE (Secure Access Service Edge)
  - Zero Trust Network Access (ZTNA)
  - Intent-Based Networking (IBN)
  - AIOps for Networking

> ### 🛠️ Phase 10 Project: **"Cloud-Native Micro-Segmented Network"**
> 1. On **AWS Free Tier**:
>    - Build a VPC with public + private subnets across 2 AZs
>    - Deploy an ALB → 2 EC2 instances running Nginx
>    - Set up a Site-to-Site VPN to a simulated on-prem (another VPC or local GNS3)
>    - Implement Security Groups + NACLs with least-privilege rules
> 2. On a **local Kubernetes cluster** (minikube / k3s):
>    - Deploy 3 microservices
>    - Install **Calico** CNI with Network Policies to enforce micro-segmentation
>    - Set up an **Nginx Ingress Controller** with TLS termination
>    - Visualize pod traffic using **Hubble** (Cilium)

---

## 📊 PHASE MAP (Visual Summary)

```
Phase 0  ██░░░░░░░░░░  Foundations
Phase 1  ████░░░░░░░░  OSI / TCP-IP Models
Phase 2  ██████░░░░░░  IP Addressing & Subnetting
Phase 3  ████████░░░░  Core Protocols (DNS, DHCP, HTTP, NAT)
Phase 4  ██████████░░  Switching & VLANs
Phase 5  ████████████  Routing (OSPF, EIGRP, BGP)
Phase 6  ████████████  Network Security (Firewalls, VPN, ACL)
Phase 7  ████████████  Wireless Networking
Phase 8  ████████████  Infrastructure Services (LB, HA, DNS+)
Phase 9  ████████████  Monitoring, Troubleshooting & Automation
Phase 10 ████████████  Cloud, SDN, Containers & The Future
```

---

## 🎯 CERTIFICATION ALIGNMENT

| Phase | Certification |
|-------|--------------|
| 0 – 4 | **CompTIA Network+ (N10-009)** |
| 1 – 6 | **Cisco CCNA 200-301** |
| 5 – 8 | **Cisco CCNP ENCOR 350-401** |
| 6 | **CompTIA Security+** |
| 9 – 10 | **Cisco DevNet Associate** / **AWS Advanced Networking** |

---

## 📚 RECOMMENDED RESOURCES

| Resource | Type |
|----------|------|
| *Computer Networking: A Top-Down Approach* — Kurose & Ross | 📖 Book |
| *TCP/IP Illustrated, Vol 1* — W. Richard Stevens | 📖 Book (Bible) |
| *Network Warrior* — Gary Donahue | 📖 Book |
| Jeremy's IT Lab (YouTube) | 🎥 CCNA Course |
| Professor Messer (YouTube) | 🎥 Network+ Course |
| Practical Networking (YouTube) | 🎥 Concepts |
| Cisco Packet Tracer | 🧪 Lab Tool (Free) |
| GNS3 / EVE-NG | 🧪 Lab Tool (Advanced) |
| TryHackMe — Network Fundamentals | 🧪 Hands-On |
| Wireshark Sample Captures | 🧪 Practice Files |

---

> ### 💡 Final Advice
> **"Don't just read about packets — capture them. Don't just memorize subnets — calculate them. Don't just study routing — build labs where it breaks."**
>
> The difference between a *networking student* and a *network engineer* is **lab hours**. Every phase above should have you spending **60% of your time in labs**, not in books.

---

*This roadmap takes you from "What's an IP address?" to "I can design, secure, automate, and troubleshoot enterprise + cloud networks."* 🚀
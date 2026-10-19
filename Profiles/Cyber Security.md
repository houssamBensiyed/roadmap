# 🛡️ THE DEFINITIVE CYBERSECURITY ROADMAP
## From Zero to Expert — Every Concept, Every Layer, Nothing Skipped

---

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                         CYBERSECURITY — MASTERY LADDER                              ║
║                                                                                      ║
║   🔴 PHASE 8 ─ Advanced & Emerging Threats           [Principal Security Architect]  ║
║       ▲                                                                              ║
║   📋 PHASE 7 ─ GRC & Security Leadership             [CISO / Security Director]      ║
║       ▲                                                                              ║
║   💀 PHASE 6 ─ Advanced Offensive Security            [Senior Red Teamer / Researcher]║
║       ▲                                                                              ║
║   ☁️ PHASE 5 ─ Specialized Security Domains           [Security Engineer]             ║
║       ▲                                                                              ║
║   🔵 PHASE 4 ─ Defensive Security (Blue Team)        [SOC Analyst / DFIR]            ║
║       ▲                                                                              ║
║   🗡️ PHASE 3 ─ Offensive Security (Red Team)          [Penetration Tester]            ║
║       ▲                                                                              ║
║   🔐 PHASE 2 ─ Security Fundamentals                 [Junior Security Analyst]       ║
║       ▲                                                                              ║
║   🧱 PHASE 1 ─ IT & Networking Foundations            [Starting Point]                ║
║                                                                                      ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---
---
---

# 🧱 PHASE 1: IT & NETWORKING FOUNDATIONS
### 📅 Duration: Months 1–3
### 🎯 Goal: Master the infrastructure that you will later attack and defend
### 👤 Level: Starting Point → IT Fundamentals
### 📜 Certifications: CompTIA A+, CompTIA Network+, Linux Essentials

---

## Module 1.1: Computer Hardware & Operating Systems

### Section 1.1.1 — Hardware Fundamentals
```
├── CPU Architecture: x86, x64, ARM — Instruction sets, Registers
├── Memory: RAM, ROM, Cache hierarchy (L1/L2/L3), Virtual memory
├── Storage: HDD vs SSD, RAID levels (0, 1, 5, 6, 10), NVMe
├── BIOS/UEFI: Boot process, Secure Boot, TPM (Trusted Platform Module)
├── Peripherals: USB, Thunderbolt, PCI/PCIe — Attack surfaces
├── Firmware: What it is, Why it matters for security, Firmware attacks
└── Embedded Systems: Microcontrollers, IoT devices, Attack surface basics
```

### Section 1.1.2 — Windows Operating System
```
├── Windows Architecture:
│   ├── Kernel Mode vs User Mode: Ring 0 vs Ring 3
│   ├── Windows Registry: Hives, Keys, Values — Forensic goldmine
│   ├── File Systems: NTFS (permissions, ADS), FAT32, ReFS
│   ├── Processes & Services: Task Manager, Services.msc, svchost.exe
│   └── DLLs: Dynamic Link Libraries, DLL search order, DLL hijacking
├── Windows Security Features:
│   ├── User Account Control (UAC): Privilege elevation, Bypass techniques
│   ├── Windows Defender: Antivirus, Firewall, Exploit Guard
│   ├── BitLocker: Full disk encryption, TPM integration
│   ├── NTFS Permissions: ACLs, DACLs, SACLs, Inheritance
│   ├── Group Policy (GPO): Centralized security configuration
│   ├── Windows Event Logs: Security, System, Application — Event IDs to know
│   └── Credential Storage: SAM database, LSASS, Credential Manager
├── Active Directory (AD):
│   ├── Domain Controller, Forest, Tree, OU structure
│   ├── LDAP: Directory queries, Enumeration
│   ├── Kerberos Authentication: TGT, TGS, Service tickets
│   ├── NTLM: Legacy auth, Pass-the-Hash fundamentals
│   ├── Group Policy Objects: Security baselines, Software restriction
│   └── AD Certificate Services (ADCS): PKI, Certificate-based auth
├── PowerShell:
│   ├── Cmdlets: Get-Process, Get-Service, Get-EventLog
│   ├── Scripting: Variables, Loops, Functions, Error handling
│   ├── Remoting: WinRM, PSSession, Invoke-Command
│   ├── PowerShell Logging: Script block logging, Transcription
│   └── Security: Execution policies, AMSI (Anti-Malware Scan Interface)
└── Windows CLI: cmd.exe, net commands, wmic, netstat, ipconfig, tasklist
```

### Section 1.1.3 — Linux Operating System
```
├── Linux Architecture:
│   ├── Kernel: Monolithic, Modules, /proc, /sys, dmesg
│   ├── File System Hierarchy: /, /etc, /var, /home, /tmp, /opt, /dev, /proc
│   ├── File Systems: ext4, XFS, Btrfs, tmpfs
│   ├── Process Management: PID, PPID, init/systemd, fork/exec
│   ├── Package Management: apt/dpkg (Debian), yum/dnf (RHEL), pacman (Arch)
│   └── Boot Process: GRUB → Kernel → init/systemd → Runlevels/Targets
├── Linux Security:
│   ├── File Permissions: rwx, chmod, chown, chgrp, Octal notation
│   ├── Special Permissions: SUID, SGID, Sticky bit — Privilege escalation targets
│   ├── Users & Groups: /etc/passwd, /etc/shadow, /etc/group, sudo, su
│   ├── PAM (Pluggable Authentication Modules): Auth configuration
│   ├── SELinux / AppArmor: Mandatory Access Control
│   ├── iptables / nftables: Firewall rules, Chains (INPUT, OUTPUT, FORWARD)
│   ├── SSH: Key-based auth, ssh-keygen, sshd_config hardening, SSH tunneling
│   ├── Logging: syslog, journalctl, /var/log/auth.log, /var/log/syslog
│   └── File Integrity: md5sum, sha256sum, AIDE, Tripwire
├── Essential Linux Commands:
│   ├── Navigation: ls, cd, pwd, find, locate, which, whereis
│   ├── File Operations: cat, less, head, tail, grep, awk, sed, cut, sort, uniq
│   ├── System: ps, top, htop, df, du, free, uname, id, whoami
│   ├── Network: ifconfig/ip, ss/netstat, ping, traceroute, dig, nslookup, curl, wget
│   ├── Process: kill, killall, bg, fg, nohup, jobs, cron, at
│   ├── Archives: tar, gzip, zip, unzip
│   ├── Text Editing: vim, nano — at minimum be proficient in one
│   └── Pipes & Redirection: |, >, >>, <, 2>, 2>&1, tee
├── Bash Scripting:
│   ├── Variables, Conditionals (if/elif/else), Loops (for, while)
│   ├── Functions, Arrays, String manipulation
│   ├── Command substitution: $(), ``
│   ├── Exit codes: $?, set -e, trap
│   └── Automation: Cron jobs, System administration scripts
└── Linux Distributions for Security:
    ├── Kali Linux: Penetration testing (primary offensive distro)
    ├── Parrot Security: Alternative to Kali, Privacy-focused
    ├── Ubuntu Server / Debian: Production server hardening
    ├── RHEL / CentOS / Rocky Linux: Enterprise server environments
    └── Arch Linux: Deep understanding of Linux internals
```

---

## Module 1.2: Networking Fundamentals

### Section 1.2.1 — OSI Model & TCP/IP (Deep Dive)
```
├── Layer 1 — Physical:
│   ├── Cables: Ethernet (Cat5e/6/6a/7), Fiber (Single/Multi-mode), Coaxial
│   ├── Wireless: Radio frequencies, Antennas, Signal propagation
│   ├── Hubs, Repeaters, Media converters
│   └── Security: Physical access control, Cable tapping, Tempest attacks
├── Layer 2 — Data Link:
│   ├── MAC Addresses: 48-bit, OUI, Unicast/Broadcast/Multicast
│   ├── Ethernet Frames: Structure, MTU, Jumbo frames
│   ├── Switches: MAC address table, CAM table, VLANs, Trunking (802.1Q)
│   ├── ARP: Address Resolution Protocol, ARP cache, Gratuitous ARP
│   ├── STP: Spanning Tree Protocol, Loop prevention
│   ├── Attacks: MAC flooding, ARP spoofing/poisoning, VLAN hopping, CAM overflow
│   └── Defenses: Port security, Dynamic ARP Inspection (DAI), DHCP snooping
├── Layer 3 — Network:
│   ├── IP Addressing:
│   │   ├── IPv4: 32-bit, Dotted decimal, Classes (A/B/C/D/E)
│   │   ├── Subnetting: CIDR notation, Subnet masks, Network/Host/Broadcast
│   │   ├── Private Ranges: 10.x, 172.16-31.x, 192.168.x
│   │   ├── IPv6: 128-bit, Hex notation, Link-local, Global unicast
│   │   └── NAT: Static, Dynamic, PAT (Port Address Translation)
│   ├── Routing:
│   │   ├── Static Routes: Manual configuration
│   │   ├── Dynamic Routing: OSPF, BGP, EIGRP, RIP
│   │   ├── Routing Tables: Longest prefix match
│   │   └── BGP: Internet backbone, AS numbers, BGP hijacking attacks
│   ├── ICMP: Ping, Traceroute, ICMP types/codes, ICMP tunneling
│   ├── Attacks: IP spoofing, Route poisoning, ICMP redirect, Fragmentation attacks
│   └── Defenses: ACLs, Ingress/Egress filtering, uRPF
├── Layer 4 — Transport:
│   ├── TCP:
│   │   ├── 3-Way Handshake: SYN → SYN-ACK → ACK
│   │   ├── Flags: SYN, ACK, FIN, RST, PSH, URG
│   │   ├── Ports: Well-known (0-1023), Registered (1024-49151), Ephemeral (49152-65535)
│   │   ├── Flow Control: Window size, Sliding window
│   │   ├── Congestion Control: Slow start, AIMD
│   │   └── Attacks: SYN flood, RST attacks, Session hijacking, Port scanning
│   ├── UDP:
│   │   ├── Connectionless: No handshake, No reliability
│   │   ├── Use cases: DNS, DHCP, SNMP, VoIP, Gaming, Video streaming
│   │   └── Attacks: UDP flood, Amplification attacks (DNS, NTP, SSDP)
│   └── Important Ports to Memorize:
│       ├── 20/21 FTP, 22 SSH, 23 Telnet, 25 SMTP, 53 DNS
│       ├── 67/68 DHCP, 80 HTTP, 110 POP3, 143 IMAP, 443 HTTPS
│       ├── 389 LDAP, 636 LDAPS, 445 SMB, 3389 RDP, 3306 MySQL
│       ├── 5432 PostgreSQL, 1433 MSSQL, 8080 HTTP-Alt, 8443 HTTPS-Alt
│       └── 88 Kerberos, 135 RPC, 161/162 SNMP, 514 Syslog, 1521 Oracle
├── Layer 5-6 — Session & Presentation:
│   ├── Session Management: Establishment, Maintenance, Termination
│   ├── Encoding: ASCII, Unicode, Base64, URL encoding
│   ├── Compression: gzip, deflate, Brotli
│   └── Encryption: SSL/TLS (covered in detail in Phase 2)
└── Layer 7 — Application:
    ├── HTTP/HTTPS: Methods (GET/POST/PUT/DELETE), Headers, Status codes, Cookies
    ├── DNS: Recursive/Iterative queries, Record types (A, AAAA, CNAME, MX, TXT, NS, SOA, PTR)
    │   └── DNS Security: DNSSEC, DNS over HTTPS (DoH), DNS over TLS (DoT)
    ├── DHCP: DORA process (Discover, Offer, Request, Acknowledge)
    ├── SMTP/POP3/IMAP: Email protocols, SPF, DKIM, DMARC
    ├── FTP/SFTP/SCP: File transfer, Active vs Passive FTP
    ├── SMB/CIFS: Windows file sharing, Port 445, EternalBlue
    ├── SNMP: Network management, v1/v2c (community strings), v3 (encrypted)
    ├── LDAP: Directory services, Queries, Injection attacks
    └── RDP: Remote Desktop Protocol, Port 3389, BlueKeep
```

### Section 1.2.2 — Network Architecture & Design
```
├── Network Topologies: Star, Bus, Ring, Mesh, Hybrid
├── Network Segmentation:
│   ├── VLANs: Virtual LANs, 802.1Q tagging, Inter-VLAN routing
│   ├── DMZ: Demilitarized Zone, Bastion hosts
│   ├── Microsegmentation: Zero Trust networking
│   └── Air-Gapped Networks: Physically isolated (military, SCADA)
├── Network Devices:
│   ├── Router: Layer 3, Connects networks, ACLs
│   ├── Switch: Layer 2 (managed/unmanaged), Layer 3 switch
│   ├── Firewall: Stateless, Stateful, NGFW (Next-Gen Firewall)
│   ├── IDS/IPS: Intrusion Detection/Prevention, Signature vs Anomaly
│   ├── WAF: Web Application Firewall, ModSecurity, AWS WAF
│   ├── Load Balancer: L4/L7, SSL offloading
│   ├── Proxy: Forward proxy, Reverse proxy, Transparent proxy
│   └── VPN Concentrator: Site-to-site, Remote access VPN
├── Wireless Networking:
│   ├── Standards: 802.11a/b/g/n/ac/ax (Wi-Fi 6/6E)
│   ├── Security: WEP (broken), WPA, WPA2, WPA3
│   ├── Authentication: PSK, Enterprise (RADIUS/802.1X)
│   ├── Attacks: Evil twin, Deauth, WPS attacks, KRACK, Dragonblood
│   └── Tools: aircrack-ng, airmon-ng, airodump-ng, Wifite
├── VPN Technologies:
│   ├── IPSec: AH, ESP, IKE, Tunnel vs Transport mode
│   ├── SSL/TLS VPN: OpenVPN, Client-based
│   ├── WireGuard: Modern, Fast, Simple
│   └── Site-to-Site vs Remote Access: Use cases, Configuration
└── Network Monitoring:
    ├── Packet Capture: Wireshark, tcpdump, tshark
    ├── NetFlow / sFlow: Traffic analysis, Bandwidth monitoring
    ├── SNMP Monitoring: Nagios, Zabbix, PRTG
    └── Network Diagrams: Physical, Logical, Document everything
```

### Section 1.2.3 — Packet Analysis (Wireshark Mastery)
```
├── Wireshark Fundamentals:
│   ├── Capture Filters: host, port, net, tcp, udp — BPF syntax
│   ├── Display Filters: ip.addr, tcp.port, http.request.method, dns.qry.name
│   ├── Following Streams: TCP stream, HTTP stream, TLS stream
│   ├── Protocol Hierarchy: Statistics → Protocol Hierarchy
│   └── Conversations: Identify top talkers
├── Protocol Analysis:
│   ├── TCP Handshake Analysis: Identify SYN scans, RST floods
│   ├── DNS Analysis: Identify DNS tunneling, Exfiltration, DGA domains
│   ├── HTTP Analysis: Credentials in cleartext, Suspicious user-agents
│   ├── TLS Analysis: Certificate inspection, JA3/JA3S fingerprinting
│   ├── ARP Analysis: Detect ARP spoofing/poisoning
│   └── SMB Analysis: File transfers, Lateral movement
├── Anomaly Detection in Packets:
│   ├── Unusual ports: Known malware C2 ports
│   ├── Beaconing: Regular interval connections (C2 callback)
│   ├── Large DNS queries: DNS exfiltration
│   ├── Encrypted traffic on unusual ports: Tunneling
│   └── Fragmented packets: Evasion techniques
└── Tools: Wireshark, tcpdump, tshark, NetworkMiner, Zeek (Bro)
```

---

## Module 1.3: Virtualization & Lab Setup

### Section 1.3.1 — Virtualization Technologies
```
├── Type 1 Hypervisors: ESXi, Hyper-V, KVM, Xen — Bare metal
├── Type 2 Hypervisors: VirtualBox, VMware Workstation — Hosted
├── Containers: Docker basics (for security tool deployment)
├── Networking in VMs:
│   ├── NAT: VM accesses internet via host
│   ├── Bridged: VM on same network as host
│   ├── Host-Only: Isolated network between host and VMs
│   └── Internal Network: Isolated between VMs only
└── Snapshots: Restore to known-good state, Essential for malware analysis
```

### Section 1.3.2 — Building Your Security Lab
```
├── Offensive Lab:
│   ├── Kali Linux: Attack machine (latest rolling release)
│   ├── Metasploitable 2/3: Intentionally vulnerable Linux
│   ├── DVWA: Damn Vulnerable Web Application
│   ├── VulnHub VMs: HackTheBox-style downloadable VMs
│   ├── Windows Server (eval): AD lab target
│   └── Network: Host-only or internal network (NEVER bridge to production!)
├── Defensive Lab:
│   ├── Security Onion: Full NSM (Network Security Monitoring) suite
│   ├── Splunk Free: SIEM for log analysis practice
│   ├── ELK Stack: Elasticsearch + Logstash + Kibana
│   ├── Wazuh: Host-based IDS, File integrity monitoring
│   └── pfSense/OPNsense: Firewall, IDS/IPS (Suricata/Snort)
├── Cloud Lab:
│   ├── AWS Free Tier: EC2, S3, IAM, CloudTrail
│   ├── Azure Free Tier: VMs, AD, Sentinel
│   └── GCP Free Tier: Compute, Networking
└── Practice Platforms:
    ├── TryHackMe: Guided learning paths, Beginner-friendly
    ├── HackTheBox: Realistic challenges, Intermediate+
    ├── PicoCTF: Beginner CTF challenges
    ├── OverTheWire (Bandit): Linux command-line challenges
    ├── CyberDefenders: Blue team challenges
    └── LetsDefend: SOC analyst training
```

---

> ### 🛠️ PHASE 1 PROJECT: **Home Security Lab + Network Recon Report**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │              HOME SECURITY LAB + NETWORK RECON                  │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ LAB SETUP:                                                      │
> │  ✅ Build a virtual lab with 5+ VMs:                             │
> │     • Kali Linux (attacker)                                     │
> │     • Ubuntu Server (target web server)                         │
> │     • Windows Server 2019 (Active Directory DC)                 │
> │     • Windows 10 (domain-joined client)                         │
> │     • Metasploitable 2 (vulnerable target)                      │
> │     • pfSense (firewall/router between segments)                │
> │  ✅ Network: 2 segments (attack subnet + target subnet)          │
> │  ✅ Document full network diagram (Visio/draw.io)                │
> │                                                                 │
> │ RECON EXERCISE:                                                 │
> │  ✅ Enumerate all hosts on the network (nmap, netdiscover)       │
> │  ✅ Identify all open ports and services on each target           │
> │  ✅ Banner grab all services, Identify versions                  │
> │  ✅ Capture traffic with Wireshark — analyze 5 protocols          │
> │  ✅ Identify 3 security misconfigurations in your lab             │
> │  ✅ Write a professional network assessment report                │
> │                                                                 │
> │ DELIVERABLES:                                                   │
> │  📄 Network diagram                                              │
> │  📄 Host inventory spreadsheet (IP, OS, Services, Versions)      │
> │  📄 Wireshark captures with annotations                          │
> │  📄 10-page recon report with findings and recommendations       │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🔐 PHASE 2: SECURITY FUNDAMENTALS
### 📅 Duration: Months 3–6
### 🎯 Goal: Understand core security concepts, cryptography, and security operations
### 👤 Level: Junior Security Analyst
### 📜 Certifications: CompTIA Security+, CC (ISC²)

---

## Module 2.1: Core Security Concepts

### Section 2.1.1 — The CIA Triad & Beyond
```
├── Confidentiality:
│   ├── Definition: Only authorized access to information
│   ├── Controls: Encryption, Access controls, Data classification
│   └── Threats: Data breaches, Eavesdropping, Shoulder surfing
├── Integrity:
│   ├── Definition: Data is accurate and unaltered
│   ├── Controls: Hashing, Digital signatures, Version control, Checksums
│   └── Threats: Data tampering, Man-in-the-Middle, SQL injection
├── Availability:
│   ├── Definition: Systems are accessible when needed
│   ├── Controls: Redundancy, Backups, DDoS protection, Load balancing
│   └── Threats: DoS/DDoS, Ransomware, Hardware failure, Natural disasters
├── Additional Principles:
│   ├── Non-Repudiation: Cannot deny performing an action (digital signatures, audit logs)
│   ├── Authentication: Proving identity (something you know/have/are)
│   ├── Authorization: What you're allowed to do after authentication
│   └── Accountability: Actions tied to identities (audit trails)
├── Security Models:
│   ├── Bell-LaPadula: Confidentiality (No read up, No write down)
│   ├── Biba: Integrity (No write up, No read down)
│   ├── Clark-Wilson: Integrity via well-formed transactions
│   └── Brewer-Nash (Chinese Wall): Conflict of interest prevention
└── Security Principles:
    ├── Least Privilege: Minimum access needed to perform job
    ├── Defense in Depth: Multiple layers of security controls
    ├── Separation of Duties: No single person controls entire process
    ├── Fail Secure: Default to secure state on failure
    ├── Zero Trust: Never trust, Always verify
    ├── Need to Know: Access only to information required for task
    └── Security by Design: Build security in from the start, Not bolted on
```

### Section 2.1.2 — Threat Landscape
```
├── Threat Actors:
│   ├── Script Kiddies: Low skill, Use existing tools
│   ├── Hacktivists: Politically motivated (Anonymous, LulzSec)
│   ├── Cybercriminals: Financially motivated, Organized crime
│   ├── Nation-State (APT): Advanced Persistent Threats (APT28, APT29, Lazarus)
│   ├── Insiders: Employees, Contractors — Malicious or negligent
│   └── Competitors: Corporate espionage, IP theft
├── Attack Vectors:
│   ├── Phishing: Email, Spear phishing, Whaling, Smishing, Vishing
│   ├── Social Engineering: Pretexting, Baiting, Tailgating, Quid pro quo
│   ├── Malware: Virus, Worm, Trojan, Ransomware, Spyware, Rootkit, Bootkit
│   ├── Web Application Attacks: SQLi, XSS, CSRF, SSRF, RCE
│   ├── Network Attacks: MitM, DoS/DDoS, DNS poisoning, ARP spoofing
│   ├── Supply Chain: Compromised vendor, Malicious dependency, SolarWinds
│   ├── Physical: USB drop attacks, Evil maid, Lock picking
│   └── Zero-Day: Unknown vulnerability, No patch available
├── Attack Lifecycle (Cyber Kill Chain — Lockheed Martin):
│   ├── 1. Reconnaissance: Target information gathering
│   ├── 2. Weaponization: Creating exploit payload
│   ├── 3. Delivery: Sending the payload (email, USB, web)
│   ├── 4. Exploitation: Triggering the vulnerability
│   ├── 5. Installation: Establishing persistence
│   ├── 6. Command & Control (C2): Remote control channel
│   └── 7. Actions on Objectives: Data exfiltration, Destruction, Ransom
├── MITRE ATT&CK Framework:
│   ├── Tactics: WHY (Initial Access, Execution, Persistence, etc.)
│   ├── Techniques: HOW (T1566 Phishing, T1059 Command & Scripting)
│   ├── Sub-Techniques: Specific implementations
│   ├── Procedures: Real-world actor implementations
│   └── Usage: Threat intelligence, Detection engineering, Red team planning
└── MITRE D3FEND: Defensive countermeasures taxonomy
```

### Section 2.1.3 — Access Control
```
├── Access Control Models:
│   ├── DAC (Discretionary): Owner decides permissions (Linux file permissions)
│   ├── MAC (Mandatory): System enforces labels (SELinux, Military classifications)
│   ├── RBAC (Role-Based): Permissions assigned to roles, Users assigned to roles
│   ├── ABAC (Attribute-Based): Policies based on user/resource/environment attributes
│   └── Rule-Based: Access based on rules (firewall rules, time-of-day)
├── Authentication Factors:
│   ├── Something You Know: Password, PIN, Security questions
│   ├── Something You Have: Smart card, Token, Mobile phone (TOTP)
│   ├── Something You Are: Biometrics (fingerprint, face, iris, voice)
│   ├── Somewhere You Are: Geolocation, IP-based
│   └── Something You Do: Behavioral biometrics (typing patterns)
├── Multi-Factor Authentication (MFA):
│   ├── TOTP: Time-based One-Time Password (Google Authenticator)
│   ├── HOTP: HMAC-based One-Time Password (hardware tokens)
│   ├── FIDO2/WebAuthn: Hardware security keys (YubiKey), Passkeys
│   ├── Push Notifications: Approve/Deny on mobile (MFA fatigue attacks)
│   └── SMS (Weak): SIM swapping, SS7 attacks — avoid if possible
├── Single Sign-On (SSO):
│   ├── SAML: XML-based, Enterprise SSO
│   ├── OAuth 2.0 + OIDC: Token-based, Modern applications
│   ├── Kerberos: Windows AD authentication
│   └── LDAP: Directory-based authentication
├── Password Security:
│   ├── Hashing: bcrypt, scrypt, Argon2 (NOT MD5, NOT SHA1)
│   ├── Salting: Random salt per password prevents rainbow tables
│   ├── Password Policies: Length > Complexity, Minimum 12+ characters
│   ├── Password Managers: KeePass, Bitwarden, 1Password
│   └── Credential Stuffing: Reused passwords across sites — Check HaveIBeenPwned
└── Privileged Access Management (PAM):
    ├── Just-In-Time Access: Temporary elevated permissions
    ├── Privileged Session Recording: Monitor admin sessions
    ├── Credential Vaulting: CyberArk, HashiCorp Vault
    └── Break Glass Accounts: Emergency access with full audit
```

---

## Module 2.2: Cryptography

### Section 2.2.1 — Cryptography Fundamentals
```
├── Terminology:
│   ├── Plaintext → Encryption → Ciphertext → Decryption → Plaintext
│   ├── Key: Secret value used in encryption/decryption
│   ├── Algorithm (Cipher): Mathematical function for encryption
│   ├── Key Space: Total number of possible keys
│   └── Kerckhoffs' Principle: Security depends on key, NOT algorithm secrecy
├── Historical Ciphers (Understanding concepts):
│   ├── Caesar Cipher: Substitution, Shift by N
│   ├── Vigenère Cipher: Polyalphabetic substitution
│   ├── Enigma: Rotor machine, WWII
│   └── One-Time Pad: Perfect secrecy (impractical)
├── Symmetric Encryption:
│   ├── Block Ciphers:
│   │   ├── AES (Advanced Encryption Standard): 128/192/256 bit keys, Gold standard
│   │   ├── DES: 56-bit key (BROKEN — never use)
│   │   ├── 3DES: Triple DES (deprecated, slow)
│   │   └── Blowfish / Twofish: Alternatives (bcrypt uses Blowfish)
│   ├── Block Cipher Modes:
│   │   ├── ECB: Electronic Codebook (INSECURE — same plaintext = same ciphertext)
│   │   ├── CBC: Cipher Block Chaining (IV required, Padding oracle attacks)
│   │   ├── CTR: Counter mode (stream cipher from block cipher)
│   │   ├── GCM: Galois/Counter Mode (authenticated encryption — RECOMMENDED)
│   │   └── CCM: Counter with CBC-MAC (IoT, wireless)
│   ├── Stream Ciphers:
│   │   ├── RC4: BROKEN — Do NOT use
│   │   ├── ChaCha20: Modern, Fast, Used in TLS 1.3 and WireGuard
│   │   └── ChaCha20-Poly1305: AEAD (authenticated encryption)
│   └── Key Exchange Problem: How to share symmetric key securely?
├── Asymmetric (Public Key) Encryption:
│   ├── RSA: Based on factoring large primes, 2048+ bit keys minimum
│   │   └── Usage: Key exchange, Digital signatures, Certificate signing
│   ├── Diffie-Hellman (DH): Key agreement protocol
│   │   ├── Classic DH: Vulnerable to MitM without authentication
│   │   └── ECDH (Elliptic Curve DH): Smaller keys, Same security level
│   ├── Elliptic Curve Cryptography (ECC): Smaller, Faster than RSA
│   │   └── Curves: P-256, P-384, Curve25519 (X25519), Ed25519
│   ├── Digital Signatures:
│   │   ├── RSA Signatures: Sign with private key, Verify with public key
│   │   ├── ECDSA: Elliptic curve signatures
│   │   ├── EdDSA (Ed25519): Modern, Fast, Deterministic
│   │   └── Usage: Code signing, Document signing, Certificate signing
│   └── Hybrid Encryption: Asymmetric to exchange symmetric key, Symmetric for data
└── Important Concepts:
    ├── Authenticated Encryption (AEAD): AES-GCM, ChaCha20-Poly1305
    ├── Key Derivation Functions (KDF): PBKDF2, scrypt, Argon2, HKDF
    ├── Perfect Forward Secrecy (PFS): Compromise of long-term key doesn't compromise past sessions
    ├── Cryptographic Agility: Design to swap algorithms when broken
    └── Random Number Generation: CSPRNG, /dev/urandom, Hardware RNG
```

### Section 2.2.2 — Hashing & Integrity
```
├── Hash Functions:
│   ├── Properties: Deterministic, Fixed output, One-way, Collision resistant
│   ├── MD5: 128-bit (BROKEN — collisions found) — NEVER for security
│   ├── SHA-1: 160-bit (BROKEN — SHAttered attack) — Deprecated
│   ├── SHA-2: SHA-256, SHA-384, SHA-512 — Currently standard
│   ├── SHA-3: Keccak-based, Backup for SHA-2
│   └── BLAKE2/BLAKE3: Modern, Faster than SHA-2, Gaining adoption
├── HMAC (Hash-based Message Authentication Code):
│   ├── Combines hash function with secret key
│   ├── Provides integrity AND authentication
│   └── Usage: API authentication, JWT signatures, Message verification
├── Password Hashing (DIFFERENT from regular hashing):
│   ├── bcrypt: Blowfish-based, Cost factor, Salt built-in — RECOMMENDED
│   ├── scrypt: Memory-hard, Resists GPU/ASIC attacks
│   ├── Argon2: Winner of Password Hashing Competition — BEST
│   │   └── Variants: Argon2d (GPU-resistant), Argon2i (side-channel resistant), Argon2id (hybrid)
│   └── NEVER use: MD5, SHA-1, SHA-256 for passwords (too fast = brutable)
├── Digital Signatures:
│   ├── Signing: Hash(message) → Encrypt hash with private key
│   ├── Verification: Decrypt with public key → Compare with hash of message
│   ├── Non-repudiation: Signer cannot deny signing
│   └── Use cases: Software updates, Emails (S/MIME, PGP), Legal documents
└── Integrity Verification:
    ├── File Integrity: SHA-256 checksums for downloads
    ├── Code Signing: Trusted publisher verification
    ├── Merkle Trees: Git commits, Blockchain, Certificate Transparency
    └── File Integrity Monitoring (FIM): AIDE, OSSEC, Tripwire
```

### Section 2.2.3 — PKI & Certificates
```
├── Public Key Infrastructure (PKI):
│   ├── Certificate Authority (CA): Issues digital certificates
│   │   ├── Root CA: Self-signed, Trusted by OS/browser
│   │   ├── Intermediate CA: Signed by Root CA, Issues end-entity certs
│   │   └── Trust Chain: End-entity → Intermediate → Root
│   ├── Registration Authority (RA): Verifies identity before cert issuance
│   ├── Certificate Revocation:
│   │   ├── CRL (Certificate Revocation List): Periodic list of revoked certs
│   │   ├── OCSP (Online Certificate Status Protocol): Real-time status check
│   │   └── OCSP Stapling: Server provides OCSP response (faster)
│   └── Certificate Transparency (CT): Public log of all issued certificates
├── X.509 Certificates:
│   ├── Fields: Subject, Issuer, Serial number, Validity, Public key, Extensions
│   ├── Types: DV (Domain Validation), OV (Organization), EV (Extended Validation)
│   ├── SAN (Subject Alternative Name): Multiple domains per certificate
│   ├── Wildcard Certificates: *.example.com (covers subdomains)
│   ├── Self-Signed Certificates: Not trusted by default (development use)
│   └── Formats: PEM, DER, PFX/PKCS#12, JKS
├── TLS/SSL (Transport Layer Security):
│   ├── TLS 1.2: Current widely-deployed standard
│   │   └── Handshake: ClientHello → ServerHello → Certificate → Key Exchange → Finished
│   ├── TLS 1.3: Modern, Faster (1-RTT / 0-RTT), Removed weak algorithms
│   │   └── Only: AES-GCM, ChaCha20-Poly1305, ECDHE, EdDSA
│   ├── Cipher Suites: TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 (example)
│   ├── Perfect Forward Secrecy: Ephemeral DH/ECDH keys per session
│   ├── Certificate Pinning: Pin expected certificate/key (HPKP — deprecated but concept matters)
│   ├── SSL/TLS Attacks: POODLE, BEAST, CRIME, BREACH, Heartbleed, DROWN, ROBOT
│   └── Testing: SSL Labs (ssllabs.com), testssl.sh, sslscan
├── PGP/GPG:
│   ├── Email Encryption: Encrypt with recipient's public key
│   ├── Email Signing: Sign with sender's private key
│   ├── Web of Trust: Decentralized trust model (vs CA hierarchy)
│   └── Key Servers: Public key distribution
└── Let's Encrypt: Free automated certificates, ACME protocol
```

---

## Module 2.3: Security Operations Fundamentals

### Section 2.3.1 — Security Policies & Frameworks
```
├── Security Policies:
│   ├── Acceptable Use Policy (AUP): What users can/can't do
│   ├── Information Security Policy: Overarching security governance
│   ├── Password Policy: Length, Complexity, Rotation, MFA requirements
│   ├── Incident Response Policy: How to handle security incidents
│   ├── Data Classification Policy: Public, Internal, Confidential, Restricted
│   ├── Remote Access Policy: VPN, BYOD, Home network requirements
│   ├── Change Management Policy: How changes are reviewed and approved
│   └── Disaster Recovery / BCP: Business Continuity Planning
├── Security Frameworks:
│   ├── NIST Cybersecurity Framework (CSF):
│   │   └── Identify → Protect → Detect → Respond → Recover
│   ├── NIST SP 800-53: Security and Privacy Controls (detailed controls catalog)
│   ├── ISO 27001/27002: Information Security Management System (ISMS)
│   ├── CIS Controls: Prioritized list of security actions (18 controls)
│   ├── COBIT: IT governance framework
│   └── MITRE ATT&CK: Adversary tactics and techniques (covered earlier)
└── Regulatory Compliance (overview):
    ├── GDPR: EU data protection
    ├── HIPAA: US healthcare data
    ├── PCI DSS: Payment card data
    ├── SOX: Financial reporting integrity
    ├── FERPA: Educational records
    └── CCPA/CPRA: California privacy
```

### Section 2.3.2 — Security Hardening
```
├── OS Hardening:
│   ├── Disable unnecessary services and ports
│   ├── Remove default accounts and change default passwords
│   ├── Apply CIS Benchmarks (Center for Internet Security)
│   ├── Enable audit logging
│   ├── Configure host-based firewall
│   ├── Keep patches current (patch management)
│   └── Disable USB auto-run, Restrict removable media
├── Network Hardening:
│   ├── Firewall rules: Default deny, Whitelist approach
│   ├── Network segmentation and VLANs
│   ├── Disable unused switch ports
│   ├── Enable port security (MAC limiting)
│   ├── Disable unnecessary protocols (Telnet, FTP, SNMPv1/v2)
│   ├── Implement 802.1X (Network Access Control)
│   └── DNS sinkholing for malicious domains
├── Application Hardening:
│   ├── Remove default pages, Sample files, Debug endpoints
│   ├── Disable directory listing
│   ├── Configure security headers (HSTS, CSP, X-Frame-Options)
│   ├── Input validation on ALL user inputs
│   ├── Parameterized queries (prevent SQLi)
│   └── Secure cookie flags (HttpOnly, Secure, SameSite)
├── Hardening Guides:
│   ├── CIS Benchmarks: OS, Application, Cloud, Network device guides
│   ├── DISA STIGs: DoD Security Technical Implementation Guides
│   └── Vendor Guides: Microsoft, Red Hat, AWS security best practices
└── Vulnerability Management:
    ├── Vulnerability Scanning: Nessus, OpenVAS, Qualys, Rapid7 InsightVM
    ├── CVSS: Common Vulnerability Scoring System (Base, Temporal, Environmental)
    ├── CVE: Common Vulnerabilities and Exposures — Unique vulnerability IDs
    ├── NVD: National Vulnerability Database
    ├── Patch Management: Test → Stage → Deploy → Verify cycle
    └── Remediation Prioritization: CVSS + Exploitability + Asset criticality
```

---

## Module 2.4: Networking Security Tools

### Section 2.4.1 — Essential Security Tools
```
├── Reconnaissance:
│   ├── nmap: Port scanning, Service detection, OS fingerprinting, NSE scripts
│   ├── Masscan: Ultra-fast port scanner (internet-scale)
│   ├── Shodan: Internet-wide scanner (find exposed devices)
│   ├── Censys: Internet-wide certificate and host data
│   ├── theHarvester: Email, Domain, IP enumeration
│   └── OSINT Framework: Organized collection of OSINT tools
├── Network Analysis:
│   ├── Wireshark: GUI packet analyzer (covered in 1.2.3)
│   ├── tcpdump: CLI packet analyzer
│   ├── Zeek (Bro): Network security monitoring framework
│   ├── NetworkMiner: Network forensic analyzer
│   └── hping3: Packet crafting and analysis
├── Vulnerability Assessment:
│   ├── Nessus: Industry standard vulnerability scanner
│   ├── OpenVAS: Open-source vulnerability scanner
│   ├── Nikto: Web server vulnerability scanner
│   ├── WPScan: WordPress vulnerability scanner
│   └── SQLmap: Automated SQL injection detection
├── Password Auditing:
│   ├── John the Ripper: Offline password cracker
│   ├── Hashcat: GPU-accelerated password cracker
│   ├── Hydra: Online brute-force tool (SSH, FTP, HTTP, etc.)
│   ├── CeWL: Custom wordlist generator from websites
│   └── SecLists: Collection of security-related lists (usernames, passwords, URLs)
└── Network Utilities:
    ├── Netcat (nc): Network Swiss Army knife (connection, listening, file transfer)
    ├── socat: Advanced netcat (SSL, proxy, port forwarding)
    ├── curl / wget: HTTP requests, Download files
    ├── proxychains: Route tools through proxy (Tor, SOCKS)
    └── Responder: LLMNR/NBT-NS/MDNS poisoner
```

---

> ### 🛠️ PHASE 2 PROJECT: **Security Assessment of a Small Business Network**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │         SECURITY ASSESSMENT — SMALL BUSINESS NETWORK            │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ SCENARIO: Simulate a small business with 3 servers,             │
> │ a firewall, and 5 workstations in your virtual lab.             │
> │                                                                 │
> │ TASKS:                                                          │
> │                                                                 │
> │ 📋 POLICY:                                                      │
> │  ✅ Write an Acceptable Use Policy (2 pages)                     │
> │  ✅ Write a Password Policy aligned with NIST guidelines         │
> │  ✅ Create a data classification scheme (4 levels)               │
> │                                                                 │
> │ 🔍 ASSESSMENT:                                                  │
> │  ✅ Run Nessus/OpenVAS vulnerability scan on all targets         │
> │  ✅ Run nmap scan: Full port, Service detection, OS fingerprint  │
> │  ✅ Identify 10+ vulnerabilities with CVSS scores                │
> │  ✅ Test SSL/TLS configuration with testssl.sh                   │
> │  ✅ Audit password strength with John the Ripper against /etc/shadow│
> │  ✅ Verify CIS Benchmark compliance on 1 Linux + 1 Windows host  │
> │                                                                 │
> │ 🔐 HARDENING:                                                   │
> │  ✅ Harden 1 Linux server following CIS Benchmark                │
> │  ✅ Configure iptables/nftables firewall rules                   │
> │  ✅ Set up SSH key-based auth, Disable password auth             │
> │  ✅ Configure TLS on web server with proper cipher suites        │
> │  ✅ Implement fail2ban for brute-force protection                │
> │                                                                 │
> │ 📊 REPORTING:                                                   │
> │  ✅ Professional vulnerability assessment report                 │
> │  ✅ Executive summary (non-technical, 1 page)                    │
> │  ✅ Technical findings with CVSS, Evidence, Remediation          │
> │  ✅ Risk matrix: Likelihood × Impact                             │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🗡️ PHASE 3: OFFENSIVE SECURITY (RED TEAM)
### 📅 Duration: Months 6–10
### 🎯 Goal: Think like an attacker — Reconnaissance, Exploitation, Post-Exploitation
### 👤 Level: Penetration Tester
### 📜 Certifications: eJPT (INE), CEH, CompTIA PenTest+, PNPT

---

## Module 3.1: Reconnaissance & Information Gathering

### Section 3.1.1 — Passive Reconnaissance (OSINT)
```
├── Domain Intelligence:
│   ├── WHOIS: Domain registration, Registrant info, Name servers
│   ├── DNS Enumeration: dig, dnsenum, dnsrecon, fierce
│   │   └── Zone Transfers: AXFR (misconfiguration goldmine)
│   ├── Subdomain Enumeration: Sublist3r, Amass, Subfinder, crt.sh (Certificate Transparency)
│   ├── Reverse DNS: PTR records, Reverse IP lookup
│   └── ASN Lookup: Identify IP ranges owned by organization
├── Email Intelligence:
│   ├── Email Harvesting: theHarvester, Hunter.io, Phonebook.cz
│   ├── Email Verification: Verify existence without sending (SMTP VRFY)
│   ├── Breach Data: HaveIBeenPwned, DeHashed (credential leaks)
│   └── Metadata: FOCA, ExifTool — Extract metadata from public documents
├── Web Intelligence:
│   ├── Google Dorking: site:, filetype:, inurl:, intitle:, intext:
│   │   └── GHDB: Google Hacking Database (exploit-db.com/google-hacking-database)
│   ├── Wayback Machine: Historical website snapshots (archive.org)
│   ├── Cached Pages: Google cache, Bing cache
│   ├── Robots.txt & Sitemap.xml: Discover hidden paths
│   └── Technology Stack: Wappalyzer, BuiltWith, WhatWeb
├── Social Media Intelligence:
│   ├── LinkedIn: Employee enumeration, Job postings reveal tech stack
│   ├── GitHub/GitLab: Leaked credentials, API keys, Internal docs
│   │   └── Tools: truffleHog, GitLeaks, git-secrets
│   ├── Twitter/X: Employee posts, Company announcements
│   └── Social Engineering Reconnaissance: Org chart, Key personnel
├── Infrastructure Intelligence:
│   ├── Shodan: Internet-connected devices, Industrial control systems
│   ├── Censys: TLS certificates, Open ports, Services
│   ├── ZoomEye: Chinese equivalent of Shodan
│   ├── BGP Toolkit: AS numbers, IP ranges, Peering info
│   └── Public Cloud: S3 bucket enumeration, Azure blob, GCS buckets
└── OSINT Frameworks:
    ├── Maltego: Visual link analysis, Transforms
    ├── SpiderFoot: Automated OSINT collection
    ├── Recon-ng: Web reconnaissance framework
    └── OSINT Framework (osintframework.com): Categorized tool collection
```

### Section 3.1.2 — Active Reconnaissance
```
├── Network Scanning (nmap mastery):
│   ├── Host Discovery: -sn (ping sweep), -Pn (no ping), -PS/-PA/-PU
│   ├── Port Scanning Techniques:
│   │   ├── TCP SYN Scan (-sS): Stealth, Most common, Half-open
│   │   ├── TCP Connect (-sT): Full connection, Logged
│   │   ├── UDP Scan (-sU): Slow, Essential for SNMP/DNS/DHCP
│   │   ├── FIN/XMAS/NULL (-sF/-sX/-sN): Firewall evasion
│   │   └── ACK Scan (-sA): Determine firewall ruleset
│   ├── Service Detection: -sV (version detection), --version-intensity
│   ├── OS Detection: -O (OS fingerprinting)
│   ├── NSE Scripts: --script=vuln, --script=smb-enum-shares, --script=http-enum
│   ├── Output: -oN (normal), -oX (XML), -oG (greppable), -oA (all)
│   └── Timing: -T0 (paranoid) to -T5 (insane) — evasion vs speed
├── Web Enumeration:
│   ├── Directory Brute-forcing: Gobuster, Dirsearch, Feroxbuster, ffuf
│   ├── Virtual Host Discovery: ffuf -H "Host: FUZZ.target.com"
│   ├── Parameter Discovery: Arjun, ParamSpider
│   ├── API Enumeration: Swagger/OpenAPI discovery, Endpoint fuzzing
│   ├── CMS Scanning: WPScan (WordPress), Joomscan (Joomla), Droopescan
│   └── Spider/Crawl: Burp Spider, ZAP Spider, scrapy
├── SMB Enumeration (Windows):
│   ├── enum4linux: Shares, Users, Groups, Policies
│   ├── smbclient: Access shares, Upload/download files
│   ├── CrackMapExec (CME): Swiss Army knife for Windows/AD
│   └── rpcclient: RPC enumeration, User info
├── SNMP Enumeration:
│   ├── snmpwalk: Walk the MIB tree
│   ├── snmp-check: Comprehensive SNMP enumeration
│   └── Community strings: public, private (default — often unchanged)
└── LDAP Enumeration:
    ├── ldapsearch: Query Active Directory
    ├── BloodHound: AD attack path visualization
    └── AD Recon: PowerView, ADRecon scripts
```

---

## Module 3.2: Web Application Attacks

### Section 3.2.1 — OWASP Top 10 (Practical Exploitation)
```
├── A01 — Broken Access Control:
│   ├── IDOR (Insecure Direct Object Reference): Change user_id in URL/API
│   ├── Privilege Escalation: Access admin functions as normal user
│   ├── Forced Browsing: Access /admin, /backup, /config directly
│   ├── Method Override: Change GET to PUT/DELETE
│   └── JWT Manipulation: None algorithm, Weak signing key
├── A02 — Cryptographic Failures:
│   ├── Cleartext Transmission: HTTP instead of HTTPS
│   ├── Weak Algorithms: MD5, SHA1, DES, RC4
│   ├── Hardcoded Secrets: API keys in source code
│   ├── Insecure Random: Predictable tokens, Session IDs
│   └── Missing Encryption: PII stored in plaintext
├── A03 — Injection:
│   ├── SQL Injection:
│   │   ├── In-Band: UNION-based (extract data), Error-based (error messages)
│   │   ├── Blind: Boolean-based (true/false), Time-based (SLEEP)
│   │   ├── Out-of-Band: DNS exfiltration, HTTP callbacks
│   │   ├── Second-Order: Payload stored, Triggered later
│   │   └── Tools: SQLmap, Manual with Burp Suite
│   ├── NoSQL Injection: MongoDB operators ($gt, $ne), JSON injection
│   ├── Command Injection (OS): ; ls, | cat /etc/passwd, $(whoami)
│   ├── LDAP Injection: Manipulate LDAP queries
│   ├── XML Injection / XXE: XML External Entity — Read files, SSRF
│   ├── Template Injection (SSTI): Jinja2, Twig, Freemarker — RCE possible
│   └── Header Injection: Host header, CRLF injection
├── A04 — Insecure Design:
│   ├── Business Logic Flaws: Bypass payment, Price manipulation
│   ├── Race Conditions: TOCTOU, Double spending
│   ├── Missing Rate Limiting: Brute-force, Account lockout bypass
│   └── Insufficient Anti-Automation: CAPTCHA bypass
├── A05 — Security Misconfiguration:
│   ├── Default Credentials: admin/admin, root/root, sa/sa
│   ├── Verbose Error Messages: Stack traces, SQL errors exposed
│   ├── Unnecessary Features: Debug endpoints, TRACE method, phpinfo()
│   ├── Directory Listing: Apache/Nginx directory indexes
│   ├── Missing Security Headers: HSTS, CSP, X-Frame-Options
│   └── Cloud Misconfiguration: Public S3 buckets, Open security groups
├── A06 — Vulnerable Components:
│   ├── Known CVEs: Check versions against NVD, Exploit-DB
│   ├── Outdated Libraries: npm, Maven, pip dependencies
│   ├── Unpatched Software: Apache, Nginx, WordPress, Log4Shell
│   └── Tools: Retire.js, npm audit, Snyk, OWASP Dependency-Check
├── A07 — Authentication Failures:
│   ├── Credential Stuffing: Automated login with breach credentials
│   ├── Brute Force: Password spraying, Dictionary attacks
│   ├── Session Fixation: Force victim's session ID
│   ├── Session Hijacking: Steal session cookie (XSS, network sniffing)
│   ├── Weak Password Recovery: Security questions, Predictable tokens
│   └── MFA Bypass: 2FA race conditions, Backup code leaks, SIM swapping
├── A08 — Software & Data Integrity Failures:
│   ├── Insecure Deserialization: Java, PHP, Python, .NET object injection
│   │   └── Tools: ysoserial, phpggc
│   ├── CI/CD Pipeline Attacks: Poisoned builds, Malicious dependencies
│   └── Unsigned Updates: Tampered software updates
├── A09 — Security Logging Failures:
│   ├── No Logging: Attacks go undetected
│   ├── Insufficient Logging: Missing login attempts, Access denials
│   ├── Log Injection: Forging log entries, CRLF in logs
│   └── No Alerting: Logs exist but nobody monitors them
└── A10 — Server-Side Request Forgery (SSRF):
    ├── Internal Network Scanning: Access internal services via web app
    ├── Cloud Metadata: http://169.254.169.254 (AWS IMDSv1)
    ├── Port Scanning: Via SSRF, Identify internal services
    ├── File Read: file:// protocol, Read /etc/passwd
    └── Mitigation Bypass: URL encoding, IP alternatives, DNS rebinding
```

### Section 3.2.2 — Web Application Testing Methodology
```
├── Tools:
│   ├── Burp Suite Pro: Intercepting proxy, Scanner, Repeater, Intruder, Sequencer
│   ├── OWASP ZAP: Open-source alternative to Burp
│   ├── Browser DevTools: Network tab, Console, Storage, Application
│   ├── Postman: API testing, Collection runner
│   └── curl: Command-line HTTP requests
├── Methodology:
│   ├── 1. Map the Application: Spider, Discover endpoints, Identify technology
│   ├── 2. Analyze Authentication: Login mechanisms, Session management
│   ├── 3. Test Access Controls: IDOR, Privilege escalation, Role bypass
│   ├── 4. Test Input Handling: SQLi, XSS, Command injection, SSTI
│   ├── 5. Test Business Logic: Workflow bypass, Price manipulation
│   ├── 6. Test File Uploads: Bypass extensions, Web shells, Path traversal
│   ├── 7. Test API: Authentication, Rate limiting, Mass assignment, BOLA
│   └── 8. Test for Information Disclosure: Error messages, Debug endpoints, Comments
├── XSS (Cross-Site Scripting) Deep Dive:
│   ├── Reflected XSS: Payload in URL, Reflected in response
│   ├── Stored XSS: Payload stored (DB), Displayed to other users
│   ├── DOM-based XSS: Payload processed by client-side JavaScript
│   ├── Payloads: <script>alert(1)</script>, <img onerror=>, <svg onload=>
│   ├── Filter Bypass: Encoding, Case variation, Event handlers
│   ├── Impact: Cookie theft, Session hijacking, Keylogging, Defacement
│   └── Tools: XSSStrike, Dalfox, Burp Intruder with XSS payloads
└── Practice Labs:
    ├── DVWA: Damn Vulnerable Web Application
    ├── bWAPP: Buggy Web Application
    ├── WebGoat: OWASP learning application
    ├── Juice Shop: OWASP modern vulnerable application
    ├── PortSwigger Web Security Academy: FREE, Excellent labs
    └── PentesterLab: Progressive web security exercises
```

---

## Module 3.3: Network & System Exploitation

### Section 3.3.1 — Network Attacks
```
├── Man-in-the-Middle (MitM):
│   ├── ARP Spoofing: arpspoof, Bettercap, Ettercap
│   ├── DNS Spoofing: Redirect domains to attacker-controlled server
│   ├── SSL Stripping: Downgrade HTTPS to HTTP (sslstrip)
│   ├── LLMNR/NBT-NS Poisoning: Responder (Windows network attacks)
│   └── Rogue DHCP/AP: Provide malicious network config
├── Password Attacks:
│   ├── Online Brute Force: Hydra, Medusa, CrackMapExec, Burp Intruder
│   ├── Offline Cracking: Hashcat, John the Ripper
│   ├── Password Spraying: One password, Many accounts
│   ├── Credential Stuffing: Leaked credentials, Automated login
│   ├── Rainbow Tables: Pre-computed hash lookups (defeated by salting)
│   └── Rules & Masks: Hashcat rules, Intelligent wordlist generation
├── DoS/DDoS:
│   ├── Volumetric: UDP flood, ICMP flood, Amplification (DNS, NTP, Memcached)
│   ├── Protocol: SYN flood, Ping of Death, Smurf attack
│   ├── Application Layer: HTTP flood, Slowloris, R-U-Dead-Yet (RUDY)
│   └── Defense: Rate limiting, CDN/DDoS protection (Cloudflare), SYN cookies
├── Exploitation Frameworks:
│   ├── Metasploit Framework:
│   │   ├── Modules: Exploits, Payloads, Auxiliaries, Post-exploitation
│   │   ├── Meterpreter: Advanced post-exploitation payload
│   │   ├── msfvenom: Payload generation (reverse shells, bind shells)
│   │   └── Database: Track hosts, services, vulnerabilities, credentials
│   ├── Cobalt Strike: Commercial C2 framework (Red team standard)
│   ├── Sliver: Open-source C2 framework (alternative to Cobalt Strike)
│   └── Empire / Starkiller: PowerShell/Python post-exploitation
└── Wireless Attacks:
    ├── WPA/WPA2 Cracking: Capture handshake → Offline crack (aircrack-ng)
    ├── Evil Twin: Fake AP, Capture credentials
    ├── Karma Attack: Respond to any SSID probe
    ├── Deauthentication: Force client disconnect → Capture handshake
    ├── WPS Attack: Reaver, Bully (brute-force WPS PIN)
    └── Tools: aircrack-ng suite, Wifite, Fern WiFi Cracker, Bettercap
```

### Section 3.3.2 — System Exploitation
```
├── Vulnerability Research:
│   ├── Exploit-DB: Searchable archive of public exploits
│   ├── CVE Details: Vulnerability database with exploit references
│   ├── Packet Storm: Security tools and exploits
│   ├── SearchSploit: Offline Exploit-DB search (Kali)
│   └── GitHub: PoC exploits, Security research repositories
├── Linux Exploitation:
│   ├── Privilege Escalation:
│   │   ├── SUID/SGID Binaries: find / -perm -4000 → GTFOBins
│   │   ├── Sudo Misconfigurations: sudo -l → exploitable rules
│   │   ├── Cron Jobs: Writable scripts run by root
│   │   ├── Kernel Exploits: DirtyCow, DirtyPipe, PwnKit
│   │   ├── Writable /etc/passwd or /etc/shadow
│   │   ├── PATH Hijacking: Relative paths in scripts
│   │   ├── Capabilities: Excessive Linux capabilities
│   │   ├── NFS no_root_squash: Mount and create SUID binaries
│   │   └── Docker Escape: Privileged containers, Mounted socket
│   ├── Tools: LinPEAS, Linux Exploit Suggester, pspy (process spy)
│   └── Technique: Enumerate → Find weakness → Exploit → Verify root
├── Windows Exploitation:
│   ├── Privilege Escalation:
│   │   ├── Unquoted Service Paths: Inject DLL in path
│   │   ├── Weak Service Permissions: Modify service binary path
│   │   ├── Always Install Elevated: MSI installer privilege
│   │   ├── Token Impersonation: SeImpersonatePrivilege (Potato attacks)
│   │   ├── Scheduled Tasks: Writable task binaries
│   │   ├── Registry Autorun: Add persistence + privesc
│   │   ├── DLL Hijacking: Missing DLLs in search order
│   │   ├── UAC Bypass: Various techniques (fodhelper, eventvwr)
│   │   └── Kernel Exploits: PrintNightmare, EternalBlue
│   ├── Tools: WinPEAS, PowerUp, SharpUp, Seatbelt, Windows Exploit Suggester
│   └── Technique: whoami /priv → Enumerate → Exploit → SYSTEM
└── Post-Exploitation:
    ├── Maintaining Access:
    │   ├── Reverse Shells: Netcat, PowerShell, Python, Bash
    │   ├── Web Shells: PHP, ASP, JSP web shells (upload after exploit)
    │   ├── Persistence: Registry keys, Scheduled tasks, Services, Startup folder
    │   └── Backdoors: SSH keys, New admin accounts
    ├── Lateral Movement:
    │   ├── Pass-the-Hash (PtH): Use NTLM hash instead of password
    │   ├── Pass-the-Ticket (PtT): Use Kerberos tickets
    │   ├── PSExec / WMI / WinRM: Remote execution on other hosts
    │   ├── RDP: Remote Desktop with stolen credentials
    │   ├── SMB: Access shares, Deploy payloads
    │   └── SSH: Key-based access to other Linux hosts
    ├── Credential Harvesting:
    │   ├── Mimikatz: Extract passwords, Hashes, Kerberos tickets from LSASS
    │   ├── SAM Dump: Extract local password hashes
    │   ├── LSASS Dump: Memory dump of credential process
    │   ├── Kerberoasting: Request TGS tickets, Crack offline
    │   ├── AS-REP Roasting: Attack accounts without pre-auth
    │   ├── DCSync: Simulate DC replication, Dump all domain hashes
    │   └── Keylogging: Capture typed passwords
    ├── Data Exfiltration:
    │   ├── DNS Exfiltration: Encode data in DNS queries
    │   ├── HTTP/HTTPS: Upload to attacker server
    │   ├── ICMP Tunneling: Data in ping packets
    │   └── Steganography: Hide data in images/files
    └── Covering Tracks:
        ├── Clear Event Logs: wevtutil, Clear-EventLog
        ├── Modify Timestamps: Timestomping
        ├── Delete Artifacts: Remove tools, Clean temp files
        └── Anti-Forensics: Disable logging, Clear bash history
```

---

## Module 3.4: Active Directory Attacks

### Section 3.4.1 — AD Attack Methodology
```
├── AD Enumeration:
│   ├── BloodHound: Map AD relationships, Find attack paths
│   │   └── SharpHound / BloodHound.py: Data collection
│   ├── PowerView: PowerShell AD enumeration
│   │   └── Get-DomainUser, Get-DomainGroup, Get-DomainComputer, Find-LocalAdminAccess
│   ├── ADRecon: Automated AD reconnaissance
│   ├── ldapsearch: LDAP queries against DC
│   └── net commands: net user /domain, net group /domain
├── AD Attacks:
│   ├── Kerberoasting: Request TGS for SPNs → Crack offline (Rubeus, GetUserSPNs.py)
│   ├── AS-REP Roasting: Attack accounts with "Do not require pre-auth" (Rubeus)
│   ├── Pass-the-Hash: CrackMapExec, PsExec, WMI with NTLM hash
│   ├── Pass-the-Ticket: Use stolen Kerberos TGT/TGS (Rubeus)
│   ├── Overpass-the-Hash: Get Kerberos ticket from NTLM hash
│   ├── Golden Ticket: Forge TGT with KRBTGT hash (domain persistence)
│   ├── Silver Ticket: Forge TGS for specific service
│   ├── DCSync: Replicate domain controller, Dump all hashes (Mimikatz, secretsdump.py)
│   ├── DCShadow: Register rogue DC, Push changes
│   ├── ADCS Attacks: Misconfigured certificate templates → Domain admin
│   │   └── Tools: Certify, Certipy
│   ├── Constrained/Unconstrained Delegation: Abuse Kerberos delegation
│   ├── Group Policy Abuse: Modify GPO for code execution
│   └── Print Spooler / PetitPotam: Coerce authentication → NTLMRelay
├── Tools:
│   ├── Impacket: Python toolkit (secretsdump, psexec, ntlmrelayx, GetNPUsers)
│   ├── Mimikatz: Credential extraction, Ticket manipulation
│   ├── Rubeus: Kerberos abuse toolkit (C#)
│   ├── CrackMapExec: Swiss Army knife for Windows networks
│   ├── Evil-WinRM: WinRM shell
│   └── Responder: LLMNR/NBT-NS/MDNS poisoning → NTLMv2 capture
└── Attack Path:
    Initial Access → Enumerate AD → Find privileged paths →
    Move laterally → Escalate to Domain Admin → Persistence
```

---

> ### 🛠️ PHASE 3 PROJECT: **Full Penetration Test (Internal Network)**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │              FULL PENETRATION TEST REPORT                       │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ TARGET: Your virtual lab (AD environment + Web apps + Linux)    │
> │                                                                 │
> │ PHASES:                                                         │
> │  ✅ 1. Scoping & Rules of Engagement document                   │
> │  ✅ 2. OSINT & Passive Recon (treat lab as real target)         │
> │  ✅ 3. Active Scanning: nmap full + service detection            │
> │  ✅ 4. Vulnerability Assessment: Nessus + Manual testing         │
> │  ✅ 5. Web App Testing (DVWA/Juice Shop):                       │
> │     • SQLi (manual + SQLmap)                                    │
> │     • XSS (reflected + stored)                                  │
> │     • SSRF, IDOR, File upload bypass                            │
> │  ✅ 6. Network Exploitation:                                    │
> │     • Exploit 2+ services with Metasploit                       │
> │     • Gain initial foothold on Linux target                     │
> │     • Gain initial foothold on Windows target                   │
> │  ✅ 7. Privilege Escalation:                                    │
> │     • Root on Linux (SUID/sudo/kernel exploit)                  │
> │     • SYSTEM on Windows (token impersonation/service exploit)   │
> │  ✅ 8. Active Directory Attack Chain:                            │
> │     • BloodHound enumeration                                    │
> │     • Kerberoasting → Crack service account                     │
> │     • Lateral movement (PtH/PsExec)                             │
> │     • DCSync → Domain Admin                                     │
> │  ✅ 9. Post-exploitation: Credential dump, Data exfiltration    │
> │                                                                 │
> │ DELIVERABLES:                                                   │
> │  📄 Professional pentest report (30+ pages):                     │
> │     • Executive Summary                                         │
> │     • Methodology                                               │
> │     • Findings (Critical/High/Medium/Low/Info)                  │
> │     • Evidence (screenshots, commands, outputs)                 │
> │     • Remediation recommendations                               │
> │     • MITRE ATT&CK mapping for each finding                     │
> │     • Risk ratings with CVSS scores                             │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🔵 PHASE 4: DEFENSIVE SECURITY (BLUE TEAM)
### 📅 Duration: Months 10–14
### 🎯 Goal: Detect, Analyze, Respond to threats — Be the defender
### 👤 Level: SOC Analyst / DFIR Specialist
### 📜 Certifications: CompTIA CySA+, BTL1 (Blue Team Level 1), SC-200

---

## Module 4.1: Security Operations Center (SOC)

### Section 4.1.1 — SOC Fundamentals
```
├── SOC Tiers:
│   ├── Tier 1 (Alert Triage): Monitor, Classify, Escalate
│   ├── Tier 2 (Incident Responder): Investigate, Correlate, Contain
│   ├── Tier 3 (Threat Hunter): Proactive hunting, Advanced analysis
│   └── SOC Manager: Strategy, Metrics, Team management
├── SOC Tools:
│   ├── SIEM: Splunk, Microsoft Sentinel, QRadar, Elastic SIEM, Wazuh
│   ├── SOAR: Phantom, XSOAR (Cortex), Swimlane — Automated response
│   ├── EDR: CrowdStrike Falcon, Carbon Black, SentinelOne, Microsoft Defender for Endpoint
│   ├── NDR: Zeek, Darktrace, ExtraHop — Network Detection & Response
│   ├── Ticketing: ServiceNow, Jira, TheHive — Incident tracking
│   └── Threat Intelligence: MISP, OpenCTI, VirusTotal, AlienVault OTX
├── SOC Metrics:
│   ├── MTTD (Mean Time to Detect): How fast threats are discovered
│   ├── MTTR (Mean Time to Respond): How fast incidents are resolved
│   ├── False Positive Rate: Tuning signal-to-noise ratio
│   └── Alert Volume: Alerts per day/week, Escalation rate
└── Shift Handoff: Ongoing incidents, Notable events, IOC updates
```

### Section 4.1.2 — SIEM & Log Analysis
```
├── SIEM Architecture:
│   ├── Log Collection: Agents, Syslog, WEF, API integrations
│   ├── Parsing & Normalization: Convert logs to common format
│   ├── Correlation: Rules that connect related events
│   ├── Alerting: Trigger on correlation rules, Thresholds
│   ├── Dashboards: Real-time visibility, KPIs
│   └── Retention: Compliance requirements, Storage management
├── Log Sources to Monitor:
│   ├── Windows Event Logs:
│   │   ├── 4624/4625: Successful/Failed logon
│   │   ├── 4672: Special privileges assigned (admin logon)
│   │   ├── 4688: New process created (command execution)
│   │   ├── 4720/4726: Account created/deleted
│   │   ├── 4732: Member added to security group
│   │   ├── 7045: New service installed
│   │   ├── 1102: Audit log cleared (cover tracks!)
│   │   └── Sysmon: Process creation, Network connections, File creation, Registry
│   ├── Linux Logs:
│   │   ├── /var/log/auth.log: Authentication events (SSH, sudo)
│   │   ├── /var/log/syslog: System events
│   │   ├── /var/log/apache2/access.log: Web server requests
│   │   ├── /var/log/secure: Security-related events (RHEL)
│   │   └── auditd: Detailed system call auditing
│   ├── Network Logs:
│   │   ├── Firewall: Allow/Deny, Source/Dest IP, Port
│   │   ├── IDS/IPS: Snort/Suricata alerts
│   │   ├── DNS: Query logs (detect DGA, tunneling)
│   │   ├── Proxy: URL filtering, Blocked domains
│   │   └── VPN: Connection logs, Failed auth
│   ├── Cloud Logs:
│   │   ├── AWS CloudTrail: API calls, IAM activity
│   │   ├── AWS GuardDuty: Threat detection findings
│   │   ├── Azure Activity Log: Resource operations
│   │   └── GCP Cloud Audit Logs: Admin and data access
│   └── Application Logs:
│       ├── Web Application: Login attempts, Errors, API calls
│       ├── Database: Query logs, Failed auth, Schema changes
│       └── Email: Inbound/outbound, Attachment hashes, SPF/DKIM failures
├── Splunk Mastery:
│   ├── SPL (Search Processing Language):
│   │   ├── Search: index=main sourcetype=syslog
│   │   ├── Filters: | where, | search, | regex
│   │   ├── Stats: | stats count by src_ip, | timechart count
│   │   ├── Table: | table _time, src_ip, dest_ip, action
│   │   ├── Lookups: Enrich data with external tables
│   │   └── Subsearches: Nested queries, Join
│   ├── Dashboards: Real-time, Scheduled, Drilldown
│   ├── Alerts: Real-time, Scheduled, Throttling
│   └── Notable Events: Correlation searches, Risk-based alerting
└── Detection Engineering:
    ├── Sigma Rules: Vendor-agnostic detection rules (YAML)
    │   └── Convert to: Splunk SPL, Elastic KQL, Microsoft KQL, QRadar AQL
    ├── YARA Rules: Pattern matching for files/memory (malware detection)
    ├── Snort/Suricata Rules: Network-based detection signatures
    ├── Detection-as-Code: Version-controlled, Tested, CI/CD pipeline
    └── MITRE ATT&CK Mapping: Map every detection to technique IDs
```

### Section 4.1.3 — Threat Intelligence
```
├── Intelligence Types:
│   ├── Strategic: High-level trends for executives
│   ├── Tactical: TTPs (Tactics, Techniques, Procedures) for defenders
│   ├── Operational: Specific campaigns, Attack details
│   └── Technical: IOCs (Indicators of Compromise) — IPs, Domains, Hashes
├── Indicators of Compromise (IOCs):
│   ├── IP Addresses: Known malicious C2 servers
│   ├── Domain Names: DGA domains, Phishing domains
│   ├── File Hashes: MD5, SHA-1, SHA-256 of malware samples
│   ├── URLs: Phishing URLs, Malware download links
│   ├── Email Addresses: Sender of phishing campaigns
│   └── YARA Signatures: Pattern-based file detection
├── Threat Intelligence Platforms:
│   ├── MISP: Open-source TIP, IOC sharing
│   ├── OpenCTI: Open-source cyber threat intelligence
│   ├── VirusTotal: Multi-scanner, Community intelligence
│   ├── AlienVault OTX: Free threat intelligence feeds
│   ├── Recorded Future: Commercial, AI-driven
│   └── Mandiant Advantage: Advanced threat intelligence
├── Threat Intelligence Frameworks:
│   ├── Diamond Model: Adversary, Infrastructure, Capability, Victim
│   ├── Kill Chain: Lockheed Martin (covered in 2.1.2)
│   ├── MITRE ATT&CK: Tactics, Techniques, Sub-techniques
│   └── STIX/TAXII: Structured Threat Information (format + transport)
└── Threat Feeds Integration:
    ├── Integrate IOCs into SIEM, Firewall, EDR, Proxy
    ├── Automated enrichment of alerts with threat context
    ├── False positive management for threat intel
    └── Attribution: Linking activity to known threat groups
```

---

## Module 4.2: Incident Response & Forensics

### Section 4.2.1 — Incident Response Process
```
├── NIST SP 800-61 Incident Response Lifecycle:
│   ├── 1. Preparation:
│   │   ├── IR Plan: Documented, Tested, Updated
│   │   ├── IR Team: Roles (IR Lead, Analyst, Communications, Legal)
│   │   ├── Communication Plan: Internal, External, Legal, PR
│   │   ├── Tools: Forensic workstation, Jump bag, Forensic images
│   │   └── Playbooks: Step-by-step for common scenarios
│   ├── 2. Detection & Analysis:
│   │   ├── Detection Sources: SIEM alerts, EDR alerts, User reports, Threat intel
│   │   ├── Triage: Is this a true incident? Severity? Scope?
│   │   ├── Initial Analysis: What happened? When? What systems?
│   │   ├── Evidence Collection: Preserve chain of custody
│   │   └── IOC Extraction: Identify indicators to search across environment
│   ├── 3. Containment, Eradication & Recovery:
│   │   ├── Short-term Containment: Isolate affected systems (network isolation)
│   │   ├── Long-term Containment: Patch, Firewall rules, Credential resets
│   │   ├── Evidence Preservation: Forensic images BEFORE cleanup
│   │   ├── Eradication: Remove malware, Close vulnerabilities, Remove persistence
│   │   └── Recovery: Restore from backups, Monitor for reinfection, Validate
│   └── 4. Post-Incident Activity:
│       ├── Lessons Learned: What went well? What didn't?
│       ├── Timeline: Complete timeline of events
│       ├── Root Cause Analysis: How did attacker get in?
│       ├── Recommendations: Prevent recurrence
│       └── Report: Executive summary + Technical details
├── Incident Classification:
│   ├── Category: Malware, Phishing, Data breach, DoS, Insider, Unauthorized access
│   ├── Severity: Critical, High, Medium, Low, Informational
│   └── Priority: Based on severity + business impact + data sensitivity
└── Common Playbooks:
    ├── Phishing Response: Analyze email → Extract IOCs → Block → Search → Notify
    ├── Malware Response: Isolate → Collect evidence → Analyze → Eradicate → Recover
    ├── Ransomware: Isolate → Assess scope → DO NOT PAY (policy) → Restore → Harden
    ├── Data Breach: Contain → Assess data exposed → Legal notification → Remediate
    └── Account Compromise: Disable account → Reset credentials → Review activity → Harden
```

### Section 4.2.2 — Digital Forensics
```
├── Forensic Principles:
│   ├── Chain of Custody: Document who handled evidence, When, Where
│   ├── Order of Volatility: Collect most volatile first
│   │   └── CPU Registers → RAM → Network State → Disk → Logs → Archives
│   ├── Write Blockers: Never modify original evidence (hardware/software)
│   ├── Forensic Images: Bit-for-bit copy (dd, FTK Imager, ewfacquire)
│   ├── Hash Verification: MD5 + SHA-256 before AND after imaging
│   └── Documentation: Every action documented with timestamps
├── Memory Forensics:
│   ├── Memory Acquisition: WinPmem, DumpIt, LiME (Linux), Magnet RAM Capture
│   ├── Volatility Framework:
│   │   ├── Process Analysis: pslist, pstree, psscan (hidden processes)
│   │   ├── Network: netscan, connections (active network connections)
│   │   ├── DLL Analysis: dlllist, ldrmodules (injected DLLs)
│   │   ├── Command Line: cmdline, cmdscan, consoles
│   │   ├── Registry: hivelist, printkey
│   │   ├── Malware: malfind (injected code), yarascan
│   │   └── Timelining: timeliner (create timeline of events)
│   └── What to Look For: Suspicious processes, Injected code, Network connections, Credentials
├── Disk Forensics:
│   ├── Image Creation: dd, dc3dd, FTK Imager, ewfacquire (E01 format)
│   ├── File System Analysis:
│   │   ├── Autopsy / Sleuth Kit: Open-source forensic suite
│   │   ├── FTK (Forensic Toolkit): Commercial forensic tool
│   │   ├── EnCase: Enterprise forensic platform
│   │   └── X-Ways Forensics: Advanced hex editor + forensics
│   ├── Evidence Types:
│   │   ├── Deleted Files: Recover from unallocated space
│   │   ├── File Metadata: Timestamps (MACB), File size, Owner
│   │   ├── Alternate Data Streams: Hidden data in NTFS
│   │   ├── Prefetch Files: Evidence of program execution (Windows)
│   │   ├── Browser Artifacts: History, Cookies, Cache, Downloads
│   │   ├── Registry Analysis: Autoruns, MRU lists, USB history
│   │   ├── Event Logs: Windows Event logs (EVTX)
│   │   ├── Email Forensics: PST/OST files, Email headers
│   │   └── Recycle Bin: Deleted file metadata
│   └── Timeline Analysis: Super timelines with Plaso/log2timeline
├── Network Forensics:
│   ├── Packet Capture Analysis: Wireshark, tcpdump, tshark
│   ├── NetFlow Analysis: Traffic patterns, Beaconing detection
│   ├── Zeek (Bro) Logs: Connection, DNS, HTTP, SSL, File logs
│   ├── Evidence: C2 traffic, Exfiltration, Lateral movement
│   └── Encrypted Traffic Analysis: JA3/JA3S fingerprinting, Metadata analysis
├── Mobile Forensics:
│   ├── Acquisition: Physical, Logical, File system, Cloud
│   ├── iOS: iTunes backups, Cellebrite, GrayKey
│   ├── Android: ADB, JTAG, Chip-off
│   └── Evidence: Messages, Call logs, Location, App data, Browser
└── Cloud Forensics:
    ├── Challenges: No physical access, Shared infrastructure, Data volatility
    ├── AWS: CloudTrail, VPC Flow Logs, S3 access logs, GuardDuty
    ├── Azure: Activity logs, NSG flow logs, Sentinel
    └── Evidence Collection: API logs, Snapshot instances, Memory capture
```

---

## Module 4.3: Threat Hunting

### Section 4.3.1 — Proactive Threat Hunting
```
├── Hunting Methodology:
│   ├── Hypothesis-Driven: "Attackers may be using PowerShell for lateral movement"
│   ├── IOC-Driven: Search for specific indicators from threat intel
│   ├── TTP-Driven: Hunt for techniques from MITRE ATT&CK
│   └── Data-Driven: Anomaly detection on baselines
├── Hunting Techniques:
│   ├── Stack Counting: Find outliers in large datasets (rare processes, rare connections)
│   ├── Clustering: Group similar behaviors, Identify anomalies
│   ├── Baselining: Know normal → Detect abnormal
│   ├── Frequency Analysis: Beaconing detection (regular C2 callbacks)
│   └── Long-Tail Analysis: Focus on rare events in the tail of the distribution
├── Hunting Data Sources:
│   ├── Endpoint: Process creation, Network connections, File modifications
│   ├── Network: DNS queries, Proxy logs, NetFlow, PCAP
│   ├── Authentication: Failed logins, Unusual login times, Impossible travel
│   ├── Cloud: API calls, Resource creation, Permission changes
│   └── Email: Attachment analysis, URL reputation, Header anomalies
├── Common Hunts:
│   ├── Living off the Land (LOLBins): PowerShell, certutil, bitsadmin, mshta, regsvr32
│   ├── Persistence Mechanisms: Registry keys, Scheduled tasks, WMI subscriptions
│   ├── Lateral Movement: PsExec, WMI, WinRM, RDP, SMB
│   ├── C2 Beaconing: Regular HTTP/HTTPS intervals, DNS tunneling
│   ├── Data Exfiltration: Large outbound transfers, DNS data encoding
│   ├── Credential Access: LSASS access, SAM dumps, DCSync
│   └── Defense Evasion: Process injection, Timestomping, Log tampering
└── Tools:
    ├── Elastic (ELK): Kibana queries for hunting
    ├── Splunk: SPL queries, Risk-based alerting
    ├── Velociraptor: Endpoint visibility and hunting at scale
    ├── OSQuery: SQL-based endpoint queries
    ├── RITA: Real Intelligence Threat Analytics (beaconing detection)
    └── Jupyter Notebooks: Data analysis, Python hunting scripts
```

---

## Module 4.4: Malware Analysis (Introduction)

### Section 4.4.1 — Malware Analysis Fundamentals
```
├── Malware Types:
│   ├── Virus: Self-replicating, Attaches to files
│   ├── Worm: Self-propagating, Network-based
│   ├── Trojan: Disguised as legitimate software
│   ├── Ransomware: Encrypts files, Demands payment
│   ├── Spyware: Steals information silently
│   ├── Adware: Unwanted advertisements
│   ├── Rootkit: Hides presence at OS level
│   ├── Bootkit: Infects boot process (MBR/UEFI)
│   ├── RAT (Remote Access Trojan): Persistent remote access
│   ├── Cryptominer: Unauthorized cryptocurrency mining
│   ├── Fileless Malware: Lives in memory, Uses LOLBins
│   └── Wiper: Destroys data (NotPetya, WhisperGate)
├── Analysis Types:
│   ├── Static Analysis (No execution):
│   │   ├── File Properties: Size, Type, Hash (MD5, SHA-256)
│   │   ├── Strings: strings command, FLOSS (obfuscated strings)
│   │   ├── PE Analysis: Headers, Sections, Imports, Exports (PEStudio, PE-bear)
│   │   ├── Packing Detection: UPX, Themida, Custom packers (Detect It Easy)
│   │   ├── YARA Matching: Pattern-based malware family identification
│   │   └── Disassembly (basic): IDA Free, Ghidra — Entry point, Functions
│   ├── Dynamic Analysis (Execute in sandbox):
│   │   ├── Behavioral Analysis: What does it do when run?
│   │   ├── System Changes: Files created/modified, Registry changes
│   │   ├── Network Activity: C2 connections, Downloads, DNS queries
│   │   ├── Process Activity: Child processes, Injected processes
│   │   ├── Sandboxes: ANY.RUN, Joe Sandbox, Cuckoo Sandbox, Hybrid Analysis
│   │   └── Tools: Process Monitor (ProcMon), Process Explorer, Wireshark, Regshot
│   └── Online Analysis:
│       ├── VirusTotal: Multi-AV scan, Behavioral analysis, Relationships
│       ├── Hybrid Analysis: Free online sandbox (Falcon Sandbox)
│       ├── ANY.RUN: Interactive online sandbox
│       └── MalwareBazaar: Malware sample sharing
├── Safe Analysis Environment:
│   ├── Isolated VM: No network access to host/production
│   ├── Snapshots: Restore to clean state after analysis
│   ├── REMnux: Linux distro for malware analysis
│   ├── FLARE-VM: Windows-based malware analysis VM (Mandiant)
│   └── Network Simulation: INetSim, FakeDNS — Simulate internet
└── Analysis Report:
    ├── Summary: What it is, What it does, Severity
    ├── IOCs: Hashes, C2 domains/IPs, File paths, Registry keys
    ├── Behavior: Detailed execution chain
    ├── MITRE ATT&CK Mapping: Techniques used by the malware
    └── Detection: YARA rules, Sigma rules, Snort/Suricata rules
```

---

> ### 🛠️ PHASE 4 PROJECT: **SOC Simulation — Detect & Respond**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │              SOC SIMULATION — FULL EXERCISE                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ SETUP:                                                          │
> │  ✅ Deploy Security Onion or ELK Stack as SIEM                  │
> │  ✅ Deploy Wazuh agents on 3+ endpoints                         │
> │  ✅ Configure Sysmon on Windows targets                         │
> │  ✅ Enable centralized logging (Syslog from all devices)        │
> │  ✅ Integrate threat intelligence feeds (AlienVault OTX)        │
> │                                                                 │
> │ DETECTION ENGINEERING:                                          │
> │  ✅ Write 10 Sigma detection rules:                              │
> │     • Mimikatz execution (process name/hash)                    │
> │     • Kerberoasting (Event ID 4769, RC4 encryption)             │
> │     • PowerShell suspicious execution (encoded commands)        │
> │     • Brute force login (5+ failed logins in 5 min)             │
> │     • New service installation (Event ID 7045)                  │
> │     • Scheduled task creation (persistence)                     │
> │     • DCSync (Event ID 4662, DS-Replication)                    │
> │     • LSASS access (Sysmon Event ID 10)                         │
> │     • DNS tunneling (query length > 50 chars)                   │
> │     • Log clearing (Event ID 1102)                              │
> │  ✅ Convert Sigma rules to SIEM-specific queries                │
> │                                                                 │
> │ ATTACK SIMULATION (Purple Team):                                │
> │  ✅ Execute 10 attacks from Phase 3 against monitored targets   │
> │  ✅ For each attack:                                             │
> │     • Execute the attack technique                              │
> │     • Verify SIEM detects it (or identify gap)                  │
> │     • Document MITRE ATT&CK technique ID                        │
> │     • Tune detection to reduce false positives                  │
> │                                                                 │
> │ INCIDENT RESPONSE:                                              │
> │  ✅ Simulate a ransomware incident end-to-end:                  │
> │     • Detection: Alert fires in SIEM                            │
> │     • Triage: Assess scope and severity                         │
> │     • Containment: Isolate affected hosts                       │
> │     • Forensics: Memory dump + Disk image + Timeline            │
> │     • Eradication: Remove persistence, Patch vulnerability      │
> │     • Recovery: Restore from backup, Verify clean               │
> │  ✅ Write complete Incident Response report                     │
> │                                                                 │
> │ MALWARE ANALYSIS:                                               │
> │  ✅ Analyze 3 malware samples (from MalwareBazaar):             │
> │     • Static analysis (hashes, strings, PE headers)             │
> │     • Dynamic analysis (sandbox, network, behavior)             │
> │     • YARA rule creation for each sample                        │
> │     • IOC extraction and MITRE mapping                          │
> │                                                                 │
> │ THREAT HUNT:                                                    │
> │  ✅ Conduct 3 hypothesis-driven hunts:                           │
> │     • Hunt for PowerShell Empire / LOLBin usage                 │
> │     • Hunt for beaconing (C2 callback patterns)                 │
> │     • Hunt for credential access (LSASS, SAM dumps)             │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# ☁️ PHASE 5: SPECIALIZED SECURITY DOMAINS
### 📅 Duration: Months 14–18
### 🎯 Goal: Deep expertise in specific security domains
### 👤 Level: Security Engineer
### 📜 Certifications: AWS Security Specialty, AZ-500, CCSP, OSWE

---

## Module 5.1: Cloud Security

### Section 5.1.1 — Cloud Security Architecture
```
├── Shared Responsibility Model:
│   ├── IaaS: Customer secures OS, Network, Applications, Data
│   ├── PaaS: Customer secures Applications, Data
│   ├── SaaS: Customer secures Data, Access management
│   └── Provider: Physical infrastructure, Hypervisor, Network fabric
├── AWS Security:
│   ├── IAM: Users, Groups, Roles, Policies (JSON), Least privilege
│   │   └── STS: Temporary credentials, AssumeRole, Cross-account access
│   ├── VPC Security: Security Groups (stateful), NACLs (stateless), VPC Flow Logs
│   ├── S3 Security: Bucket policies, ACLs, Block Public Access, Encryption, Versioning
│   ├── KMS: Key management, CMK, Envelope encryption, Key rotation
│   ├── CloudTrail: API audit logging, Management + Data events
│   ├── GuardDuty: Threat detection (DNS, VPC Flow, CloudTrail analysis)
│   ├── Config: Resource compliance, Configuration drift detection
│   ├── WAF: Web Application Firewall, Managed rule groups
│   ├── Shield: DDoS protection (Standard free, Advanced paid)
│   ├── Macie: PII discovery in S3 (GDPR compliance)
│   ├── Inspector: Vulnerability scanning for EC2, ECR, Lambda
│   ├── Secrets Manager: Secret rotation, RDS integration
│   └── Security Hub: Centralized security findings aggregation
├── Azure Security:
│   ├── Entra ID (Azure AD): Identity management, Conditional Access, PIM
│   ├── NSG: Network Security Groups
│   ├── Azure Defender / Microsoft Defender for Cloud
│   ├── Azure Sentinel: Cloud-native SIEM
│   ├── Key Vault: Secret and key management
│   └── Azure Policy: Compliance enforcement
├── Cloud Attack Techniques:
│   ├── Credential Leaks: GitHub exposed keys, Metadata service (IMDS)
│   ├── SSRF to Metadata: http://169.254.169.254/latest/meta-data/ (IMDSv1)
│   ├── Misconfigured S3 Buckets: Public read/write, Directory listing
│   ├── IAM Privilege Escalation: Overly permissive policies, iam:PassRole
│   ├── Lambda Injection: Code injection in serverless functions
│   ├── Cross-Account Access: Misconfigured trust policies
│   └── Container Escape: Privileged containers, Mounted Docker socket
├── Cloud Security Tools:
│   ├── Prowler: AWS security assessment tool
│   ├── ScoutSuite: Multi-cloud security auditing
│   ├── Pacu: AWS exploitation framework
│   ├── CloudSploit: Cloud security scanner
│   └── Steampipe: SQL-based cloud infrastructure queries
└── Cloud Compliance:
    ├── CIS Benchmarks: AWS, Azure, GCP hardening guides
    ├── AWS Well-Architected: Security pillar
    └── Cloud Security Alliance (CSA): STAR certification, CCM
```

### Section 5.1.2 — Container & Kubernetes Security
```
├── Container Security:
│   ├── Image Security: Vulnerability scanning (Trivy, Snyk, Grype)
│   ├── Base Image Selection: Minimal, Trusted, Updated (distroless)
│   ├── Non-root Containers: Run as unprivileged user
│   ├── Read-only File Systems: Prevent runtime modifications
│   ├── Secret Management: Kubernetes Secrets, External Secrets Operator, Vault
│   ├── Image Signing: Cosign, Notary — Verify image integrity
│   └── Registry Security: Private registry, Image pull policies
├── Kubernetes Security:
│   ├── RBAC: Roles, ClusterRoles, RoleBindings — Least privilege
│   ├── Network Policies: Pod-to-pod firewall (Calico, Cilium)
│   ├── Pod Security Standards: Restricted, Baseline, Privileged
│   ├── Service Accounts: Disable auto-mount tokens, Scoped permissions
│   ├── Secrets Encryption: etcd encryption, External secrets (Vault, AWS SM)
│   ├── Admission Controllers: OPA Gatekeeper, Kyverno — Policy enforcement
│   ├── Runtime Security: Falco, Sysdig — Detect anomalous container behavior
│   └── Supply Chain: Signed images, SBOM, In-Toto
├── Kubernetes Attack Techniques:
│   ├── Exposed Dashboard: Kubernetes Dashboard without auth
│   ├── etcd Access: Unencrypted, Unauthenticated etcd access
│   ├── Privileged Pods: Mount host filesystem, Escape container
│   ├── Service Account Token Theft: Access API server with pod token
│   └── Cluster Takeover: RBAC escalation, Node compromise
└── Tools:
    ├── kube-bench: CIS Kubernetes Benchmark testing
    ├── kube-hunter: Penetration testing for K8s
    ├── Trivy: Container image + K8s vulnerability scanner
    ├── Falco: Runtime security (detect suspicious syscalls)
    └── Kubescape: Kubernetes security scanning (NSA, MITRE)
```

---

## Module 5.2: Application Security (AppSec)

### Section 5.2.1 — Secure Software Development Lifecycle (SSDLC)
```
├── Shift Left: Security earlier in SDLC, Not just at the end
├── Security in Each Phase:
│   ├── Requirements: Security requirements, Abuse cases, Data classification
│   ├── Design: Threat modeling (STRIDE), Secure design patterns
│   ├── Development: Secure coding practices, Code review, SAST
│   ├── Testing: DAST, IAST, Penetration testing, Fuzzing
│   ├── Deployment: Container scanning, IaC scanning, Secret detection
│   └── Operations: RASP, WAF, Monitoring, Vulnerability management
├── Security Testing Tools:
│   ├── SAST (Static): SonarQube, Semgrep, Checkmarx, Fortify
│   ├── DAST (Dynamic): OWASP ZAP, Burp Suite, Nuclei
│   ├── IAST (Interactive): Contrast Security (agent-based, runtime)
│   ├── SCA (Software Composition Analysis): Snyk, Dependabot, OWASP Dependency-Check
│   ├── Secret Detection: truffleHog, GitLeaks, detect-secrets
│   ├── IaC Scanning: Checkov, tfsec, KICS — Terraform/CloudFormation
│   └── Fuzzing: AFL, LibFuzzer, Jazzer — Find edge-case crashes
├── DevSecOps Pipeline:
│   ├── Pre-commit: Secrets scanning, Linting
│   ├── CI Build: SAST, SCA, Container scan, Unit tests
│   ├── CI Test: DAST, Integration tests, API security tests
│   ├── Pre-deploy: Policy checks (OPA), Compliance validation
│   ├── Deploy: Signed artifacts, Image signature verification
│   └── Runtime: WAF, RASP, Monitoring, Vulnerability alerts
└── Security Champions: Developer-embedded security advocates
```

### Section 5.2.2 — API Security
```
├── OWASP API Security Top 10:
│   ├── API1: Broken Object Level Authorization (BOLA/IDOR)
│   ├── API2: Broken Authentication
│   ├── API3: Broken Object Property Level Authorization
│   ├── API4: Unrestricted Resource Consumption
│   ├── API5: Broken Function Level Authorization
│   ├── API6: Unrestricted Access to Sensitive Business Flows
│   ├── API7: Server-Side Request Forgery (SSRF)
│   ├── API8: Security Misconfiguration
│   ├── API9: Improper Inventory Management
│   └── API10: Unsafe Consumption of APIs
├── API Authentication: OAuth 2.0, API keys, mTLS, JWT
├── API Rate Limiting: Per key, Per endpoint, Per IP
├── API Gateway Security: WAF, Input validation, Schema validation
├── GraphQL Security: Introspection control, Query depth limiting, Cost analysis
└── Tools: Postman, Burp Suite, OWASP ZAP, Nuclei, API fuzzing
```

---

## Module 5.3: Identity & Access Management (IAM)

### Section 5.3.1 — Enterprise IAM
```
├── Identity Lifecycle: Provisioning → Management → Deprovisioning
├── Directory Services: Active Directory, Entra ID, Okta, OneLogin
├── Federation: SAML, OAuth 2.0/OIDC, WS-Federation
├── Privileged Access Management: CyberArk, BeyondTrust, Thycotic
├── Identity Governance: Access reviews, Certification campaigns, Segregation of Duties
├── Zero Trust Identity: Continuous verification, Risk-based authentication
├── Conditional Access: Location, Device, Risk level, Application sensitivity
└── SCIM: System for Cross-domain Identity Management (automated provisioning)
```

---

## Module 5.4: Network Security Engineering

### Section 5.4.1 — Advanced Network Security
```
├── Next-Gen Firewalls: Application awareness, User identity, IPS, SSL inspection
│   └── Vendors: Palo Alto, Fortinet, Check Point, Cisco Firepower
├── IDS/IPS: Snort, Suricata — Rule writing, Tuning, Evasion
├── Network Access Control (NAC): 802.1X, Cisco ISE, Aruba ClearPass
├── DNS Security: DNS filtering, Sinkholing, DNSSEC, DNS over HTTPS
├── Email Security: SPF, DKIM, DMARC, Email gateways, Anti-phishing
├── DLP (Data Loss Prevention): Network DLP, Endpoint DLP, Cloud DLP
├── Network Segmentation: Microsegmentation, Zero Trust networking
├── Web Proxy: Forward proxy, SSL inspection, URL filtering
└── Deception Technology: Honeypots, Honeynets, Honeytokens, Canary tokens
```

---

> ### 🛠️ PHASE 5 PROJECT: **Secure Cloud Infrastructure & DevSecOps Pipeline**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │        SECURE CLOUD INFRASTRUCTURE + DEVSECOPS                  │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ ✅ Deploy a 3-tier web app on AWS (Terraform IaC):              │
> │    • VPC with public/private subnets, NAT Gateway               │
> │    • ALB → ECS Fargate → RDS PostgreSQL                         │
> │    • All encrypted (KMS), All logged (CloudTrail)               │
> │                                                                 │
> │ ✅ IAM Security:                                                │
> │    • Least privilege IAM roles (no wildcards!)                   │
> │    • MFA enforced for all users                                 │
> │    • Service roles for ECS tasks                                │
> │    • Cross-account access with AssumeRole                       │
> │                                                                 │
> │ ✅ DevSecOps Pipeline (GitHub Actions):                         │
> │    • Pre-commit: GitLeaks (secret scanning)                     │
> │    • Build: SAST (Semgrep), SCA (Snyk), Container scan (Trivy)  │
> │    • Test: DAST (OWASP ZAP), API security tests                 │
> │    • IaC: Checkov/tfsec scan of Terraform                       │
> │    • Deploy: Signed container images, ArgoCD                    │
> │    • Runtime: GuardDuty + CloudTrail → Sentinel/Splunk          │
> │                                                                 │
> │ ✅ Security Assessment:                                         │
> │    • Run Prowler/ScoutSuite against your AWS account            │
> │    • CIS AWS Benchmark compliance check                         │
> │    • Attempt SSRF to IMDS, Verify IMDSv2 blocks it             │
> │    • Verify all S3 buckets are private                          │
> │    • Test IAM privilege escalation paths                        │
> │                                                                 │
> │ ✅ Kubernetes Security (bonus):                                 │
> │    • Deploy on EKS with Network Policies                        │
> │    • Pod Security Standards (restricted)                        │
> │    • Falco for runtime detection                                │
> │    • kube-bench CIS compliance check                            │
> │                                                                 │
> │ 📄 Deliverables: Security architecture diagram, Pipeline docs,  │
> │    Assessment report, Remediation evidence                      │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 💀 PHASE 6: ADVANCED OFFENSIVE SECURITY
### 📅 Duration: Months 18–22
### 🎯 Goal: Exploit development, Malware analysis, Red Team operations
### 👤 Level: Senior Red Teamer / Security Researcher
### 📜 Certifications: OSCP, OSWE, OSEP, CRTO, GPEN, GXPN

---

## Module 6.1: Advanced Exploitation

### Section 6.1.1 — Exploit Development Foundations
```
├── x86/x64 Assembly:
│   ├── Registers: EAX, EBX, ECX, EDX, ESP, EBP, EIP, EFLAGS
│   ├── Instructions: MOV, PUSH, POP, CALL, RET, JMP, CMP, TEST, NOP
│   ├── Calling Conventions: cdecl, stdcall, fastcall
│   ├── Stack Operations: Function prologue/epilogue, Stack frames
│   └── System Calls: INT 0x80 (Linux), syscall instruction
├── Memory Corruption:
│   ├── Buffer Overflow:
│   │   ├── Stack-Based: Overwrite return address → Control EIP/RIP
│   │   ├── Heap-Based: Chunk metadata corruption, Use-after-free
│   │   ├── Off-by-One: One byte overflow → Frame pointer overwrite
│   │   └── Format String: %x, %n → Read/Write memory
│   ├── Exploitation Process:
│   │   ├── 1. Discover: Fuzzing, Code review, Crash analysis
│   │   ├── 2. Control EIP: Determine offset, Overwrite return address
│   │   ├── 3. Place Shellcode: On stack, Heap spray, Egg hunting
│   │   └── 4. Redirect Execution: JMP ESP, ROP chain, Ret2libc
│   ├── Protections:
│   │   ├── ASLR (Address Space Layout Randomization): Random base addresses
│   │   ├── DEP/NX (Data Execution Prevention): Non-executable stack
│   │   ├── Stack Canaries: Detect stack overwrites
│   │   ├── PIE (Position Independent Executable): Code at random address
│   │   ├── RELRO: Relocation Read-Only (protect GOT)
│   │   └── CFI (Control Flow Integrity): Validate branch targets
│   └── Bypass Techniques:
│       ├── ROP (Return-Oriented Programming): Chain gadgets to bypass DEP
│       ├── Ret2libc: Call system() or execve() — bypass NX
│       ├── Information Leak: Bypass ASLR by leaking addresses
│       ├── Heap Spraying: Fill heap with shellcode, Increase hit probability
│       └── JIT Spraying: Abuse JIT compilation to create executable code
├── Shellcoding:
│   ├── Linux Shellcode: execve("/bin/sh") in assembly
│   ├── Windows Shellcode: WinExec, CreateProcess, Reverse shell
│   ├── Encoders: XOR encoding, Polymorphic shellcode (avoid detection)
│   ├── Staged vs Stageless: Download full payload vs All-in-one
│   └── Tools: msfvenom, Donut, ScareCrow
└── Tools:
    ├── GDB + PEDA/GEF/pwndbg: Linux debugging
    ├── WinDbg / x64dbg: Windows debugging
    ├── IDA Pro / Ghidra: Disassembly & Decompilation
    ├── Radare2 / Cutter: Open-source reverse engineering
    ├── ROPgadget / Ropper: ROP chain building
    └── pwntools: Python exploitation library (CTF & Real-world)
```

### Section 6.1.2 — Advanced Web Exploitation
```
├── Deserialization Attacks:
│   ├── Java: ysoserial, Apache Commons exploits
│   ├── PHP: phpggc, POP chains
│   ├── .NET: ysoserial.net
│   └── Python: pickle, yaml.load
├── Race Conditions: TOCTOU, Double-submit, Limit bypass
├── Prototype Pollution (JavaScript): __proto__ manipulation
├── WebSocket Attacks: Cross-site WebSocket hijacking, Injection
├── OAuth Attacks: Redirect URI manipulation, Token theft, PKCE bypass
├── JWT Attacks: Algorithm confusion (none, HS256 vs RS256), Key injection
├── GraphQL Attacks: Introspection, Batching, Nested queries DoS
├── Cache Poisoning: Web cache deception, Cache key manipulation
└── HTTP Request Smuggling: CL.TE, TE.CL, TE.TE desync attacks
```

---

## Module 6.2: Advanced Malware Analysis & Reverse Engineering

### Section 6.2.1 — Reverse Engineering
```
├── Static Analysis (Advanced):
│   ├── IDA Pro: Industry standard disassembler, Decompiler (Hex-Rays)
│   ├── Ghidra: NSA's open-source reverse engineering framework
│   ├── PE Format Deep Dive: Sections, IAT, EAT, Resources, Debug info
│   ├── ELF Format: Sections, Symbols, Dynamic linking, GOT/PLT
│   ├── Control Flow Analysis: Function identification, Basic blocks, CFG
│   └── Obfuscation: Packing (UPX, Themida), VM protection, Anti-analysis
├── Anti-Analysis Techniques:
│   ├── Anti-Debugging: IsDebuggerPresent, Timing checks, Int3 detection
│   ├── Anti-VM: CPUID checks, Registry artifacts, MAC address checks
│   ├── Anti-Sandbox: Sleep extended, User interaction required, Environment checks
│   ├── String Encryption: XOR, AES, Custom encoding
│   ├── Code Obfuscation: Control flow flattening, Dead code insertion
│   └── Rootkit Techniques: API hooking, SSDT hooking, DKOM
├── Dynamic Analysis (Advanced):
│   ├── Debugging: Step through code, Set breakpoints, Modify execution
│   ├── API Monitoring: API Monitor, x64dbg + API logging
│   ├── System Call Tracing: strace (Linux), Process Monitor (Windows)
│   ├── Network Emulation: INetSim, FakeNet-NG
│   └── Memory Dumping: Unpack in memory, Dump unpacked binary
└── Malware Categories Deep Dive:
    ├── Ransomware: Encryption algorithms, Key management, C2 communication
    ├── Banking Trojans: Web injection, Form grabbing, Man-in-the-Browser
    ├── APT Implants: Custom protocols, DNS C2, Steganography
    ├── Bootkits/Rootkits: UEFI, MBR, Kernel-level persistence
    └── Fileless: PowerShell, WMI, Reflective DLL injection, .NET in-memory
```

---

## Module 6.3: Red Team Operations

### Section 6.3.1 — Red Team Methodology
```
├── Red Team vs Pentest:
│   ├── Pentest: Find as many vulnerabilities as possible
│   └── Red Team: Simulate real adversary, Test detection and response
├── Planning:
│   ├── Threat Profile: Emulate specific APT group (MITRE ATT&CK)
│   ├── Rules of Engagement: Scope, Restrictions, Notifications
│   ├── Communication Plan: Emergency contacts, Deconfliction
│   └── Objective: Specific goal (steal PII, access CEO email, exfiltrate IP)
├── Infrastructure:
│   ├── C2 Infrastructure: Redirectors, Domain fronting, Malleable C2 profiles
│   ├── Phishing Infrastructure: Look-alike domains, GoPhish, Evilginx2
│   ├── OpSec: Separate infrastructure, VPNs, Clean identities
│   └── Tools: Cobalt Strike, Sliver, Mythic, Nighthawk, Brute Ratel
├── Initial Access:
│   ├── Phishing: Spear phishing with payloads, Credential harvesting
│   ├── Watering Hole: Compromise trusted website
│   ├── Supply Chain: Compromised dependency, Trusted vendor
│   ├── Physical: USB drop, Tailgating, Lock picking
│   └── Exploit: Public-facing application, VPN, Webmail
├── Execution & Evasion:
│   ├── Living off the Land (LOLBins): PowerShell, certutil, mshta, regsvr32
│   ├── AMSI Bypass: Patch AMSI in memory, Obfuscation
│   ├── AV Evasion: Custom loaders, Syscall-based execution, Process hollowing
│   ├── EDR Evasion: Direct syscalls, Unhooking DLLs, ETW patching
│   ├── Application Whitelisting Bypass: MSBuild, InstallUtil, WMIC
│   └── Payload Delivery: HTA, ISO, LNK, VBA macros (post-Mark of the Web)
├── Persistence:
│   ├── Registry: Run keys, COM objects, AppInit DLLs
│   ├── Scheduled Tasks: schtasks, Task Scheduler
│   ├── WMI Event Subscriptions: Fileless persistence
│   ├── Golden/Silver Tickets: Kerberos persistence
│   ├── DCShadow: AD persistence
│   ├── ADCS: Certificate-based persistence
│   └── SID History: Domain persistence via SID injection
├── Reporting:
│   ├── Attack Narrative: Story of the engagement, Timeline
│   ├── MITRE ATT&CK Mapping: Every technique used, Detection gaps
│   ├── Detection Gaps: What the Blue Team missed
│   ├── Recommendations: Technical and process improvements
│   └── Debrief: Joint Red + Blue team review
└── Purple Teaming:
    ├── Collaborative: Red executes, Blue detects in real-time
    ├── Atomic Red Team: Small, testable ATT&CK techniques
    ├── CALDERA: Automated adversary emulation (MITRE)
    └── Objective: Improve detection capabilities, Not just "win"
```

---

> ### 🛠️ PHASE 6 PROJECT: **Full Red Team Engagement Simulation**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │              RED TEAM ENGAGEMENT SIMULATION                     │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Simulate a full APT engagement against your AD lab:             │
> │                                                                 │
> │ ✅ PLANNING:                                                    │
> │    • Select APT group to emulate (e.g., APT29)                  │
> │    • Map their TTPs from MITRE ATT&CK                           │
> │    • Build C2 infrastructure (Sliver/Mythic + redirectors)      │
> │    • Set up phishing infrastructure (GoPhish)                   │
> │                                                                 │
> │ ✅ INITIAL ACCESS:                                              │
> │    • Craft spear phishing email with payload                    │
> │    • Bypass AMSI + Windows Defender                              │
> │    • Establish C2 callback (HTTPS + domain fronting)            │
> │                                                                 │
> │ ✅ POST-EXPLOITATION:                                           │
> │    • Enumerate AD with BloodHound (stealthily)                  │
> │    • Kerberoast service accounts                                │
> │    • Move laterally to Domain Controller                        │
> │    • DCSync for all domain hashes                               │
> │    • Create Golden Ticket for persistence                       │
> │    • Exfiltrate "sensitive data" via DNS tunneling              │
> │                                                                 │
> │ ✅ EVASION:                                                     │
> │    • Custom loader (bypass AV signature detection)              │
> │    • Process injection (avoid suspicious processes)             │
> │    • ETW patching (reduce telemetry)                            │
> │    • Timestomping (modify file timestamps)                      │
> │                                                                 │
> │ ✅ EXPLOIT DEVELOPMENT:                                         │
> │    • Write a stack buffer overflow exploit for a practice binary │
> │    • Create a custom reverse shell in C/Assembly                │
> │    • Bypass DEP using ROP chain                                 │
> │                                                                 │
> │ ✅ MALWARE ANALYSIS:                                            │
> │    • Reverse engineer 2 real-world malware samples (Ghidra)     │
> │    • Document: Unpacking, C2 protocol, Persistence mechanism   │
> │    • Write YARA + Sigma rules for detection                     │
> │                                                                 │
> │ 📄 Full Red Team report with ATT&CK mapping + detection gaps    │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 📋 PHASE 7: GOVERNANCE, RISK & COMPLIANCE (GRC) + LEADERSHIP
### 📅 Duration: Months 22–26
### 🎯 Goal: Lead security programs, Manage risk, Ensure compliance
### 👤 Level: Security Manager / CISO
### 📜 Certifications: CISSP, CISM, CRISC, CGRC, ISO 27001 Lead Auditor

---

## Module 7.1: Risk Management

### Section 7.1.1 — Risk Assessment & Management
```
├── Risk Concepts:
│   ├── Threat: Potential cause of unwanted impact
│   ├── Vulnerability: Weakness that can be exploited
│   ├── Risk: Probability × Impact (Threat exploiting Vulnerability)
│   ├── Asset: What we're protecting (data, systems, people, reputation)
│   ├── Control: Measure to reduce risk (preventive, detective, corrective)
│   └── Residual Risk: Risk remaining AFTER controls are applied
├── Risk Assessment Methods:
│   ├── Qualitative: High/Medium/Low ratings, Risk matrix
│   ├── Quantitative:
│   │   ├── SLE (Single Loss Expectancy): Asset Value × Exposure Factor
│   │   ├── ARO (Annual Rate of Occurrence): How often per year
│   │   ├── ALE (Annual Loss Expectancy): SLE × ARO
│   │   └── ROI of Controls: (ALE before - ALE after - Control cost) / Control cost
│   └── Semi-Quantitative: Hybrid approach (FAIR methodology)
├── Risk Treatment:
│   ├── Mitigate: Implement controls to reduce risk
│   ├── Transfer: Insurance, Outsourcing, SLAs
│   ├── Accept: Acknowledge risk, Document decision (risk acceptance)
│   ├── Avoid: Eliminate the risky activity entirely
│   └── Risk Register: Track all identified risks, Owners, Status, Treatment
├── Risk Frameworks:
│   ├── NIST RMF: Risk Management Framework (SP 800-37)
│   ├── ISO 31000: Risk management standard
│   ├── FAIR: Factor Analysis of Information Risk (quantitative)
│   ├── OCTAVE: Operationally Critical Threat, Asset, and Vulnerability Evaluation
│   └── COSO ERM: Enterprise Risk Management
└── Third-Party Risk Management:
    ├── Vendor Assessment: Security questionnaires, SOC 2 reports
    ├── SIG (Standardized Information Gathering): Shared Assessments
    ├── Continuous Monitoring: SecurityScorecard, BitSight, UpGuard
    ├── Contract Requirements: Data handling, Breach notification, Audit rights
    └── Supply Chain Risk: Software supply chain (SBOM), Hardware supply chain
```

---

## Module 7.2: Compliance & Regulatory

### Section 7.2.1 — Compliance Frameworks (Deep Dive)
```
├── ISO 27001:
│   ├── ISMS: Information Security Management System
│   ├── Annex A Controls: 93 controls across 4 themes (2022 version)
│   ├── Risk Assessment: Mandatory, documented, reviewed
│   ├── Certification: External audit, 3-year cycle, Annual surveillance
│   └── Statement of Applicability (SoA): Which controls apply and why
├── SOC 2 (Type I & Type II):
│   ├── Trust Service Criteria: Security, Availability, Confidentiality,
│   │   Processing Integrity, Privacy
│   ├── Type I: Controls design at a point in time
│   ├── Type II: Controls effectiveness over a period (3-12 months)
│   └── SOC 2 Report: For customers/partners, Demonstrates security posture
├── PCI DSS v4.0:
│   ├── 12 Requirements: Firewall, Encryption, Access control, Monitoring, Testing
│   ├── Scope Reduction: Tokenization, P2PE, PCI-compliant service providers
│   ├── SAQ vs ROC: Self-Assessment Questionnaire vs Report on Compliance
│   └── Requirement 6: Secure software development
├── GDPR:
│   ├── Data Subject Rights: Access, Rectification, Erasure, Portability
│   ├── Legal Bases: Consent, Contract, Legitimate interest
│   ├── DPIA (Data Protection Impact Assessment): For high-risk processing
│   ├── DPO (Data Protection Officer): When required, Role
│   ├── Breach Notification: 72 hours to supervisory authority
│   └── Fines: Up to €20M or 4% of global annual revenue
├── HIPAA:
│   ├── Privacy Rule: Use and disclosure of PHI
│   ├── Security Rule: Administrative, Physical, Technical safeguards
│   ├── Breach Notification Rule: Notification requirements
│   └── BAA: Business Associate Agreements
├── NIST SP 800-53:
│   ├── Control Families: 20 families (AC, AU, AT, CM, CP, IA, IR, MA, etc.)
│   ├── Control Baselines: Low, Moderate, High impact
│   ├── FedRAMP: Cloud security for US government (based on 800-53)
│   └── CMMC: Cybersecurity Maturity Model Certification (DoD contractors)
└── Audit & Evidence:
    ├── Evidence Collection: Policies, Screenshots, Configurations, Logs
    ├── Control Testing: Design effectiveness + Operating effectiveness
    ├── Audit Readiness: Continuous compliance, Not annual scramble
    └── Compliance Automation: Vanta, Drata, Tugboat Logic, Secureframe
```

---

## Module 7.3: Security Program Management

### Section 7.3.1 — Building a Security Program
```
├── Security Strategy:
│   ├── Align with Business: Security enables business, Not blocks it
│   ├── Maturity Assessment: Where are we? Where do we need to be?
│   ├── Roadmap: Phased plan with milestones, Quick wins + Long-term
│   └── Metrics & KPIs: Measure progress, Report to board
├── Security Organization:
│   ├── CISO Role: Business alignment, Risk management, Strategy
│   ├── Team Structure: AppSec, InfraSec, SOC, GRC, IAM, Cloud Security
│   ├── Security Champions: Embedded in dev teams
│   └── Outsourcing: MSSP, MDR, Pen testing firms
├── Security Architecture Review:
│   ├── Threat Modeling: For every new project/major change
│   ├── Security Design Reviews: Architecture evaluation
│   ├── Secure by Default: Security baked into templates and standards
│   └── Architecture Decision Records: Document security decisions
├── Security Awareness:
│   ├── Training Programs: Annual training, Role-based training
│   ├── Phishing Simulations: Regular campaigns, Track metrics
│   ├── Security Culture: Make security everyone's responsibility
│   └── Metrics: Click rates, Report rates, Training completion
├── Budget & Resources:
│   ├── Security Budget: Typically 5-15% of IT budget
│   ├── Tool Rationalization: Avoid tool sprawl
│   ├── Build vs Buy: When to build custom, When to buy solutions
│   └── ROI Justification: Translate risk reduction to financial terms
└── Board & Executive Reporting:
    ├── Risk Dashboard: Top risks, Trends, Treatment status
    ├── Incident Metrics: MTTD, MTTR, Incident count by severity
    ├── Compliance Status: Audit findings, Remediation progress
    ├── Security Posture: Vulnerability trends, Patch compliance
    └── Benchmark: Compare against industry peers
```

---

> ### 🛠️ PHASE 7 PROJECT: **Security Program Design**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │           SECURITY PROGRAM DESIGN (For Fictional Company)       │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ SCENARIO: You're hired as CISO for a 500-person SaaS company   │
> │ handling healthcare data (HIPAA) with AWS infrastructure.       │
> │                                                                 │
> │ ✅ ASSESSMENT:                                                  │
> │    • Current state maturity assessment (NIST CSF)               │
> │    • Gap analysis: Where are we vs Where we need to be          │
> │    • Risk assessment: Top 20 risks with FAIR quantification     │
> │    • Third-party risk assessment of top 5 vendors               │
> │                                                                 │
> │ ✅ PROGRAM DESIGN:                                              │
> │    • Security organizational chart (10-person team)             │
> │    • 12-month security roadmap with milestones                  │
> │    • Annual security budget proposal ($2M) with justification   │
> │    • Tool selection: SIEM, EDR, IAM, CSPM, Vulnerability mgmt  │
> │                                                                 │
> │ ✅ POLICIES (write all):                                        │
> │    • Information Security Policy (master policy)                │
> │    • Acceptable Use Policy                                      │
> │    • Incident Response Plan                                     │
> │    • Data Classification Policy                                 │
> │    • Access Control Policy                                      │
> │    • Vendor Risk Management Policy                              │
> │    • Business Continuity / DR Plan                              │
> │                                                                 │
> │ ✅ COMPLIANCE:                                                  │
> │    • HIPAA compliance checklist (all safeguards)                 │
> │    • SOC 2 Type II readiness assessment                          │
> │    • Evidence collection guide for auditors                     │
> │    • Continuous compliance monitoring plan                      │
> │                                                                 │
> │ ✅ EXECUTIVE REPORTING:                                         │
> │    • Board-level security dashboard (1-page)                    │
> │    • Monthly security metrics report template                   │
> │    • Annual security posture presentation (20 slides)           │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 🔴 PHASE 8: ADVANCED & EMERGING THREATS
### 📅 Duration: Months 26–30+
### 🎯 Goal: Master cutting-edge security domains, Shape the future
### 👤 Level: Principal Security Architect / Distinguished Engineer
### 📜 Certifications: OSEE, GREM, SANS Masters, Custom research

---

## Module 8.1: AI/ML Security

### Section 8.1.1 — AI Threats & Defenses
```
├── AI-Powered Attacks:
│   ├── Deepfakes: Voice cloning, Video manipulation, Social engineering
│   ├── AI-Generated Phishing: ChatGPT-crafted emails (bypass detection)
│   ├── Automated Vulnerability Discovery: AI-powered fuzzing
│   ├── Password Cracking: Neural network-based password generation
│   └── Malware Generation: AI-assisted polymorphic malware
├── Adversarial Machine Learning:
│   ├── Evasion Attacks: Adversarial examples (fool classifiers)
│   ├── Poisoning Attacks: Corrupt training data
│   ├── Model Extraction: Steal ML models via API queries
│   ├── Data Extraction: Infer training data from model outputs
│   └── Prompt Injection: Manipulate LLM behavior via crafted inputs
├── LLM Security:
│   ├── Prompt Injection: Direct and indirect
│   ├── Jailbreaking: Bypass safety guardrails
│   ├── Data Leakage: Model memorization, PII extraction
│   ├── Supply Chain: Poisoned models, Malicious fine-tuning
│   └── OWASP Top 10 for LLMs: Emerging standard
├── AI in Defensive Security:
│   ├── Anomaly Detection: ML-based UEBA, Network anomaly detection
│   ├── Malware Classification: ML-powered AV/EDR
│   ├── Threat Intelligence: NLP for threat report analysis
│   ├── Automated Triage: AI-assisted alert prioritization
│   └── Predictive Security: Predict likely attack paths
└── Responsible AI Security:
    ├── Model Governance: Access controls, Versioning, Audit trails
    ├── Data Privacy: Federated learning, Differential privacy
    ├── Bias Detection: Fairness testing, Disparate impact analysis
    └── Red Teaming AI: Adversarial testing of ML models
```

---

## Module 8.2: Zero Trust Architecture (Deep Dive)

### Section 8.2.1 — Zero Trust Implementation
```
├── Core Principles:
│   ├── Never Trust, Always Verify: Every request authenticated/authorized
│   ├── Least Privilege: Minimum access for minimum time
│   ├── Assume Breach: Minimize blast radius, Segment everything
│   └── Verify Explicitly: User, Device, Location, Behavior — all factors
├── NIST SP 800-207: Zero Trust Architecture standard
├── Pillars:
│   ├── Identity: Strong authentication, Conditional access, Just-in-time
│   ├── Devices: Device health, Compliance, Managed vs Unmanaged
│   ├── Networks: Microsegmentation, Encrypted connections, SDP
│   ├── Applications: Per-app access, No VPN needed
│   ├── Data: Classification, Encryption, DLP, Rights management
│   └── Visibility: Logging, Analytics, Continuous monitoring
├── Technologies:
│   ├── SDP (Software-Defined Perimeter): Zscaler, Cloudflare Access
│   ├── BeyondCorp (Google): No corporate network, All access via proxy
│   ├── ZTNA (Zero Trust Network Access): Replace VPN
│   ├── SASE (Secure Access Service Edge): Network + Security in cloud
│   └── Microsegmentation: Illumio, Guardicore, VMware NSX
└── Implementation Roadmap:
    ├── Phase 1: Strong identity + MFA everywhere
    ├── Phase 2: Device trust and compliance
    ├── Phase 3: Microsegmentation of networks
    ├── Phase 4: Application-level access controls
    └── Phase 5: Data-centric security, Continuous validation
```

---

## Module 8.3: Supply Chain Security

### Section 8.3.1 — Software Supply Chain
```
├── Attack Surface:
│   ├── Dependencies: Malicious packages (typosquatting, maintainer compromise)
│   ├── Build Systems: CI/CD pipeline compromise, Poisoned builds
│   ├── Source Code: Compromised VCS, Insider threats
│   ├── Distribution: Tampered artifacts, Compromised registries
│   └── Runtime: Compromised containers, Malicious base images
├── Notable Incidents:
│   ├── SolarWinds (2020): Build system compromise, Nation-state
│   ├── Log4Shell (2021): Zero-day in ubiquitous library
│   ├── Codecov (2021): CI/CD bash uploader compromise
│   ├── ua-parser-js (2021): npm package hijack
│   └── 3CX (2023): Desktop app supply chain compromise
├── Defenses:
│   ├── SBOM (Software Bill of Materials): CycloneDX, SPDX formats
│   ├── Dependency Scanning: Snyk, Dependabot, npm audit, pip-audit
│   ├── Code Signing: Sign commits (GPG), Sign artifacts, Sign containers (Cosign)
│   ├── Build Provenance: SLSA framework (Supply chain Levels for Software Artifacts)
│   │   ├── Level 1: Documentation of build process
│   │   ├── Level 2: Tamper-resistant build service
│   │   ├── Level 3: Hardened, Auditable build platform
│   │   └── Level 4: Two-party review, Hermetic builds
│   ├── Reproducible Builds: Same source → Same binary (verifiable)
│   ├── In-Toto: Supply chain layout verification
│   ├── Sigstore: Keyless signing for software artifacts
│   └── Private Registries: Host your own npm, PyPI, Maven, Docker registry
└── Standards:
    ├── NIST SSDF: Secure Software Development Framework
    ├── OpenSSF Scorecard: Automated security health checks for OSS
    └── Executive Order 14028: US government software supply chain requirements
```

---

## Module 8.4: OT/ICS/SCADA Security

### Section 8.4.1 — Industrial Control Systems
```
├── ICS Components:
│   ├── PLC (Programmable Logic Controller): Controls physical processes
│   ├── RTU (Remote Terminal Unit): Field data acquisition
│   ├── HMI (Human-Machine Interface): Operator interface
│   ├── SCADA: Supervisory Control and Data Acquisition
│   ├── DCS (Distributed Control System): Large-scale process control
│   └── Historian: Stores operational data
├── Protocols:
│   ├── Modbus: Serial, No authentication (legacy)
│   ├── DNP3: Distributed Network Protocol (utilities)
│   ├── OPC UA: Modern, Encrypted, Authenticated
│   ├── BACnet: Building automation
│   └── EtherNet/IP: Industrial Ethernet
├── Threats:
│   ├── Stuxnet: First known ICS malware (Iranian centrifuges)
│   ├── Industroyer/CrashOverride: Ukrainian power grid attack
│   ├── TRITON/TRISIS: Safety system attack (SIS)
│   └── Colonial Pipeline: Ransomware → Operational shutdown
├── Security Challenges:
│   ├── Legacy Systems: 20+ year old systems, No patches available
│   ├── Availability > Confidentiality: Uptime is paramount
│   ├── Air-Gapped (sometimes): Bridged via USB, Remote access
│   ├── No Authentication: Many protocols have zero auth
│   └── Safety Critical: Failure can cause physical harm/death
├── Defenses:
│   ├── Purdue Model: Network segmentation (Enterprise → DMZ → Control → Field)
│   ├── ICS-specific IDS: Claroty, Dragos, Nozomi Networks
│   ├── Network Monitoring: Passive monitoring (can't actively scan!)
│   ├── NIST SP 800-82: Guide to ICS Security
│   └── IEC 62443: Industrial cybersecurity standard
└── Standards: NERC CIP (electric utilities), IEC 62443, ISA/IEC
```

---

## Module 8.5: Privacy Engineering & Cryptographic Engineering

### Section 8.5.1 — Advanced Privacy
```
├── Privacy by Design: 7 principles (Ann Cavoukian)
├── Privacy Enhancing Technologies (PETs):
│   ├── Differential Privacy: Add noise to queries (Apple, Google, US Census)
│   ├── Homomorphic Encryption: Compute on encrypted data (emerging)
│   ├── Secure Multi-Party Computation (MPC): Joint computation without sharing data
│   ├── Zero-Knowledge Proofs (ZKP): Prove statement without revealing data
│   ├── Federated Learning: Train ML without centralizing data
│   └── Confidential Computing: Process data in hardware enclaves (SGX, SEV)
├── Data Anonymization:
│   ├── K-Anonymity: Each record indistinguishable from K-1 others
│   ├── L-Diversity: Diverse values within equivalence classes
│   ├── T-Closeness: Distribution of sensitive attribute close to overall
│   └── Synthetic Data: Generate fake data with same statistical properties
└── Quantum Cryptography (Post-Quantum):
    ├── Threat: Quantum computers break RSA, ECC, DH
    ├── NIST PQC Standards: CRYSTALS-Kyber (encryption), CRYSTALS-Dilithium (signatures)
    ├── Lattice-Based Cryptography: Mathematical hardness problem
    ├── Hash-Based Signatures: SPHINCS+, XMSS
    ├── Migration Strategy: Crypto agility, Hybrid approaches
    └── Timeline: "Harvest now, Decrypt later" — Start preparing NOW
```

---

> ### 🛠️ PHASE 8 PROJECT: **Comprehensive Security Research Paper + Tooling**
> ```
> ┌─────────────────────────────────────────────────────────────────┐
> │      SECURITY RESEARCH & ADVANCED TOOL DEVELOPMENT              │
> ├─────────────────────────────────────────────────────────────────┤
> │                                                                 │
> │ Choose ONE specialization and deliver:                          │
> │                                                                 │
> │ OPTION A — AI Security:                                         │
> │  ✅ Build an LLM Red Teaming framework:                         │
> │     • Automated prompt injection testing                        │
> │     • Jailbreak detection and classification                    │
> │     • Data leakage measurement                                  │
> │     • Generate OWASP LLM Top 10 assessment report               │
> │  ✅ Write research paper on AI-powered attack detection          │
> │                                                                 │
> │ OPTION B — Supply Chain Security:                               │
> │  ✅ Build a supply chain security scanner:                       │
> │     • SBOM generation (CycloneDX format)                        │
> │     • Dependency vulnerability scanning                         │
> │     • License compliance checking                               │
> │     • Malicious package detection (typosquatting)               │
> │     • SLSA provenance verification                              │
> │  ✅ Publish as open-source tool                                  │
> │                                                                 │
> │ OPTION C — Zero Trust Implementation:                           │
> │  ✅ Design and implement a Zero Trust architecture:              │
> │     • Identity-based access (no VPN)                            │
> │     • Device trust scoring                                      │
> │     • Microsegmentation with Kubernetes Network Policies        │
> │     • Continuous authentication                                  │
> │     • Full NIST 800-207 compliance mapping                      │
> │  ✅ Document architecture with C4 diagrams + ADRs               │
> │                                                                 │
> │ OPTION D — ICS/OT Security:                                     │
> │  ✅ Build an ICS security monitoring lab:                        │
> │     • Simulate PLC/SCADA environment (GRFICSv2, OpenPLC)       │
> │     • Deploy passive network monitoring                         │
> │     • Detect Modbus/DNP3 anomalies                              │
> │     • Write detection rules for ICS-specific attacks            │
> │  ✅ ICS security assessment methodology document                │
> │                                                                 │
> │ ALL OPTIONS REQUIRE:                                            │
> │  📄 30+ page research paper / whitepaper                        │
> │  🎤 Conference-style presentation (30 minutes)                  │
> │  🛠️ Working tool or proof-of-concept (open-source)              │
> │  📋 Blog series (3-5 posts) documenting the journey             │
> └─────────────────────────────────────────────────────────────────┘
> ```

---
---
---

# 📚 COMPLETE READING & RESOURCE LIST

```
┌──────────┬───────────────────────────────────────────────────────────────────────┐
│  PHASE   │  BOOKS & RESOURCES                                                   │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 CompTIA Network+ Study Guide                                     │
│  PHASE 1 │  📖 The Linux Command Line — William Shotts (FREE)                   │
│          │  📖 Computer Networking: A Top-Down Approach — Kurose & Ross          │
│          │  🌐 TryHackMe: Pre-Security + Introduction to Cybersecurity paths    │
│          │  🌐 OverTheWire: Bandit (Linux CLI challenges)                        │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 CompTIA Security+ Get Certified Get Ahead — Darril Gibson         │
│  PHASE 2 │  📖 Serious Cryptography — Jean-Philippe Aumasson                     │
│          │  📖 Cryptography and Network Security — Stallings                     │
│          │  🌐 CryptoHack.org: Interactive cryptography challenges               │
│          │  🌐 PicoCTF: Beginner CTF platform                                    │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 The Web Application Hacker's Handbook — Stuttard & Pinto          │
│  PHASE 3 │  📖 Penetration Testing — Georgia Weidman                             │
│          │  📖 The Hacker Playbook 3 — Peter Kim                                 │
│          │  📖 Red Team Field Manual (RTFM) — Ben Clark                          │
│          │  📖 Active Directory Attacks — Nikhil Mittal / HackTricks             │
│          │  🌐 PortSwigger Web Security Academy (FREE)                           │
│          │  🌐 HackTheBox + TryHackMe (Offensive paths)                          │
│          │  🌐 VulnHub VMs                                                       │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 Blue Team Handbook: Incident Response — Don Murdoch               │
│  PHASE 4 │  📖 The Art of Memory Forensics — Ligh, Case, Levy, Walters          │
│          │  📖 Practical Malware Analysis — Sikorski & Honig                     │
│          │  📖 Intelligence-Driven Incident Response — Mooncake & Roberts        │
│          │  📖 Crafting the InfoSec Playbook — Bollinger, Enright, Valites       │
│          │  🌐 CyberDefenders: Blue team challenges                              │
│          │  🌐 LetsDefend: SOC analyst training                                  │
│          │  🌐 SANS DFIR Posters & Cheat Sheets                                  │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 Cloud Security and Privacy — Mather, Kumaraswamy, Latif           │
│  PHASE 5 │  📖 Hacking APIs — Corey Ball                                        │
│          │  📖 Kubernetes Security — Liz Rice                                    │
│          │  📖 Agile Application Security — Bell, Brunton-Spall, Smith           │
│          │  🌐 flaws.cloud / flaws2.cloud: AWS security challenges               │
│          │  🌐 CloudGoat: Intentionally vulnerable AWS environment               │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 Hacking: The Art of Exploitation (2nd ed) — Jon Erickson          │
│  PHASE 6 │  📖 Practical Reverse Engineering — Dang, Gazet, Bachaalany           │
│          │  📖 Red Team Development and Operations — Joe Vest                    │
│          │  📖 The Shellcoder's Handbook — Anley, Heasman, Lindner               │
│          │  🌐 pwn.college: Binary exploitation CTF                              │
│          │  🌐 Malware Traffic Analysis (malware-traffic-analysis.net)            │
│          │  🌐 SANS Cyber Ranges: NetWars, DFIR                                  │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 CISSP All-in-One Exam Guide — Shon Harris / Fernando Maymí        │
│  PHASE 7 │  📖 CISM Review Manual — ISACA                                       │
│          │  📖 Managing Risk and Information Security — Malcolm Harkins           │
│          │  📖 Navigating the Cybersecurity Career Path — Helen Patton            │
│          │  📖 The CISO Evolution — Matthew Sharp                                │
├──────────┼───────────────────────────────────────────────────────────────────────┤
│          │  📖 AI Security — Gary McGraw et al.                                  │
│  PHASE 8 │  📖 Sandworm — Andy Greenberg (ICS/Nation-state)                     │
│          │  📖 This Is How They Tell Me the World Ends — Nicole Perlroth         │
│          │  📖 Post-Quantum Cryptography — Bernstein, Buchmann, Dahmen           │
│          │  🌐 OWASP Top 10 for LLMs                                             │
│          │  🌐 MITRE ATT&CK for ICS                                              │
└──────────┴───────────────────────────────────────────────────────────────────────┘
```

---

# 🧭 COMPLETE VISUAL PROGRESSION MAP

```
╔═══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                       ║
║  PHASE 8 ━━ ADVANCED & EMERGING ━━━━━━━━━━━━━━━━━━━━━━━━ [Principal Security Arch.]  ║
║  ┃                                                                                    ║
║  ┣━ 8.1 AI/ML Security         (AI Attacks, Adversarial ML, LLM Security, AI Defense)║
║  ┣━ 8.2 Zero Trust Deep Dive   (NIST 800-207, SDP, SASE, ZTNA, Implementation)      ║
║  ┣━ 8.3 Supply Chain Security  (SBOM, SLSA, Sigstore, Reproducible Builds)           ║
║  ┣━ 8.4 OT/ICS/SCADA Security  (PLCs, Modbus, Purdue Model, IEC 62443)              ║
║  ┗━ 8.5 Privacy & Crypto Eng.  (PETs, Post-Quantum, ZKP, Homomorphic, MPC)          ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 7 ━━ GRC & LEADERSHIP ━━━━━━━━━━━━━━━━━━━━━━━━━━ [CISO / Director]           ║
║  ┃                                                                                    ║
║  ┣━ 7.1 Risk Management        (FAIR, NIST RMF, Risk Register, Third-Party Risk)    ║
║  ┣━ 7.2 Compliance             (ISO 27001, SOC 2, PCI DSS, GDPR, HIPAA, CMMC)       ║
║  ┗━ 7.3 Security Program       (Strategy, Budget, Metrics, Board Reporting, Culture) ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 6 ━━ ADVANCED OFFENSIVE ━━━━━━━━━━━━━━━━━━━━━━━━ [Sr Red Teamer / Researcher]║
║  ┃                                                                                    ║
║  ┣━ 6.1 Exploit Development    (Assembly, Buffer Overflow, ROP, Shellcode, Bypasses) ║
║  ┣━ 6.2 Reverse Engineering    (IDA/Ghidra, Anti-Analysis, Malware Internals)        ║
║  ┗━ 6.3 Red Team Operations    (C2, Evasion, OPSEC, APT Emulation, Purple Team)     ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 5 ━━ SPECIALIZED DOMAINS ━━━━━━━━━━━━━━━━━━━━━━━ [Security Engineer]          ║
║  ┃                                                                                    ║
║  ┣━ 5.1 Cloud Security          (AWS/Azure/GCP, IAM, Misconfigs, K8s, Container)     ║
║  ┣━ 5.2 Application Security    (SSDLC, DevSecOps, SAST/DAST/SCA, API Security)     ║
║  ┣━ 5.3 Identity & Access Mgmt  (Federation, PAM, Zero Trust Identity, Governance)   ║
║  ┗━ 5.4 Network Security Eng.   (NGFW, IDS/IPS, NAC, DLP, Email Sec, Deception)     ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 4 ━━ DEFENSIVE SECURITY (BLUE TEAM) ━━━━━━━━━━━━ [SOC Analyst / DFIR]        ║
║  ┃                                                                                    ║
║  ┣━ 4.1 SOC Operations          (SIEM/Splunk, Log Analysis, Detection Engineering,   ║
║  ┃                                Sigma/YARA Rules, Threat Intelligence)              ║
║  ┣━ 4.2 Incident Response        (NIST IR Lifecycle, Playbooks, Chain of Custody)    ║
║  ┃      & Digital Forensics      (Memory/Disk/Network/Cloud Forensics, Volatility)   ║
║  ┣━ 4.3 Threat Hunting           (Hypothesis-Driven, TTP Hunting, Baselining,        ║
║  ┃                                Beaconing Detection, LOLBin Hunting)               ║
║  ┗━ 4.4 Malware Analysis         (Static, Dynamic, Sandboxing, YARA, Reporting)      ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 3 ━━ OFFENSIVE SECURITY (RED TEAM) ━━━━━━━━━━━━━ [Penetration Tester]         ║
║  ┃                                                                                    ║
║  ┣━ 3.1 Reconnaissance           (OSINT, Active Scanning, nmap Mastery, Web/SMB/     ║
║  ┃                                 SNMP/LDAP Enumeration)                            ║
║  ┣━ 3.2 Web Application Attacks  (OWASP Top 10, SQLi, XSS, SSRF, CSRF, SSTI,        ║
║  ┃                                 Burp Suite, Deserialization)                      ║
║  ┣━ 3.3 Network & System Exploit (MitM, Password Attacks, Metasploit, Wireless,      ║
║  ┃                                 Linux/Windows PrivEsc, Post-Exploitation)         ║
║  ┗━ 3.4 Active Directory Attacks (BloodHound, Kerberoasting, Pass-the-Hash,          ║
║                                    DCSync, Golden Ticket, ADCS Attacks)              ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 2 ━━ SECURITY FUNDAMENTALS ━━━━━━━━━━━━━━━━━━━━━ [Jr Security Analyst]        ║
║  ┃                                                                                    ║
║  ┣━ 2.1 Core Concepts            (CIA Triad, Threat Landscape, Kill Chain, ATT&CK,   ║
║  ┃                                 Access Control Models, Security Principles)       ║
║  ┣━ 2.2 Cryptography             (Symmetric/Asymmetric, Hashing, PKI, TLS,           ║
║  ┃                                 Digital Signatures, Key Management)               ║
║  ┣━ 2.3 Security Operations      (Policies, Frameworks: NIST/ISO/CIS, Hardening,     ║
║  ┃                                 Vulnerability Management, CVSS/CVE)              ║
║  ┗━ 2.4 Security Tools           (nmap, Wireshark, Nessus, Hashcat, John, Hydra,     ║
║                                    Netcat, Burp Suite basics)                        ║
║      ▲                                                                                ║
║      ║                                                                                ║
║  PHASE 1 ━━ IT & NETWORKING FOUNDATIONS ━━━━━━━━━━━━━━━━ [Starting Point]             ║
║  ┃                                                                                    ║
║  ┣━ 1.1 Hardware & OS            (CPU/Memory/Storage, Windows Internals, AD,          ║
║  ┃                                 PowerShell, Linux Deep Dive, Bash, Permissions)   ║
║  ┣━ 1.2 Networking               (OSI/TCP-IP All Layers, Subnetting, Routing,         ║
║  ┃                                 Wireless, VPN, Wireshark, Packet Analysis)        ║
║  ┗━ 1.3 Virtualization & Lab     (Hypervisors, VM Networking, Kali, Security Onion,   ║
║                                    Practice Platforms: THM, HTB, PicoCTF)            ║
║                                                                                       ║
╚═══════════════════════════════════════════════════════════════════════════════════════╝

TOTAL: 8 Phases │ 27 Modules │ 80+ Sections │ 8 Milestone Projects │ 30+ Books
TIMELINE: ~30 months (adjust based on prior experience and specialization)
```

---

# 🗺️ CAREER PATH SPECIALIZATION MAP

```
                              ┌─────────────────────┐
                              │   FOUNDATIONS        │
                              │  (Phases 1-2)        │
                              └──────────┬──────────┘
                                         │
                          ┌──────────────┼──────────────┐
                          │              │              │
                    ┌─────┴─────┐  ┌─────┴─────┐  ┌────┴──────┐
                    │  OFFENSIVE │  │ DEFENSIVE  │  │ENGINEERING│
                    │  (Phase 3) │  │ (Phase 4)  │  │ (Phase 5) │
                    └─────┬─────┘  └─────┬─────┘  └────┬──────┘
                          │              │              │
              ┌───────────┤     ┌────────┤     ┌────────┤
              │           │     │        │     │        │
         ┌────┴────┐ ┌────┴──┐ │   ┌────┴──┐ │   ┌────┴────┐
         │  Pentest │ │ Red   │ │   │  SOC  │ │   │  Cloud  │
         │  (OSCP)  │ │ Team  │ │   │Analyst│ │   │Security │
         └─────────┘ │(CRTO) │ │   │(CySA+)│ │   │(AWS Sec)│
                     └───┬───┘ │   └───┬───┘ │   └────┬────┘
                         │     │       │     │        │
                    ┌────┴──┐  │  ┌────┴──┐  │   ┌────┴────┐
                    │Exploit│  │  │  DFIR  │  │   │  AppSec │
                    │  Dev  │  │  │(GCFE)  │  │   │ (OSWE)  │
                    │(OSEE) │  │  └───┬───┘  │   └─────────┘
                    └───────┘  │      │      │
                               │ ┌────┴──┐   │
                               │ │Threat │   │
                               │ │Hunter │   │
                               │ │(GCTI) │   │
                               │ └───────┘   │
                               │             │
                         ┌─────┴─────────────┴─────┐
                         │       LEADERSHIP          │
                         │     (Phases 6-7)          │
                         │   CISO / Director         │
                         │   (CISSP, CISM)           │
                         └───────────┬───────────────┘
                                     │
                         ┌───────────┴───────────┐
                         │     SPECIALIZATION     │
                         │      (Phase 8)         │
                         │  AI Sec │ OT/ICS │ ZT  │
                         │  Supply Chain │ Privacy│
                         └───────────────────────┘
```

---

# ⚡ GOLDEN RULES FOR THE CYBERSECURITY JOURNEY

```
┌─────┬──────────────────────────────────────────────────────────────────────────┐
│  #  │  RULE                                                                   │
├─────┼──────────────────────────────────────────────────────────────────────────┤
│  1  │  BUILD A LAB. Practice > Theory. Break things in YOUR lab, not others'. │
│  2  │  ALWAYS stay legal. Get written permission. Never test without auth.    │
│  3  │  Learn BOTH offense AND defense. The best defenders think like attackers.│
│  4  │  Document everything. Notes, Screenshots, Write-ups = Your portfolio.   │
│  5  │  CTFs are gym for hackers. Do them regularly (THM, HTB, PicoCTF).       │
│  6  │  Networking > Certifications. Join communities, Discord, Conferences.   │
│  7  │  Read CVEs weekly. Understand real vulnerabilities, not just theory.     │
│  8  │  Automate repetitive tasks. Python/Bash scripting is non-negotiable.    │
│  9  │  Teach what you learn. Blog, Present, Mentor — it deepens understanding.│
│ 10  │  Stay current. Follow: Krebs on Security, The Hacker News, SANS ISC,   │
│     │  DarkReading, Schneier on Security, Twitter/X security community.       │
│ 11  │  Ethics FIRST. With great power comes great responsibility.             │
│ 12  │  Never stop learning. Threats evolve daily. So must you.                │
└─────┴──────────────────────────────────────────────────────────────────────────┘
```

---

> *"The only truly secure system is one that is powered off, cast in a block of concrete, and sealed in a lead-lined room with armed guards — and even then, I have my doubts."* — Eugene Spafford
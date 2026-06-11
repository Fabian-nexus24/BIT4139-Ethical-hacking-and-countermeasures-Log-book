# Ethical Hacking & Countermeasures — Lab Logbook

> **Unit:** BIT4138 — Ethical Hacking and Countermeasures  
> **Course:** Bachelor of Science in Computer Science  
> **Semester / Year:** 2026  
> **Lecturer:** Michael Nyoro

---

## Overview

This repository contains the weekly lab logbook for the BIT4138 Ethical Hacking and Countermeasures unit. Each week covers a hands-on practical exercise using industry-standard security tools in a controlled, authorized lab environment. All scans and tests were conducted exclusively on local machines, local networks, or publicly available passive sources — never on unauthorized systems.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Primary OS | Kali Linux (running on VirtualBox) |
| Host OS | Windows 10 / 11 |
| Local Server | Laragon (Apache 2.4.54, PHP 8.1.10, MySQL 8.0.30) |
| Target App | Tsavo Water Delivery System (local PHP web app) |

---

## Weekly Topics

### Week 1 — Nmap Installation & Setup
- Installed Nmap from [nmap.org](https://nmap.org) on a Windows host
- Configured Zenmap (GUI) alongside the CLI version
- Set up Kali Linux as a virtual machine on VirtualBox

### Week 2 — Network Scanning with Nmap
- Performed a full port scan on localhost (Laragon server)
- Discovered open ports: `80/tcp` (Apache), `443/tcp` (HTTPS), `3306/tcp` (MySQL)
- Ran vulnerability detection using `nmap --script vuln 127.0.0.1`
- OS/service footprinting with `nmap -A 192.168.0.101`

### Week 3 — Advanced Nmap Scanning Techniques
- Targeted port scans on local network hosts
- OS version identification with `nmap -O`
- Service and version detection with `-sV`
- Vulnerability scanning using Nmap Scripting Engine (`--script vuln`)

### Week 4 — Passive OSINT Reconnaissance
- **Target:** Mount Kenya University (`mku.ac.ke`) — public domain, passive methods only
- **Tools used:**
  - KENIC WHOIS Lookup — domain & registrar information
  - MXToolbox — DNS record enumeration
  - Google Dorking — publicly accessible documents
  - crt.sh — certificate transparency & subdomain discovery
- No direct interaction with target systems

### Week 5 — Web Application Vulnerability Assessment
- **Target:** Tsavo Water Delivery System (locally hosted PHP application)
- **Tools used:**
  - `Nmap -sV` — network and service discovery
  - `Nikto` — web server vulnerability scanning
  - OWASP ZAP — web application assessment
- **Key findings:**
  - Outdated Apache, PHP, and OpenSSL versions
  - Missing HTTP security headers (CSP, HSTS, X-Content-Type-Options, etc.)
  - HTTP TRACE method enabled
  - PHP version disclosure via `X-Powered-By` header
  - Exposed phpMyAdmin interface

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| [Nmap](https://nmap.org) | Port scanning, OS detection, vulnerability scripting |
| [Zenmap](https://nmap.org/zenmap/) | GUI frontend for Nmap |
| [Nikto](https://github.com/sullo/nikto) | Web server vulnerability scanner |
| [OWASP ZAP](https://www.zaproxy.org/) | Web application security testing |
| [Kali Linux](https://www.kali.org/) | Penetration testing OS |
| [VirtualBox](https://www.virtualbox.org/) | Virtualization platform |
| [Laragon](https://laragon.org/) | Local development server (Apache/MySQL/PHP) |
| KENIC WHOIS | Domain registration lookup |
| MXToolbox | DNS record analysis |
| crt.sh | Certificate transparency search |
| Google Dorking | Passive public information gathering |

---

## Ethical Disclaimer

All activities documented in this logbook were performed strictly in compliance with ethical hacking principles:

- Scans were conducted **only on authorized systems** (personal machines and local networks)
- OSINT activities used **only publicly available sources** with no direct system interaction
- No systems were exploited, modified, or harmed in any exercise
- This work is intended purely for **educational purposes** as part of an accredited academic programme

---

## Repository Structure

```
├── docs/
│   └── ethical_hacking_Documentation.docx   # Full logbook with screenshots
├── README.md
```

---

## License

This project is submitted as academic coursework. All rights reserved. Do not reproduce or distribute without permission.

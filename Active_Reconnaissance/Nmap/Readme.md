# 🛰️ Nmap – Network Mapper

## 📚 Overview

**Nmap (Network Mapper)** is one of the most powerful and widely used open-source tools for network discovery, security auditing, and vulnerability assessment. Created by Gordon Lyon (aka Fyodor) in 1997, Nmap has become a fundamental tool in the arsenal of network administrators, ethical hackers, and penetration testers.

Official website: [https://nmap.org](https://nmap.org)

---

## 🕰️ History

- **Initial Release:** September 1997
- **Author:** Gordon Lyon (Fyodor)
- **License:** GNU GPL v2
- **Platforms:** Linux, Windows, macOS, and more

Nmap gained widespread popularity due to its flexibility, performance, and extensibility. It has been featured in numerous books, security courses, and even Hollywood movies.

---

## 🔧 How to Use

To see the help file and command options:

```bash
nmap --help

Scan a single IP:
nmap 192.168.1.1

Scan a range of IPs:
nmap 192.168.1.1-100

Scan an entire subnet:
nmap 192.168.1.0/24

Scan specific ports:
nmap -p 80,443,21 192.168.1.1

Service and version detection:
nmap -sV 192.168.1.1

OS Detection:
nmap -O 192.168.1.1

✨ Key Features
Host discovery – Identify live hosts in a network

Port scanning – Determine open ports and services

Service version detection – Identify versions of running services

Operating system detection – Guess the OS based on TCP/IP stack fingerprinting

Scriptable interaction (NSE) – Use powerful Nmap Scripting Engine for advanced scanning

Flexible output formats – XML, grepable, normal, and interactive

Firewall evasion techniques – Includes fragmentation, decoys, spoofing, etc.

 Nmap Scripting Engine (NSE)
Nmap's scripting engine allows users to write Lua scripts for:

Brute-force attacks

Vulnerability detection

Malware scanning

Network discovery

🔒 Legal Disclaimer
Use Nmap only on networks and systems you own or are authorized to test. Unauthorized scanning may be considered illegal in many jurisdictions.

📢 Final Notes
Nmap is a cornerstone of modern cybersecurity practices. From reconnaissance to exploitation, it lays the foundation for understanding a target's network landscape. Mastering Nmap is essential for anyone pursuing ethical hacking, penetration testing, or network administration.

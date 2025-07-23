# 📡 Hping3 – Advanced Packet Crafting & Active Reconnaissance Tool

## 🧠 What is Hping3?

**Hping3** is a powerful command-line tool used to craft and analyze custom TCP/IP packets. Unlike traditional ping tools, hping3 gives users complete control over network packets—making it ideal for **firewall testing**, **port scanning**, **TCP/IP stack analysis**, and **active reconnaissance** during penetration testing.

It's widely used by red teamers, penetration testers, and network administrators for **low-level testing** and **advanced information gathering**.

---

## 🚀 Why Use Hping3?

Hping3 allows you to:

- Craft custom TCP, UDP, ICMP, or raw IP packets.
- Test firewall and IDS/IPS behavior.
- Detect live hosts and open ports with specific flags.
- Analyze TCP sequence numbers.
- Estimate system uptime using TCP timestamps.
- Perform manual traceroute.
- Create **fragmented packets** to test how systems handle packet reassembly or to bypass basic intrusion detection systems.

---

## 🧪 Common Use Cases

| Purpose                      | Command Example                                                |
|------------------------------|----------------------------------------------------------------|
| SYN Port Scan                | `hping3 -S -p 80 <target>`                                     |
| ACK Firewall Scan            | `hping3 -A -p 80 <target>`                                     |
| ICMP Ping                    | `hping3 -1 <target>`                                           |
| Traceroute                   | `hping3 --traceroute -V -1 <target>`                          |
| TCP Timestamp (uptime)       | `hping3 --tcp-timestamp -S -p 80 <target>`                    |
| TCP Sequence Prediction      | `hping3 -Q -S -p 80 <target>`                                 |
| Fragmented Packet Test       | `hping3 -S -p 80 --frag <target>`                             |
| Spoofed IP Address           | `hping3 -S -a <fake-ip> -p 80 <target>`                       |

---

## 🛠️ Key Features

- 🔍 **Packet Crafting**: Full control over all TCP/IP header fields.
- 🚀 **Protocol Support**: TCP, UDP, ICMP, and raw IP packets.
- 🧨 **Fragmentation**: Send fragmented packets to test reassembly or evade detection.
- 🧬 **TCP Flags Manipulation**: SYN, ACK, FIN, RST, PSH, URG, XMAS (PUF), and custom combinations.
- 🧭 **Traceroute Functionality**: Built-in manual traceroute for hop-by-hop inspection.
- 🕒 **Uptime Detection**: Leverage TCP timestamps to estimate target's uptime.
- 🎯 **Firewall/IDS Testing**: Easily bypass or test rule sets.
- 🧠 **Custom Payloads**: Add data to packet bodies for deeper testing.

---

## 📘 Common Options & Flags

| Option               | Description                                      |
|----------------------|--------------------------------------------------|
| `-S`                | Send TCP SYN flag                                |
| `-A`                | Send TCP ACK flag                                |
| `-F`                | Send TCP FIN flag                                |
| `-1`                | ICMP mode                                        |
| `-p <port>`         | Destination port                                 |
| `--frag`            | Enable fragmentation                             |
| `--spoof <ip>`      | Spoof source IP address                          |
| `--tcp-timestamp`   | Get remote uptime using TCP timestamp            |
| `-Q`                | Display TCP sequence number                      |
| `--traceroute`      | Run traceroute mode                              |
| `-i u1000`          | Microsecond delay between packets (1ms here)     |
| `-c <count>`        | Number of packets to send                        |
| `-V`                | Verbose output                                   |

---

## ⚠️ Legal Disclaimer

**Use Hping3 only on systems you own or are authorized to test.** Unauthorized usage is illegal and unethical. Always follow responsible disclosure and red teaming practices.

---

## 🧷 Summary

Hping3 is an essential utility in every red teamer’s toolkit. It enables deep inspection and manipulation of network packets for a variety of testing, reconnaissance, and bypassing techniques. With support for **fragmentation**, **custom flags**, and **detailed TCP/IP control**, it is ideal for advanced scanning and security validation.

---

## 🧰 Tools Covered Alongside Hping3

- `Nmap` – Port scanning & OS detection
- `WhatWeb` – Web technology fingerprinting
- `BuiltWith` – Web tech enumeration (browser + web-based)

---

## 👨‍💻 Maintained by

*Cybersecurity Enthusiast | Open to Red Teaming & Pentesting Roles*

📬 Reach out on LinkedIn  
#CyberSecurity #Hping3 #RedTeam #PenetrationTesting #Reconnaissance #ActiveRecon #InfoSec #PacketCrafting

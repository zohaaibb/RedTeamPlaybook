# 🛠️ Sniffers for Network and Protocol Analysis

## 🔍 Overview

A **network sniffer**—also known as a **packet analyzer**, **protocol analyzer**, or **network traffic analyzer**—is a tool used to **intercept and analyze network traffic**. These sniffers are essential in fields like cybersecurity, network engineering, digital forensics, and ethical hacking.

They allow professionals (and attackers) to examine raw data traveling across a network. For example, if an application sends credentials in **unencrypted** form, they could be easily captured using a sniffer. While such insecure behavior is rare today, sniffers remain invaluable for other reasons.

---

## 👨‍💻 Who Uses Sniffers?

- **Network Engineers** – To troubleshoot and monitor network traffic.
- **Security Analysts** – To detect potential intrusions or vulnerabilities.
- **Digital Forensic Investigators** – To trace actions during incident response.
- **Hackers** – To intercept and analyze sensitive data, especially during attacks like MiTM or DNS spoofing.

---

## 🎯 Why Are Sniffers Important?

Even if passwords are encrypted, sniffers can help attackers or defenders:

- Monitor **websites visited**
- Capture **cookies**, **user agents**
- Intercept **emails** (if unencrypted or weakly protected)
- Analyze traffic to perform or prevent:
  - **MiTM attacks**
  - **DNS spoofing**
  - **Session hijacking**
  - **Exploitation** (e.g., EternalBlue)

---

## 🛠 Common Sniffer Tools

| Tool Name | Description |
|-----------|-------------|
| **Wireshark** | Industry-standard GUI packet analyzer. Deep inspection capabilities. |
| **Tcpdump** | CLI-based packet analyzer for Unix/Linux systems. Powerful and lightweight. |
| **Tshark** | CLI version of Wireshark for headless environments. |
| **Windump** | Windows version of Tcpdump. |
| **SolarWinds DPI Tool** | Commercial tool with advanced DPI and analytics features. |
| **Network Miner** | Passive forensic analysis tool; reconstructs transferred files and sessions. |
| **Capsa** | Visual, user-friendly network monitoring and troubleshooting tool. |

---

## 🧠 Case Study: EternalBlue & Wireshark

Wireshark can be used to analyze advanced exploits like the NSA's **EternalBlue**, allowing professionals to understand how malicious payloads travel across the network at the **packet level** and identify tell-tale indicators of compromise.

---

## ⚙️ Prerequisites to Sniffing

To use sniffers effectively, the following system-level configurations must be met:

### 1. 🧲 Promiscuous Mode (NIC Requirement)
- **Normal NIC behavior**: Captures only packets addressed to its MAC.
- **Promiscuous mode**: NIC captures **all packets** on the local network segment, regardless of destination.
  
Enable this mode to fully monitor traffic on your LAN.

### 2. 📦 Packet Capture Format – `.pcap`
- All captured data is saved in **`.pcap`** files (Packet Capture format).
- These files allow for later inspection using tools like Wireshark or Tcpdump.

### 3. 📚 Required Libraries

| Operating System | Packet Capture Library |
|------------------|------------------------|
| **Linux**        | `libpcap`              |
| **Windows**      | `WinPcap` or `Npcap`   |

These libraries provide the backend functionality to read and write packets in `.pcap` format.

---

## ✅ Quick Checklist Before Sniffing

- [ ] Enable **promiscuous mode** on NIC
- [ ] Install **libpcap** or **Npcap**
- [ ] Use tools like **Wireshark** or **Tcpdump**
- [ ] Know your **legal boundaries** – sniffing unauthorized traffic may be illegal!

---

## 🧪 Example Commands

Enable promiscuous mode (Linux):

```bash
sudo ifconfig eth0 promisc
```

Capture packets with Tcpdump:

```bash
sudo tcpdump -i eth0 -w capture.pcap
```

Open capture in Wireshark:

```bash
wireshark capture.pcap
```

---

## ⚠️ Disclaimer

> Network sniffing should only be performed in **authorized environments** and for **educational, ethical, or professional purposes**. Unauthorized sniffing may violate laws and privacy policies.

---

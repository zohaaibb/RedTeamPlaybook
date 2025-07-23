# 🕵️‍♂️ p0f – Passive Operating System Detection

## 🧠 What is p0f?

**p0f** (Passive OS Fingerprinting) is a stealthy reconnaissance tool that identifies a target’s **operating system**, **network link type**, and **uptime** by **passively analyzing network packets**. It doesn’t send any traffic to the target—making it ideal for staying under the radar during reconnaissance.

Developed by **Michal Zalewski**, p0f is widely used in penetration testing to gain insights about systems without generating alerts.

---

## 🚦 Why Use p0f?

- ✅ **Completely passive** – no probes or active scans
- ✅ **Stealthy** – hard to detect
- ✅ **OS fingerprinting down to version/service pack level**
- ✅ **Determines system uptime**
- ✅ **Detects link type (Ethernet, modem, etc.)**
- ❌ Requires pre-existing traffic
- ❌ May struggle with encrypted/obfuscated traffic

---

## 🧪 How Does It Work?

Every OS implements TCP/IP stacks slightly differently. These differences appear in the structure of packets they send. p0f watches for:

| Field | Description |
|-------|-------------|
| **TOS (Type of Service)** | Packet priority (delay, throughput, reliability) |
| **TTL (Time to Live)** | Default hop count varies by OS (Windows: 32, Linux: 64) |
| **DF (Don't Fragment)** | Controls IP fragmentation behavior |
| **Window Size** | TCP buffer size, often unique to each OS |

By matching these values to a built-in **database of over 320+ signatures**, p0f identifies:

- OS type and version (e.g., Windows 7 SP1)
- Network link type (Ethernet, modem)
- MTU size (e.g., 1500 bytes)
- Uptime of the system

---

## 🔧 Installation

p0f comes **pre-installed** in **Kali Linux**.

> 🔍 It's a command-line tool, not found in the GUI.

Check if installed:

```bash
which p0f

Display Help Menu
p0f -h

Start Passive OS Detection on an Interface (e.g., eth0)
sudo p0f -i eth0

When p0f sees traffic, it outputs something like:
[+] 192.168.1.10:54321 -> 192.168.1.5:80 [SYN]
    OS: Windows 7 or 8
    Link: ethernet/modem
    MTU: 1500
    Uptime: 6 days, 16 hrs, 16 min
SYN indicates TCP handshake

OS is guessed from TCP/IP header fields

Link type (Ethernet/modem)

MTU helps deduce the connection type

Uptime shows how long the system has been active

⚡ Uptime is crucial: It can reveal if the system hasn’t been rebooted recently,meaning critical patches may not have been applied!

🧠 Technical Insight: Signature Matching
Upon startup, p0f:

Loads 320+ fingerprint signatures from its database

Listens on a specified interface (e.g., eth0)

Enters a loop, decoding live packets

Matches header patterns against known OS fingerprints

Outputs details such as:

IP address

Port number

TCP flags (SYN)

OS guess

MTU

Link type

Uptime


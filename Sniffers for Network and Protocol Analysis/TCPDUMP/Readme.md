# 🧪 Tcpdump in Action

## 📌 Overview

`Tcpdump` is a powerful command-line network sniffer and packet analyzer for Unix/Linux systems. Introduced in 1988, it remains an essential tool for capturing and inspecting network traffic, especially in headless or remote systems where GUI-based tools like Wireshark are inefficient.

---

## ▶️ Starting Tcpdump

To begin capturing packets:

```bash
sudo tcpdump
```

Once started, packets will begin flowing in the terminal. These are typically interactions between your machine and the LAN gateway.

---

## 🧪 Generate Sample Traffic

Open two terminals:

1. In **Terminal 1**, start capturing with:

```bash
sudo tcpdump
```

2. In **Terminal 2**, ping a target device:

```bash
ping 192.168.0.114
```

You will observe **ICMP Echo Requests and Echo Replies** in Tcpdump's output.

---

## 💾 Save Output to a File

To save captured packets for later analysis:

```bash
sudo tcpdump -w myoutput.cap
```

---

## 🔍 Filtering Traffic

Tcpdump supports **Berkeley Packet Filter (BPF)** syntax for precise packet filtering.

### 🔸 Filter by Host IP

```bash
sudo tcpdump host 192.168.0.114
```

### 🔸 Filter by Source or Destination

```bash
sudo tcpdump src host 192.168.0.114
sudo tcpdump dst host 192.168.0.114
```

---

## 🌐 Apache Web Server Example

Start Apache server on Kali Linux:

```bash
sudo systemctl start apache2
```

Then capture traffic:

```bash
sudo tcpdump host 192.168.0.114
```

Open a browser on Windows 7 and access Kali’s IP. You'll observe the **TCP 3-way handshake**:
- `S` = SYN
- `S.` = SYN/ACK
- `.` = ACK

---

## 🔢 Filter by Port

Capture only HTTP (port 80) traffic:

```bash
sudo tcpdump port 80
```

Verbose output for deeper inspection:

```bash
sudo tcpdump -vv port 80
```

---

## 🚩 Filter by TCP Flags

Examples:

```bash
sudo tcpdump 'tcp[tcpflags] == tcp-ack'
sudo tcpdump 'tcp[tcpflags] == tcp-fin'
sudo tcpdump 'tcp[tcpflags] == tcp-rst'
sudo tcpdump 'tcp[tcpflags] == tcp-psh'
sudo tcpdump 'tcp[tcpflags] == tcp-urg'
```

---

## 🔗 Combining Filters

You can combine filters using logical operators:

### ✅ Logical AND (`and` / `&&`)
```bash
sudo tcpdump host 192.168.0.114 and port 80
```

### ✅ Logical OR (`or` / `||`)
```bash
sudo tcpdump port 80 or port 443
```

### ❌ Negation (`!` or `not`)
```bash
sudo tcpdump not host 192.168.0.114
```

---

## 🔐 Filtering for Passwords & Sensitive Data

You can combine port filters with `egrep` to search for password-related strings in plain-text protocols:

```bash
sudo tcpdump port 80 or port 21 or port 25 or port 110 or port 143 or port 23 -lA | \
egrep -i 'pass=|pwd=|log=|login=|user=|username=|pw=|passw=|password='
```

> ⚠️ Note: Only works if credentials are sent in **cleartext**.

---

## 🧾 Extracting User-Agent Strings

To view browser user-agent headers (common in HTTP requests):

```bash
sudo tcpdump -vvAls 0 | grep 'User-Agent'
```

- `-A`: Print each packet in ASCII
- `-l`: Make stdout line-buffered
- `-s 0`: Capture entire packet (not truncated)

---

## ✅ Summary Table

| Use Case                        | Tcpdump Command Example                                           |
|---------------------------------|-------------------------------------------------------------------|
| Basic capture                   | `tcpdump`                                                        |
| Save capture                    | `tcpdump -w myoutput.cap`                                       |
| Filter by IP                    | `tcpdump host 192.168.0.114`                                     |
| Filter by port                  | `tcpdump port 80`                                               |
| Combined IP and port            | `tcpdump host 192.168.0.114 and port 80`                         |
| Exclude specific host           | `tcpdump not host 192.168.0.114`                                 |
| Multiple ports (HTTP + HTTPS)  | `tcpdump port 80 or port 443`                                   |
| Extract cleartext passwords     | See password filtering command above                             |
| Extract user-agent info         | `tcpdump -vvAls 0 | grep 'User-Agent'`                           |

---

## ⚠️ Disclaimer

> Tcpdump should only be used in networks where you have explicit permission to monitor traffic. Unauthorized use may violate privacy laws and organizational policies.

---

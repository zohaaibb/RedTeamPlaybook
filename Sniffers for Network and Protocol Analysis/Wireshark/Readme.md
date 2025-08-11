# Wireshark Usage Guide

Wireshark has become the de-facto standard in network sniffers. Formerly known as **Ethereal**, it is now part of every network or security administrator’s toolkit. Kali Linux has Wireshark built-in, so you can start it via the terminal or GUI.

---

## Starting Wireshark

### Via Terminal
```bash
wireshark
```

### Via GUI
```
Applications -> Usual Applications -> Internet -> Wireshark
```

When opened, Wireshark will prompt you to choose a network interface:

- **VM Users:** Select `eth0`
- **Physical Machine with Wi-Fi:** Select `wlan0`
- Use the adapter with the highest activity for best results.

---

## Packet Capturing

Wireshark captures packets and saves them in `.pcap` format.  
`.pcap` is the industry standard used by tools like **Snort**, **aircrack-ng**, and more.

---

## Wireshark Interface Layout

- **Packet List Pane** – Displays real-time, color-coded packet data.

---

## Creating Filters in Wireshark

Since packet flow can be overwhelming, use filters to focus your analysis.

### Protocol Filters
To capture only TCP traffic:
```plaintext
tcp
```
Similarly, you can filter for:
```plaintext
http
smtp
udp
dns
```

### IP Address Filters
To see traffic from/to a specific IP:
```plaintext
ip.addr == 192.168.1.107
```

### Port Filters
To filter only TCP traffic for port 80:
```plaintext
tcp.dstport == 80
```

---

## Using the Expression Window

If unsure about filter syntax:
1. Click **Expression** on the right of the filter bar.
2. Select the field and operator from the list.

---

## Following Streams

Following streams allows you to track a complete conversation between hosts.

1. Right-click a packet from the desired connection.
2. Select **Follow -> TCP Stream** (or appropriate protocol).

This is useful for investigating suspicious or targeted communication.

---

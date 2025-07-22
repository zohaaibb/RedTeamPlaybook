# 🕵️ Passive Reconnaissance

## 📌 What is Reconnaissance?

Reconnaissance is the **first phase of ethical hacking or penetration testing**, where the goal is to gather as much information as possible about a target system, network, or organization. It helps attackers or ethical hackers understand the target’s infrastructure, detect potential weaknesses, and plan their approach.

Reconnaissance is divided into two main categories:

- **Passive Reconnaissance**: Gathering data **without directly interacting** with the target. This helps avoid detection.
- **Active Reconnaissance**: Involves direct interaction (e.g., scanning ports) and is more likely to be detected.

---

## 🧠 What is Passive Reconnaissance?

Passive reconnaissance focuses on collecting information **without alerting the target** or touching their systems. It uses **publicly available sources** such as domain records, search engines, open databases, and third-party services.

This helps build an intelligence profile without leaving fingerprints on the target's servers.

---

## 🛠️ Tools We Will Be Using

Below are the tools and techniques we’ll explore in this phase, including short explanations, example commands, and sample screenshots you can add later.

---

### 🔎 1. Google Dorking

**Description**: Google Dorking uses advanced search queries to find sensitive data indexed by search engines (e.g., login pages, exposed files, or admin panels).


🌐 2. Netcraft
Description: Netcraft gives detailed reports about domains, including:

Hosting provider

Server technologies

SSL certificate details

Site history

Use: Map the tech stack and infrastructure of a website.

Screenshot Placeholder:

🌍 3. Shodan
Description: Shodan is a search engine for internet-connected devices like webcams, routers, and exposed web servers.

Example Search:

nginx

apache port:80 country:"PK"
Use: Discover public services, device banners, and vulnerabilities.

Screenshot Placeholder:

🗂️ 4. Whois
Command:


whois example.com
Use: Retrieves domain registration info such as:

Registrar

Contact info

Creation/expiry dates

Name servers

🌐 5. DNS Tools: dig, nslookup, dnsenum
🔹 dig

dig example.com any
🔹 nslookup

nslookup example.com
🔹 dnsenum
dnsenum example.com
Use: Gather DNS records, mail servers, subdomains, and name server info.

Screenshot Placeholder:

🧠 6. p0f (Passive OS Fingerprinting)
Command:


sudo p0f -i eth0
Use: Sniffs network traffic to determine the OS, uptime, and system characteristics without actively scanning.

🧠 7. IP and TCP Basics
Before diving into advanced tools, it's important to understand how the internet works at the basic level:

IP Addressing: Identifying systems on a network

TCP/UDP Ports: Services running on machines

Protocols: How systems communicate (e.g., HTTP, DNS, FTP)

Packet Structure: Helpful for interpreting recon data

We’ll briefly touch on these to understand what the tools are showing you under the hood.


⚠️ Legal Disclaimer
This repository is created for educational purposes only.
Do not perform reconnaissance or scanning on systems you do not own or lack explicit permission to analyze.
Unauthorized scanning or data collection may be illegal and unethical.

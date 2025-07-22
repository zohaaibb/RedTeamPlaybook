# 🌐 Netcraft - Website Reconnaissance Tool

## 📌 What is Netcraft?

[Netcraft](https://www.netcraft.com/) is a **passive reconnaissance tool** used to gather intelligence on websites without touching the target server directly. It provides publicly available data such as:

- Web technologies (server type, CMS, frameworks)
- Hosting providers and IP addresses
- SSL certificate details
- Site uptime and historical changes
- DNS records and site network structure

This makes Netcraft an excellent tool for mapping a target’s infrastructure quietly and legally.

---

## 🧠 Why Use Netcraft in Passive Recon?

Netcraft helps ethical hackers and penetration testers to:

- Identify the web server and technology stack
- Understand DNS setup and hosting changes
- Spot potential legacy tech or unpatched components
- Correlate infrastructure used across multiple domains
- Build a passive footprint without triggering detection

---

## 🚀 How to Use Netcraft for Recon

### 🔗 Step 1: Visit the Site Report Page

- Navigate to:  
  [https://sitereport.netcraft.com/](https://sitereport.netcraft.com/)

- Enter your target domain (e.g., `example.com`) in the search bar.

### 🧾 Step 2: Review the Data

You’ll get insights like:

- **Hosting History**: See if the IP or provider has changed over time.
- **SSL Certificate Info**: Get issuer, expiration, and common names.
- **Web Technologies**: Server type, CMS, scripting languages, etc.
- **Risk Rating**: Overview of potential threats tied to the domain.
- **Site Network**: View IP addresses and DNS associations.

### 🖼️ Screenshot Example:

_Add a screenshot of a Netcraft Site Report page here:_

![Netcraft Report](../screenshots/netcraft_report.png)

---

## 🧠 What to Look For

| Information        | Why It’s Useful                            |
|--------------------|--------------------------------------------|
| Server Technology  | Can reveal outdated or vulnerable software |
| SSL Certificate    | Shows common names, expiration, misuse     |
| Hosting Provider   | Useful for pivoting to other hosted sites  |
| Historical Changes | Detect infrastructure migration            |
| DNS Records        | Map the network structure                  |

---

## ⚠️ Legal Disclaimer

All data gathered through Netcraft is **publicly accessible** and **legal** to use for educational or authorized security testing purposes.  
**Never perform analysis on targets without permission.**

---

## ✅ Next Steps

After collecting server and infrastructure data via Netcraft, continue with:

- Whois and DNS recon
- Subdomain enumeration
- Active scanning (only in safe/lab environments)

Stay stealthy, stay legal. 🕵️‍♂️

# 📡 DNS Enumeration – Passive Reconnaissance

## 📘 What is DNS?

**DNS (Domain Name System)** is the phonebook of the internet. It translates human-readable domain names like `microsoft.com` into IP addresses so browsers can load websites. Attackers or security professionals can query DNS records to gather valuable information about a target.

---

## 🛠 Tools We Will Use

- `dig` (Domain Information Groper) – Unix/Linux-based DNS query tool.
- `nslookup` – DNS query tool available on both Windows and Linux.
- Online DNS tools (for non-terminal users)

---

## 🔍 Common DNS Record Types

| Record Type | Description                       |
|-------------|-----------------------------------|
| A           | IPv4 address                      |
| AAAA        | IPv6 address                      |
| MX          | Mail Exchange (email servers)     |
| NS          | Name Server                       |
| TXT         | Human-readable text data          |
| SOA         | Start of Authority record         |
| CNAME       | Canonical name (alias)            |

---

## 🔧 DNS Enumeration with `dig`

### 🔹 Find Nameservers of a Domain

```bash
dig microsoft.com ns

Find Mail Servers (MX Records)
dig microsoft.com mx

Perform Zone Transfer (AXFR)
dig @75.75.75.75 microsoft.com axfr
@75.75.75.75: DNS server to query

axfr: Command for attempting a full zone transfer

⚠️ Zone Transfers are generally blocked and only work on misconfigured DNS servers.

 Zone Transfers Explained
A Zone Transfer (AXFR) is used between DNS servers to replicate DNS records. Attackers exploit open zone transfers to dump entire DNS databases—revealing all subdomains and IPs.

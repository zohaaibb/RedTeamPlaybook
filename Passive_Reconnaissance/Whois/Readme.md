# 📄 Whois - Domain Registration Information Gathering

## 📌 What is Whois?

Whenever a domain is registered, the domain owner must provide key details such as:

- Registrar and Nameservers
- Organization or Contact Name
- Physical Address
- Phone Number
- Email Address

This data is stored in **registrar databases** and made publicly accessible through the **Whois protocol** (typically on **port 43**).

Whois lookups are an essential part of **passive reconnaissance** — helping gather initial information about the target without direct interaction.

---

## 🎯 Why Use Whois in Reconnaissance?

Whois data can reveal:

- Real identities or organizations behind a domain
- Contact info for social engineering attempts
- Domain creation and expiry dates
- Nameservers and hosting providers
- Associated infrastructure or subdomains

---

## 💻 How to Use Whois

### 🔸 On Linux/Kali (Built-in Command)

```bash
whois facebook.com

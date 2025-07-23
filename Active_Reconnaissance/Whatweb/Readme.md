# 🌐 WhatWeb – Web Technology Fingerprinting Tool

## 🧠 What is WhatWeb?

**WhatWeb** is an open-source web scanner that identifies technologies used by websites. It helps security professionals, penetration testers, and bug bounty hunters understand the components of a web application—like the **web server**, **CMS**, **JavaScript libraries**, **analytics tools**, **frameworks**, and more—by matching signatures against a large plugin database.

WhatWeb supports **over 1700 plugins**, enabling fingerprinting of thousands of web technologies including **WordPress**, **Joomla**, **Apache**, **nginx**, **Cloudflare**, **Google Analytics**, and **many others**.

---

## 🚀 Why Use WhatWeb?

Before you can exploit a web application, you must know what it's running on. WhatWeb helps identify:

- CMS platforms (e.g., WordPress, Joomla)
- Web servers (e.g., Apache, Nginx, IIS)
- JavaScript libraries (e.g., jQuery, React)
- Hosting providers (e.g., Amazon AWS, Cloudflare)
- Analytics tools (e.g., Google Analytics, Hotjar)
- Frameworks (e.g., Laravel, ASP.NET)
- Plugins, themes, and version numbers
- SQL errors and potential misconfigurations

This information is crucial for building a targeted attack strategy and selecting the right exploits.

---

## 🔧 Basic Syntax

```bash
whatweb <target>
```

### 🔍 Examples

| Purpose                       | Command Example                                   |
|-------------------------------|---------------------------------------------------|
| Basic scan                   | `whatweb example.com`                             |
| Verbose output               | `whatweb -v example.com`                          |
| Aggressive mode              | `whatweb -a 3 example.com`                        |
| Scan multiple URLs           | `whatweb -i urls.txt`                             |
| Enable color output          | `whatweb --colour example.com`                    |
| Output in JSON               | `whatweb -a 3 -t 10 -v --log-json=result.json example.com` |
| Use proxy                    | `whatweb --proxy 127.0.0.1:8080 example.com`      |

---

## 🔐 Modes of Aggression

`-a` defines the level of aggression in scanning (0–3):

- `0` – Passive: Doesn’t make HTTP requests  
- `1` – Default: Makes a basic request and analyses the response  
- `2` – More extensive checks including 404 and regex  
- `3` – Most aggressive: sends extra requests, follows redirects, etc.

---

## 🛠️ Key Features

- 🔍 **Technology Detection**: Identify CMS, web servers, JS libraries, and more  
- 📊 **Version Detection**: Extract versions of plugins and services  
- 🌐 **Multiple Output Formats**: Support for JSON, CSV, XML, grepable output  
- 🧠 **Plugin Architecture**: Over 1700 plugins and easily extendable  
- 📁 **Batch Scanning**: Scan a list of domains or URLs from a file  
- 🛡️ **Proxy Support**: Can use HTTP or SOCKS proxies  
- 🚀 **Aggression Levels**: Customize how stealthy or thorough your scan is  

---

## 📁 Installation (on Kali/Linux)

```bash
sudo apt install whatweb
```

Or clone from GitHub:

```bash
git clone https://github.com/urbanadventurer/WhatWeb.git
cd WhatWeb
ruby whatweb example.com
```

(Note: WhatWeb is written in Ruby.)

---

## 📌 Use Case in Reconnaissance Workflow

✅ Start with **passive recon** (e.g., WHOIS, DNSdumpster)  
✅ Move to **active recon** using tools like `nmap`, `hping3`, and `whatweb`  
✅ Determine web technologies  
✅ Lookup known vulnerabilities for discovered versions  
✅ Build custom exploitation plan  

---

## ⚠️ Legal Disclaimer

**Use WhatWeb only on domains you own or have permission to scan.** Unauthorized scanning may be illegal or against terms of service.

---

## 👨‍💻 Maintained by

*Cybersecurity Enthusiast | Open to Red Teaming & Pentesting Roles*

📬 Reach out on LinkedIn  
#WhatWeb #Reconnaissance #WebTechFingerprinting #CyberSecurity #BugBounty #RedTeam #InfoSec #ActiveRecon #WebEnumeration

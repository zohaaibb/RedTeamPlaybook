# 🌐 Shodan (Web Interface) - Passive Reconnaissance Tool

## 📌 What is Shodan?

**Shodan** (Sentient Hyper-Optimized Data Access Network) is a powerful search engine used to discover internet-connected devices and services. Unlike traditional search engines like Google which index web pages, Shodan indexes metadata from devices such as servers, routers, IoT devices, webcams, and more.

Shodan is widely used by security professionals, red teamers, researchers, and attackers to gather **passive reconnaissance** data.

---

## 🕵️‍♂️ What Can You Discover with Shodan?

- Open ports and services
- Webcams, printers, routers, and ICS/SCADA systems
- Running software, versions, and OS banners
- Misconfigured databases (MongoDB, Elasticsearch, etc.)
- SSL certificate info and vulnerabilities
- Device geolocation and organization info

---

## 🔑 Getting Started

1. Go to [https://www.shodan.io](https://www.shodan.io)
2. Create an account (free or paid for more results)
3. Start searching with filters or simple queries

---

## 🔎 Useful Web Search Queries

### 🔹 Basic Searches

- `nginx` – Find web servers running nginx  
- `apache` – Search for Apache servers  
- `ftp` – Discover FTP servers  

### 🔹 Filters You Can Use

| Filter         | Description                            | Example                              |
|----------------|----------------------------------------|--------------------------------------|
| `country:`     | Two-letter country code                | `nginx country:PK`                   |
| `org:`         | Organization name                      | `ssh org:"Google"`                   |
| `port:`        | Specific open port                     | `port:21`                            |
| `os:`          | Operating system                       | `os:"Windows 7"`                     |
| `product:`     | Specific software/service              | `product:"MongoDB"`                  |
| `city:`        | City name                              | `city:"Karachi"`                     |
| `hostname:`    | Match subdomain or domain              | `hostname:"gov.pk"`                  |
| `before/after:`| Date filter (indexing)                 | `before:2023-01-01`                  |

---

## 🧪 Real-World Web Examples

### 🔸 Find Open Cameras

```text
"webcamXP" country:PK



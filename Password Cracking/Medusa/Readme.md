# 🐍 Medusa - Fast, Parallel, Online Password Cracking Tool

**Medusa** is a speedy, parallel, and modular **online password brute-forcer**. It supports multiple protocols and services and is commonly used in penetration testing for testing weak login credentials on live services.

---

## 📌 What is Medusa?

Medusa is a command-line tool designed to perform **online brute-force attacks** against various authentication services. Unlike offline cracking tools like John or Hashcat, Medusa interacts directly with the live target system to test username and password combinations.

It is modular, meaning each supported protocol is implemented as a module, allowing for easy extension.

---

## 🎯 Why Use Medusa?

🔹 Medusa is ideal for:

- Brute-forcing **remote services** (SSH, FTP, HTTP, SMB, RDP, etc.)
- Parallel testing for **high speed**
- Handling multiple usernames, passwords, and hosts simultaneously
- Red team engagements, CTFs, and credential testing

---

## 💡 Key Features

- Supports many services (over 15 modules)
- Fast and highly parallelized
- Username, password, and host list support
- Flexible and scriptable
- Optional SSL support
- Resume feature for interrupted sessions

---

## 🛠️ Installation (Kali Linux)

Medusa is pre-installed on Kali. If not:

```bash
sudo apt update
sudo apt install medusa
```

---

## 📂 Supported Protocol Modules

Medusa supports the following services (and more):

- `ssh` (port 22)
- `ftp`
- `http`, `https`, `http-form`
- `rdp`
- `telnet`
- `vnc`
- `smb`
- `mssql`, `mysql`, `postgres`
- `rexec`, `rlogin`, `rsh`
- `ncp`
- `snmp`

---

## 🔧 Basic Syntax

```bash
medusa -h <target> -u <username> -P <passwordlist> -M <module>
```

---

## 📌 Example Usages

### 🔹 Brute-force SSH login on a target:

```bash
medusa -h 192.168.1.100 -u root -P /usr/share/wordlists/rockyou.txt -M ssh
```

### 🔹 Use a list of usernames and passwords:

```bash
medusa -h 192.168.1.100 -U usernames.txt -P passwords.txt -M ssh
```

### 🔹 Brute-force login on an HTTP form:

```bash
medusa -h example.com -u admin -P passwords.txt -M http-form -m FORM:"/login.php":admin_field:password_field:"Login Failed"
```

> Note: HTTP form attacks require additional tweaking based on the page's structure.

---

## ⚙️ Other Useful Options

- `-t` → Number of parallel threads (default: 16)
- `-T` → Target port
- `-f` → Stop after first valid credential
- `-vV` → Verbose output

---

## ⚠️ Important Notes

- Medusa is an **online tool**, meaning it interacts with real systems — don't test it on systems without **explicit permission**.
- Many services implement lockouts or rate-limiting. Use with caution to avoid detection or denial-of-service.

---

## 🔐 Ethical Use Disclaimer

This tool is for **authorized penetration testing**, red teaming, or lab environments only. **Unauthorized use is illegal and unethical**.

---

## 🔗 Official Resources

- [Medusa GitHub (unofficial forks)](https://github.com/jmk-foofus/medusa)  
- [Medusa Docs](http://foofus.net/goons/jmk/medusa/medusa.html) *(if available)*

---

## 📌 Tags

#Medusa #Online

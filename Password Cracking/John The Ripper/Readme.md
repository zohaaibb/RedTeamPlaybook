# 🔑 John the Ripper

**John the Ripper** is one of the most powerful and widely used password cracking tools. It is primarily used for offline password cracking, especially on Unix/Linux systems. John takes password hashes and attempts to recover plaintext passwords through dictionary attacks, brute-force, and rule-based mangling techniques.

---

## 📌 What is John the Ripper?

John the Ripper (JtR) is an open-source password cracker designed to detect weak Unix passwords. It supports various hash types and platforms and is a go-to tool for cracking password hashes extracted from `/etc/shadow`, Windows SAM, and more.

---

## 🧠 Key Features

- Supports multiple hash types (MD5, SHA, NTLM, bcrypt, etc.)
- Extremely fast on basic hashes
- Rule-based mangling to modify wordlists
- Custom wordlist support
- Format-specific cracking
- Session management (pause/resume cracking)

---
## Supported Hash Formats
Some of the many hash types John supports:

DES, MD5, SHA-1, SHA-256, SHA-512

bcrypt

LM/NTLM (Windows)

Raw MD5

MySQL, MSSQL

PDF, ZIP, RAR, Office documents

Use --list=formats to view all supported formats.
## 🔧 Basic Usage

### 📂 1. Unshadow (Linux Only)
Combine `/etc/passwd` and `/etc/shadow` into a single file:

```bash
unshadow /etc/passwd /etc/shadow > hashes.txt
Crack Hashes
john hashes.txt --wordlist=wordlists/top-5000-passwords.txt
View Cracked Passwords
john --show hashes.txt

⚠️ Disclaimer
Use John the Ripper only on systems and hashes you have permission to audit. Unauthorized use is illegal and unethical.

Official Resources
John the Ripper GitHub
John the Ripper Documentation





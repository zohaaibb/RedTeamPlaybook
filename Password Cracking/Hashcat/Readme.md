# ⚡ Hashcat - GPU-Accelerated Password Cracker

**Hashcat** is the world’s fastest password recovery tool. It supports a wide range of hashing algorithms and utilizes the full power of GPUs (or CPUs) to crack password hashes with unmatched speed and efficiency. Hashcat is a must-have tool in every ethical hacker’s and red teamer's arsenal.

---

## 📌 What is Hashcat?

Hashcat is an advanced password recovery tool capable of brute-force, dictionary, hybrid, rule-based, mask, and combinator attacks. It supports over 300 hash algorithms, including:

- MD5, SHA1, SHA256, SHA512
- NTLM (Windows)
- bcrypt, scrypt, PBKDF2
- WPA/WPA2 (Wi-Fi)
- MySQL, MSSQL, Oracle
- and many more...

---

## 🚀 Why Use Hashcat?

🔹 Key advantages:

- Leverages GPU for high-speed cracking
- Highly customizable attack modes
- Supports massive wordlists and rule-based mutations
- Open-source and cross-platform

Hashcat is ideal for cracking strong hashes and performing large-scale offline password audits efficiently.

---

## 🛠️ Installation (Linux)

Hashcat is pre-installed on Kali Linux. If not:

```bash
sudo apt update
sudo apt install hashcat
```

Or install manually from: [https://hashcat.net/hashcat/](https://hashcat.net/hashcat/)

---

## 🧪 Basic Usage

### 🔹 Dictionary Attack

```bash
hashcat -m <hash_type> -a 0 hashes.txt wordlist.txt
```

Example:

```bash
hashcat -m 0 -a 0 hashes.txt rockyou.txt
```

Where:

- `-m` specifies the hash type (e.g., `0` for MD5, `1000` for NTLM)
- `-a` is the attack mode (e.g., `0` = straight/dictionary attack)

---

## 🎯 Attack Modes

| Mode | Description             |
|------|-------------------------|
| 0    | Dictionary (Straight)   |
| 1    | Combination             |
| 3    | Brute-force (Mask)      |
| 6    | Hybrid (Dict + Mask)    |
| 7    | Hybrid (Mask + Dict)    |

---

## 🎭 Mask Attack

Perfect when you know the pattern of the password:

```bash
hashcat -m 0 -a 3 hashes.txt ?l?l?l?l?l?d?d
```

- `?l` → lowercase
- `?u` → uppercase
- `?d` → digit
- `?s` → special character

Example: `p@ssw0rd`, `admin123`, etc.

---

## 🔐 Common Hash Modes

| Hash Type     | Mode |
|---------------|------|
| MD5           | 0    |
| SHA1          | 100  |
| NTLM          | 1000 |
| bcrypt        | 3200 |
| SHA256        | 1400 |
| WPA/WPA2      | 22000 |

List all with:

```bash
hashcat --help | grep -i hash-mode
```

---

## 💡 Example: Using CeWL Output

```bash
hashcat -m 1000 -a 0 hashes.txt cewlpasswords.txt
```

Combine with rules for password mangling:

```bash
hashcat -m 1000 -a 0 -r rules/best64.rule hashes.txt wordlist.txt
```

---

## 📂 Output & Session Control

- Pause/resume with `p`, `r`
- Check status:

```bash
hashcat --status
```

- Resume a session:

```bash
hashcat --restore
```

---

## ⚠️ Ethical Use Notice

Hashcat is a **powerful** tool. Only use it in lab environments or with **explicit permission** from the system owner. Unauthorized use may lead to criminal charges.

---

## 🔗 Official Resources

- [Hashcat.net](https://hashcat.net/hashcat/)
- [Hashcat Wiki](https://hashcat.net/wiki/)
- [GitHub Repository](https://github.com/hashcat/hashcat)

---

## 📌 Tags

#Hashcat #GPUCracking #PasswordRecovery #OfflineCracking #CyberSecurity #EthicalHacking #PenetrationTesting #RedTeamTools #InfoSec #BruteForce #WPA2Crack

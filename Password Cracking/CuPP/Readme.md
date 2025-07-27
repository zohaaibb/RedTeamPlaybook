# 👤 CUpp - Common User Passwords Profiler

**CUpp (Common User Passwords Profiler)** is a social engineering-based wordlist generator. It creates personalized password lists using information gathered about a specific target (person or organization). It’s ideal for creating highly targeted dictionaries for password cracking.

---

## 📌 What is CUpp?

CUpp builds custom wordlists by combining common human password behavior with personal information about the target. People often use predictable passwords like names, birthdays, pet names, favorite bands, or sports teams. CUpp leverages this to generate relevant and realistic password lists.

---

## 🎯 Why Use CUpp?

🔹 Use CUpp when you have or can gather personal details about a target, such as:

- Name, nickname
- Partner, child, or pet names
- Date of birth or anniversary
- Favorite brands, music, or sports teams
- Company name, keywords, hobbies

🔹 CUpp helps you:

- Increase success rate of password cracking attacks
- Target individuals with minimal noise
- Reduce wordlist size by avoiding irrelevant entries

---

## 🛠️ Installation

CUpp is **not pre-installed** on Kali Linux. Clone it from GitHub:

```bash
git clone https://github.com/Mebus/cupp.git
cd cupp
python3 cupp.py -i
```

---

## 📌 Example Usage

### 🔹 Interactive Mode

```bash
python3 cupp.py -i
```

You'll be asked questions like:

```
[+] Enter the target's first name: Krista
[+] Enter the target's nickname: Kris
[+] Enter the target's birthdate (DDMMYYYY): 12051987
...
```

After entering the details, CUpp will generate a wordlist (e.g., `krista.txt`) with thousands of combinations based on your input.

---

### 🔹 Download Wordlists from the Web

```bash
python3 cupp.py -l
```

Downloads popular password lists like `rockyou.txt`, `10-million-password-list`, etc.

---

## 📂 Output Example

CUpp might generate passwords like:

```
krista1987
krista@123
kristagordon
krista_12
kris0519
...
```

Use this output in password crackers:

```bash
john --wordlist=krista.txt hashes.txt
hashcat -a 0 -m 0 hashes.txt krista.txt
```

---

## 🧠 Best Use Cases

- Red Teaming engagements
- Social engineering simulations
- CTFs involving targeted attacks
- Password audit tests with partial intel

---

## ⚠️ Ethical Use Notice

CUpp should be used **only** in environments where you have legal authorization (e.g., pentesting, training labs, or red team exercises). Using it without consent is **illegal and unethical**.

---

## 🔗 Official Repository

- [CUpp GitHub](https://github.com/Mebus/cupp)

---

## 📌 Tags

#CUpp #PasswordProfiler #SocialEngineering #CustomWordlist #RedTeamTools #PasswordCracking #EthicalHacking #PenetrationTesting #CyberSecurity #InfoSec

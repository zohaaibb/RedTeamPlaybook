# 🕸️ CeWL - Custom Wordlist Generator

**CeWL (Custom Word List generator)** is a Ruby-based tool used to scrape websites and build targeted wordlists based on their content. It's particularly useful for generating password lists that reflect the language, terminology, and keywords associated with a specific company, industry, or individual.

---

## 📌 What is CeWL?

CeWL is a powerful tool that spiders a target website to extract words that can later be used in password cracking attacks. It helps red teamers and penetration testers create **customized dictionaries** based on a target's real-world context.

---

## 🎯 Why Use CeWL?

🔹 Many users choose passwords based on:
- Industry jargon
- Company name or values
- Job titles, technologies, or products
- Personal interests (if targeting individuals)

🔹 CeWL helps you:
- Create smarter, more relevant wordlists
- Improve the effectiveness of dictionary attacks
- Reduce guesswork by targeting meaningful words

---

## 🛠️ How CeWL Works

CeWL performs the following:

1. Crawls the specified URL
2. Collects all unique words from the text content
3. Filters words based on length (optional)
4. Outputs a custom wordlist file

---

## ⚙️ Basic Syntax

```bash
cewl [options] <URL>
```

---

## 📌 Example Usage

### 🔹 Scrape a website for words longer than 8 characters:

```bash
cewl -d 4 -m 8 https://www.example.com -w cewl-wordlist.txt
```

Where:

- `-d 4` → Depth of 4 directories
- `-m 8` → Minimum word length of 8
- `-w` → Output wordlist file name

---

## 📁 Sample Output

A typical CeWL output might include:

```
Metasploit
Vulnerability
Encryption
ExploitDevelopment
ReverseShell
```

These words can now be used in tools like **John the Ripper**, **Hashcat**, or other password crackers.

---

## 🧠 Pro Tips

- Combine CeWL output with `--rules` in John or `mask attack` in Hashcat.
- Use it on public-facing target websites before performing brute force.
- Run with `--ua` flag to bypass User-Agent restrictions.

---

## ⚠️ Ethical Use Notice

Use CeWL only on domains you are authorized to test. Web scraping without permission may violate terms of service or legal boundaries.

---

## 🔗 Official Source

- [CeWL GitHub](https://github.com/digininja/CeWL)

---

## 📌 Tags

#CeWL #CustomWordlist #PasswordCracking #WebScraping #RedTeamTools #EthicalHacking #PenetrationTesting #WordlistGenerator #CyberSecurity


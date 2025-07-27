# 🔤 Crunch - Custom Wordlist Generator

**Crunch** is a command-line tool used to generate wordlists based on specified patterns, lengths, and character sets. It’s particularly useful when you have partial information about a target’s password structure — like known suffixes, prefixes, or character rules.

---

## 📌 What is Crunch?

Crunch allows you to create **custom password lists** by generating all possible combinations of characters within specified constraints. This is incredibly useful when:

- You know a password format (e.g., `Name####`)
- You’re targeting specific length passwords
- You need a brute-force-style wordlist tailored to certain rules

---

## 🎯 Why Use Crunch?

🔹 Crunch helps you:

- Create focused wordlists rather than large, general ones
- Generate passwords based on known patterns or policies
- Reduce cracking time by excluding unrealistic combinations

---

## 🛠️ Syntax

```bash
crunch <min> <max> [options]
```

Where:

- `<min>` is the minimum length
- `<max>` is the maximum length

---

## 📌 Example Usage

### 🔹 Generate passwords exactly 8 characters long using lowercase letters:

```bash
crunch 8 8 abcdefghijklmnopqrstuvwxyz -o lowercase8.txt
```

### 🔹 Generate passwords starting with "pass" followed by 4 digits:

```bash
crunch 8 8 -t pass@@@@ -o pass4digit.txt
```

- `@` = lowercase letters  
- `^` = uppercase letters  
- `,` = numbers  
- `%` = symbols

(Use `man crunch` to view the full charset symbols)

---

## 🧪 Practical Scenario

You know the target is a Bob Dylan fan and might use the password format: `BobDylan####` (where `####` = birth year or date). You can generate:

```bash
crunch 12 12 -t BobDylan%%%% -o dylanfan.txt
```

Now use this custom list in tools like **John the Ripper** or **Hashcat**.

---

## ⚠️ Things to Consider

- Crunch can generate *very large* files quickly. Always estimate size using `-s` before creating.
- Combine it with **CeWL** or **CUpp** outputs for hybrid attacks.
- Best used when you have clues about the password format.

---

## 📎 Combine with Password Crackers

```bash
john --wordlist=dylanfan.txt --rules hashes.txt
hashcat -a 0 -m 0 hashes.txt dylanfan.txt
```

---

## 📂 Output

Crunch saves the output list into a file using the `-o` option, or streams it to stdout by default.

---

## ⚠️ Ethical Use Notice

Use Crunch only in ethical hacking environments with full authorization. Generating and using large wordlists against unauthorized systems is illegal.

---

## 🔗 Official Source

- [Crunch GitHub (Mirror)](https://github.com/crunchsec/crunch)

---

## 📌 Tags

#Crunch #PasswordGenerator #BruteForce #CustomWordlist #PasswordCracking #RedTeamTools #EthicalHacking #PenetrationTesting #CyberSecurity

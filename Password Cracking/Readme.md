# 🔐 Password Cracking

This repository provides an overview of password cracking methodologies, covering both **offline** and **online** techniques, associated challenges, and tools used in ethical hacking and penetration testing.

> ⚠️ This knowledge is intended for educational and authorized security testing purposes only. Unauthorized use is illegal and unethical.

---

## 🧭 Topics Covered

### ✅ Offline vs Online Password Cracking

#### 🔹 Offline Cracking
- Involves obtaining password **hashes** (e.g., from `/etc/shadow` or Windows `SAM` file) and cracking them locally.
- Offers unlimited attempts without alerting the target system.
- Faster when using powerful hardware or GPU acceleration.
- Often uses **dictionary attacks**, **rule-based attacks**, or **brute force** on the hashes.

#### 🔹 Online Cracking
- Involves attempting to log in directly to a live system using guessed passwords.
- Limited by lockout policies, rate limits, and detection.
- Riskier and slower, but still viable in specific attack scenarios.

---

## ⚠️ Common Issues in Password Cracking

- **Password complexity**: Length, character diversity, and randomness increase difficulty.
- **Hashing algorithms**: Slow algorithms (e.g., bcrypt) make brute force infeasible without powerful resources.
- **Account lockouts**: In online cracking, repeated attempts may lead to account lockout or IP bans.
- **Detection**: Online cracking attempts may be logged or flagged by security systems.
- **Ethical boundaries**: Cracking should always be done with permission in legal, controlled environments.

---

## 🧰 Tools Used

> These tools were used in a controlled lab environment for educational purposes:

- **John the Ripper**
- **Hashcat**
- **CeWL**
- **Crunch**
- **CUpp (Common User Password Profiler)**


---

## 🛡️ Disclaimer

This repository and its contents are meant for **educational** and **authorized penetration testing** only. Do not use any tool or technique herein against systems you do not own or have explicit permission to test.

---


# Evading AV & Shellcode

**Author/Team:** RedOps Crew  
**Document:** Evading Av & Shellcode.pdf  

---

## 📖 Overview
This guide explores how attackers may attempt to evade antivirus (AV) detection and generate shellcode that bypasses defenses. It demonstrates the use of **Metasploit’s evasion modules**, **OWASP-ZSC**, and alternative shellcode generation methods.  

⚠️ **Disclaimer:** This material is for **educational and research purposes only**. Practice strictly in a **controlled lab environment** with explicit authorization. Misuse may be illegal.

---

## 📂 Contents
1. [Metasploit’s New Evasion Module](#-metasploits-new-evasion-module)  
2. [Download and Install OWASP-ZSC](#-download-and-install-owasp-zsc)  
3. [Using OWASP-ZSC](#-using-owasp-zsc)  
4. [Generating Basic Shellcode](#-generating-basic-shellcode)  
5. [Limitations of OWASP-ZSC](#-limitations-of-owasp-zsc)  
6. [Alternative Ways to Fetch Shellcode](#-alternative-ways-to-fetch-shellcode)  
7. [Conclusion](#-conclusion)  

---

## 🛡️ Metasploit’s New Evasion Module
- Introduced in **Metasploit 5 (2018)** with two new evasion modules.  
- Initially effective against **Windows Defender on Windows 10**.  
- Microsoft quickly updated detections.  
- Still valuable for **understanding attacker vs. defender adaptation**.  

**Why?**  
Traditional payloads from `msfvenom` are often flagged by AV due to signatures. The evasion modules aimed to **obfuscate and bypass detection**.

---

## 📥 Download and Install OWASP-ZSC
OWASP-ZSC (**Zero-Day Shellcode Compiler**) helps generate, encode, and obfuscate shellcode.  

Clone and install:
```bash
git clone https://github.com/zscproject/OWASP-ZSC
cd OWASP-ZSC
chmod +x installer.py
./installer.py

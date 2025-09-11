# Covering Your Tracks

**Author/Team:** RedOps Crew  
**Document:** Covering Your Tracks.pdf  

---

## 📖 Overview
This document explores techniques attackers may use to erase their footprints after compromising a system. It demonstrates how attackers attempt to remove logs, modify timestamps, and clear command history, while also showing the **limitations** of these methods on modern systems.  

⚠️ **Disclaimer:** This material is for **educational and defensive purposes only**. Do not misuse. Practice only in controlled lab environments.

---

## 📂 Contents
1. [Introduction](#-introduction)  
2. [Covering Tracks on Windows](#-covering-tracks-on-windows)  
   - Meterpreter `clearev`  
   - `wevtutil` for event logs  
   - File timestamp manipulation (`timestomp`)  
   - Limitations, failures, and modern defenses  
3. [Covering Tracks on Linux](#-covering-tracks-on-linux)  
   - Stopping `rsyslog` and `syslog.socket`  
   - Why it fails on modern distros  
   - Risks & detection by blue teams  
4. [Removing Command History](#-removing-command-history)  
   - `$HISTSIZE` method  
   - Clearing history with `history`  
   - Secure deletion with `shred`  
5. [Key Takeaways](#-key-takeaways)  
6. [Summary](#-summary)  
7. [Disclaimer](#-disclaimer)  

---

## 📝 Introduction
Hackers who want to stay undetected attempt to minimize evidence left behind.  
Forensic investigators rely on three key sources to recreate events:  

- **Log files**  
- **File timestamps**  
- **Command history**  

If these are altered or deleted, attribution becomes more difficult.  
This guide demonstrates attacker techniques and why they often fail in modern systems.

---

## 🪟 Covering Tracks on Windows

### 🔹 Meterpreter `clearev`
When using a Meterpreter session, attackers can clear logs with:
```bash
meterpreter > clearev

---
Using wevtutil

If clearev fails, attackers can drop to a Windows shell and run:

C:\Windows\system32\wevtutil cl security


This clears the Security logs. Other logs can be targeted by replacing security with another log name, for example:

wevtutil cl application
wevtutil cl system


Note: Clearing logs leaves a noticeable gap that defenders can detect.

🔹 Timestamp Manipulation with timestomp

Attackers may try to hide file access/modification by changing timestamps:

meterpreter > timestomp malware.txt -z "06/25/2015 09:25:03"


❌ Demonstration & Failure
On Windows 7 SP1+ with hardened NTFS:

[-] priv_fs_set_file_mace: Operation failed: The handle is invalid.


Why?
Microsoft hardened metadata handling.
timestomp works on older systems (XP, Vista) but often fails on Windows 7 and later.

✅ Safer Lab Alternative (PowerShell)

(Get-Item C:\Users\<username>\Desktop\testfile.txt).CreationTime="06/25/2015 09:25:03"
(Get-Item C:\Users\<username>\Desktop\testfile.txt).LastWriteTime="06/25/2015 09:25:03"
(Get-Item C:\Users\<username>\Desktop\testfile.txt).LastAccessTime="06/25/2015 09:25:03"

🐧 Covering Tracks on Linux
🔹 Stopping rsyslog
sudo systemctl stop rsyslog


But syslog.socket auto-restarts the service when logs are generated.

🔹 Attempting to Fully Disable
sudo systemctl stop rsyslog
sudo systemctl stop syslog.socket
sudo systemctl disable rsyslog
sudo systemctl disable syslog.socket
sudo systemctl mask rsyslog


❌ Why This Is Unsafe

Systemd logs the attempt (journalctl).

Log gaps are suspicious to defenders.

Centralized logging (SIEM/Syslog servers) still receives logs.

Tampering is evidence itself.

👉 Works only in lab demos, not in real-world attacks.

⌨️ Removing Command History
🔹 Prevent Logging Commands
HISTSIZE=0
export HISTSIZE

🔹 Delete Specific Command
history -d <line_number>

🔹 Clear Entire History
history -c

🗑️ Secure File Deletion

Even after clearing history, .bash_history still exists.
Use shred to overwrite and make recovery harder:

shred -f ~/.bash_history

📌 Key Takeaways

Windows:

clearev can remove event logs.

wevtutil can clear specific logs but leaves detectable gaps.

timestomp is mostly obsolete on hardened systems.

Linux:

Stopping rsyslog alone is insufficient.

Disabling logging is noisy and detectable.

Command history:

$HISTSIZE=0 stops saving.

history -c clears logs.

shred makes recovery harder.

Defensive Note:

Blue teams monitor for gaps, tampering, and inconsistencies.

Forensics can detect timestamp manipulation and log suppression attempts.

✅ Summary

Covering tracks has always been part of post-exploitation, but:

On modern Windows systems, many tricks fail.

On modern Linux systems, logging is resilient and centralized.

Attempts to erase footprints are often more suspicious than the activity itself.

This makes studying both attacker evasion and defender detection equally important.

⚠️ Disclaimer

This project is for educational purposes only.
Do not use on systems without explicit authorization.
Misuse may be illegal and punishable under law.

Intended use: Red Team training, penetration testing labs, and defender awareness.

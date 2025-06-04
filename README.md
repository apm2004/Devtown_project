# Basic Penetration Testing Project

## 👤 Author
**Adithya Pramod Menon**

## 📅 Date
**03 June 2025**

---

## 🧾 Project Overview
This project involved discovering, exploiting, and analyzing vulnerabilities in a simulated target machine (`10.0.2.4`). The objective was to gain root access through various penetration testing methodologies and tools within a controlled environment.

---

## 🛠️ Tools & Technologies Used
- **Reconnaissance & Scanning:** `netdiscover`, `nmap`
- **Enumeration:** `nikto`, web browser
- **Exploitation:** `Metasploit`, `Hydra`, `John the Ripper`
- **Post-Exploitation:** Linux shell commands, shell upgrade using `python3`

---

## 🔍 Key Steps

### 1. Reconnaissance
- Discovered target IP using `netdiscover`
- Scanned for open ports using `nmap`

### 2. Enumeration
- Ran `nikto` on web server
- Discovered `/secret` directory and login page

### 3. Exploitation
- Attempted brute-force on login
- Used Metasploit module `exploit/unix/ftp/proftpd_133c_backdoor`
- Payload used `payload/cmd/unix/reverse`
- Gained reverse shell and escalated privileges

### 4. Post-Exploitation
- Extracted shadow hash from `/etc/shadow`
- Cracked password using `john` and `rockyou.txt`
- Upgraded shell with `python3 -c 'import pty; pty.spawn("/bin/bash")'`

---

## ❗ Initial Mistake
An early failure was caused by using the wrong target IP (`10.0.2.15` instead of `10.0.2.4`), resulting in failed exploitation attempts until corrected.

---

## 📷 Screenshots Included
- Netdiscover result
- Nmap result
- Nikto scan result
- Secret webpage on port 80
- Website login page
- Exploit setup in Metasploit
- Reverse shell session
- Shell upgrade
- Extracted shadow hash
- Bruteforce in progress
- Password cracked with John

---

## ✅ Outcome
- Full root access on target
- Successful hash extraction and password cracking
- Interactive shell access obtained

---

## 🔒 Defensive Recommendations
- Disable or update vulnerable services like vsftpd
- Restrict directory listing and access
- Implement account lockouts and rate limits
- Use strong, unique passwords for user accounts
- Monitor logs and unauthorized access attempts

---

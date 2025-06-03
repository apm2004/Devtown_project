# Basic Penetration Testing on Target Machine 10.0.2.2

## Overview
This project documents the steps and findings from a basic penetration testing engagement conducted on a target machine with IP address `10.0.2.2`. The main goal was to identify open ports, enumerate services, attempt exploitation, and analyze the security posture of the target.

## Tools Used
- **Netdiscover**: Network discovery and live host identification  
- **Nmap**: Port scanning and service/version detection  
- **Enum4linux**: SMB enumeration  
- **Nikto**: Web server vulnerability scanning  
- **Metasploit Framework**: Exploitation framework for attempting to gain access

## Project Steps

1. **Reconnaissance & Scanning**  
   - Used `netdiscover` to find live hosts on the subnet.  
   - Scanned the target IP with `nmap` to identify open ports and running services.

2. **Enumeration**  
   - Ran `enum4linux` to enumerate SMB shares and user info.  
   - Used `nikto` to scan web servers on ports 8080 and 9080 for vulnerabilities.  
   - Discovered accessible directories such as `/images` on the web server.

3. **Exploitation**  
   - Attempted to exploit PostgreSQL using Metasploit’s `postgres_copy_from_program_cmd_exec` module.  
   - Set required parameters like RHOSTS, RPORT, and LHOST.  
   - Exploit did not succeed in gaining shell access.

4. **Post Exploitation**  
   - No shell access obtained; hence, no further post-exploitation actions were possible.

## Results
- Several open ports were identified, including PostgreSQL (5432) and Apache HTTP (8080).  
- SMB service revealed limited information via enum4linux.  
- Web vulnerabilities scanned with nikto showed some accessible resources but no critical findings.  
- Exploitation attempts against PostgreSQL failed, indicating the need for stronger vectors or credentials.

## Lessons Learned
- Effective enumeration is key to understanding attack surface.  
- Default or weak credentials may not always be present; brute forcing can be time-consuming without proper wordlists.  
- Exploit modules may fail but still provide insight into potential vulnerabilities.

## Recommendations
- Harden exposed services by disabling unused ports and enforcing strong authentication.  
- Regularly update software and apply security patches.  
- Monitor and log network activity to detect suspicious attempts.

## How to Use
- Ensure the testing environment is isolated and authorized.  
- Run `netdiscover` to find live hosts.  
- Use `nmap` with service detection to find open ports.  
- Enumerate SMB and HTTP services with `enum4linux` and `nikto`.  
- Attempt exploitation using Metasploit modules relevant to discovered services.

## Disclaimer
This project is for educational purposes only. Always obtain explicit permission before performing any penetration testing activities on any network or system.

---

*Prepared by Adithya Pramod Menon*  
*Date: 03/06/25*

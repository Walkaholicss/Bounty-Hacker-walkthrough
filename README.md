# Bounty Hacker — Pentest Walkthrough

## Project Overview
This project is a "hands-on penetration test" conducted on the 'Bounty Hacker' TryHackMe room.  
It simulates a real-world attack chain from reconnaissance to privilege escalation, with all actions mapped to the "MITRE ATT&CK Framework" and compared against real-world cybersecurity incidents.

---

## Objectives
- Identify exposed network services  
- Gain unauthorized access using discovered credentials  
- Escalate privileges to root  
- Relate each stage of the attack to MITRE ATT&CK tactics  
- Recommend real-world mitigations  

---

## Environment
- Platform: TryHackMe — 'Bounty Hacker' room  
- Tools Used: Nmap, Hydra, FTP client, SSH, and standard Linux privilege escalation methods  

---

## 🕵️‍♂️ Attack Summary

| Phase | Description | MITRE ATT&CK Technique |
|-------|--------------|------------------------|
| Reconnaissance | Scanned host, discovered FTP, SSH, and HTTP ports | T1595 – Active Scanning |
| Discovery | Anonymous FTP login, listed files | T1083 – File & Directory Discovery |
| Credential Access | Retrieved password list, used Hydra for SSH brute force | T1110 – Brute Force |
| Initial Access | Logged in with valid SSH credentials | T1078 – Valid Accounts |
| Privilege Escalation | Misconfigured `sudo -l` allowed root escalation | T1548.001 – Abuse Elevation Control Mechanism |
| Collection | Accessed root artifacts | T1005 – Data from Local System |

---

## Real-World Parallels

### Military Document Theft (2018)
Hacker exploited default FTP credentials on Netgear routers, stealing classified MQ-9 Reaper and tank manuals.  
     Sources: [Recorded Future](https://www.recordedfuture.com/blog/reaper-drone-documents-leaked), [BleepingComputer](https://www.bleepingcomputer.com/news/security/hacker-steals-military-docs-because-someone-didn-t-change-a-default-ftp-password/)

### Collins Aerospace Breach (2024)
Attackers leveraged old passwords and delayed response to exfiltrate data, showing the danger of poor credential hygiene.  
Source: [Heise Online](https://www.heise.de/en/news/Collins-Aerospace-Old-Passwords-and-Delayed-Response-Enable-Data-Theft-10900183.html)

---

## Recommendations
- Disable anonymous FTP and change default credentials immediately.  
- Use MFA and strong, unique passwords across systems.  
- Prefer SSH key authentication over password logins.  
- Patch sudo and remove unnecessary NOPASSWD permissions.  
- Monitor unusual FTP downloads and brute-force attempts with SIEM alerts.  
- Train users on credential rotation and quick incident reporting.  

---

## Key Takeaways
This walkthrough demonstrates how simple misconfigurations (like open FTP or weak SSH credentials) can lead to complete compromise, both in controlled environments and in the real world.

---

## Team
Bounty Hacker Penetration Test — Team Presentation (2025)
- Tiago D.
- Mario B.
- Bertrand A

# Brute-force-personalproject4


![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)
![](.png)

![](.png)
![](.png)



## Overview
• In this project I simulated real world red team credential attacks by brute forcing exposed services, identifying weak/default passwords, and demonstrating how poor authentication expands the attack surface of an organization.

## Objective
• Evaluate the target for weak authentictaion controls such as default creds, anonymous login, and other misconfigurtaions to determine whether an attacker can gain initial access or a foothold on the network.

## Tools Used
• nmap
• burp suite
• dvwa
• OSINT
• Hydra

## Architecture

![kali setup](images/Homelab-setup2.png)
![metasploitble setup](images/Homelab-setup1.png)

## Recon/ Scanning methodology
ping -c 3 (metasploitable-ip)
![ping scan](images/ping-scan.png)
nmap -A -p 21,23,445,5432,8180
![ping scan](images/scan2.png)
![ping scan](images/scan3.png)
![ping scan](images/scan4.png)

OSINT search
![OSINT search](images/OSINT.png)

## Attack Methodogy

• Based off of the information from my nmap scans I saw that the target had a lot of vulnerabilities within it's security and I recognized a name, "Metasploitable". Metasploitable is known for having a large attack surface with weak creds being one of them. To further my search I used OSINT (Open Source Intelligence) also referred as passive recon, to search for the passwords to services in an attempt to gain access. 
![OSINT search](images/OSINT.png)

• I then put together a wordlist of both possible passwords and usernames as default creds are usually the same word. (Ex: Admin:Admin) I didn't know which username would correlate to what password so I used a method refferred to as password spraying which is testing multiple passwords against each username in the wordlist provided simply put. I did this because it would save me time from running multiple scans and from being detected. I then began to brute force every service to see if default creds were being used

Syntax: hyrda -L ms3U.txt -P /usr/share/wordlists/rockyou.txt (metasploitable-ip) ftp
![Password and userlist](images/OSINT-pws.png)


• I brute forced against the telnet service known as a old interfaace command line using the same password/username list and password sprayed
Syntax:
hyrda -L ms3U.txt -P /usr/share/wordlists/rockyou.txt (metasploitable-ip) telnet

• I brute forced against smb (server message block) using the same password/username list and password sprayed
Syntax:
hydra -L ms3U.txt -P /usr/share/wordlists/rockyou.txt (metasploitable-ip) smb

• I brute forced against postgres using the same password/username list and password sprayed
Syntax:
hyrda -L ms3U.txt -P /usr/share/wordlists/rockyou.txt (metasploitable-ip) postgres

• I brute forced against tomcat using the same password/username list and password sprayed
Syntax:
hyrda -L ms3U.txt -P /usr/share/wordlists/rockyou.txt (metasploitable-ip) 8180

## Findings
## Security Impact / Importance
## Recommendations
## Lessons Learned
## MITRE ATT&CK Mapping
## Conclusion


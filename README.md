# cybersecurity-lab
Hands-on cybersecurity lab projects (Nmap, SIEM, IR, Vulnerability scans)
Nmap Scan Project — Ubuntu VM (Local Lab)
Project Overview
This project demonstrates basic network scanning and service enumeration using Nmap inside a controlled Ubuntu virtual machine.
The goal is to identify open ports, running services, and understand the system’s network exposure as part of a cybersecurity home lab.

Environment
Target: Ubuntu 22.04.5 LTS (VirtualBox VM)
Target IP: 10.0.2.15
Network Mode: NAT
Scanner: Nmap 7.x
Service Enabled: OpenSSH (port 22)

Scan Command Used
sudo nmap -sV 10.0.2.15
sudo → Ensures full scanning capabilities
-sV → Enables service/version detection
10.0.2.15 → Target VM IP

Scan Findings:
  After enabling SSH (sudo apt install openssh-server -y), Nmap detected: 22/tcp open  ssh  OpenSSH <version> (Ubuntu)
Interpretation:
  * Port 22 is open, meaning SSH remote access is enabled. 
  * The version detection shows the running OpenSSH service.
  * Other common ports (80, 443, 3306, etc.) were closed or filtered. 
  * This indicates a minimal attack surface — only one exposed service.

Risk Summary:
Port	Service	Status	Risk
22/tcp	SSH	Open	Medium
SSH is secure when configured properly, but:
 * Weak passwords
 * Outdated OpenSSH versions
 * Exposed SSH over the internet
…can lead to brute-force or credential attacks.

Next Steps / Improvements:
1. Configure SSH security
    * Disable password authentication
    * Use key-based login
    * Change default port (optional)
2. Run deeper scans
    sudo nmap -A 10.0.2.15
    sudo nmap -p- 10.0.2.15
3. Add additional services to analyze (Apache, MySQL, etc.)
4. Document comparisons across different scans.

Files in This Folder
  * scan1.txt — Raw Nmap output
  * README.md — This analysis report

Skills Demonstrated
  * Network scanning
  * Service enumeration
  * Linux system administration
  * Nmap usage
  * Portfolio documentation
  * Basic risk interpretation

Add additional services to analyze (Apache, MySQL, etc.)

Document comparisons across different scans.

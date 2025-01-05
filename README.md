Project: Cyber Fortress
Description:
This project involves solving a challenge on the TryHackMe platform, which includes tasks such as extracting encrypted archives, analyzing source code, and privilege escalation.

In this task, tools like Nmap, Gobuster, Hashcat, and LinPeas were used. The challenge required port scanning, finding hidden files, cracking passwords, working with encrypted archives, and escalating privileges by exploiting system vulnerabilities.

All actions were performed within the legal and controlled environment of TryHackMe, which provides a legitimate and safe platform for learning and practicing cybersecurity. TryHackMe is specifically designed for educational purposes, and all tasks are solved within its platform, ensuring compliance with legal standards.

Steps Taken:
Port Scanning:
The first step was to scan open ports using the Nmap command (nmap -sV -sC -v 10.10.183.215), which revealed open ports 22 (SSH) and 80 (Apache HTTP).

Web Application Discovery:
I used Gobuster to brute-force directories and files on the web server, which led to finding an admin page and the /etc/squid folder containing a password hash.

Password Cracking:
The password hash was extracted and cracked using Hashcat. The admin credentials (username: music_archive, password: squidward) were obtained.

Accessing the Archive:
A downloaded tar archive turned out to be a Borg backup archive. After extracting files and using the password for access, the archive content was revealed, including access to the home directory of the user alex.

User Access:
SSH was used to log into the system as the user alex, allowing access to the user.txt flag.

Privilege Escalation:
LinPeas was used to find that alex had permission to run a backup script as root. By exploiting this, I executed a command to escalate privileges and capture the root.txt flag.

Tools and Techniques Used:
Nmap: For scanning and identifying open ports and services.
Gobuster: For brute-forcing directories and files on the web server.
Hashcat: For cracking password hashes.
BorgBackup: For working with encrypted backup archives.
LinPeas: For finding vulnerabilities and escalating privileges within the system.

XXE Infiltration
Platform
CyberDefenders

Skills Demonstrated
Wireshark
Network Forensics
Packet Analysis
XXE Detection
Incident Response
Scenario
Investigated a PCAP containing evidence of an XML External Entity (XXE) attack against a web application.

Findings
Reconnaissance
The attacker conducted a SYN scan.

Open service identified:

TCP 3306 (MySQL)
Vulnerable Endpoint
The attacker uploaded XML files through:

/review/upload.php
Files Accessed
The attacker successfully accessed:

/etc/passwd
and

/var/www/html/config.php
Stolen Credentials
Database User:

webuser
Database Password:

[REDACTED]
Persistence
The attacker leveraged XXE to retrieve remote content and establish persistence.

MITRE ATT&CK
Technique	ID
Network Service Scanning	T1046
Exploit Public-Facing Application	T1190
Valid Accounts	T1078
Command and Scripting Interpreter	T1059
Lessons Learned
Disable XML external entity processing.
Protect sensitive configuration files.
Store secrets securely.
Monitor unexpected XML uploads.

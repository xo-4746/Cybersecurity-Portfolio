# XXE Infiltration
## Executive Summary

This investigation analyzed a PCAP containing an XML External Entity (XXE) attack against a web application. The attacker exploited a vulnerable XML upload feature to access sensitive files, obtain database credentials, authenticate to MySQL, and establish persistence on the target system. Analysis was performed using Wireshark and network forensic techniques.


## Platform
CyberDefenders

## Skills Demonstrated

- Wireshark
- Network Forensics
- Packet Analysis
- XXE Detection
- Incident Response

## Scenario

Investigated a PCAP containing evidence of an XML External Entity (XXE) attack against a web application.

## Findings

### Reconnaissance

The attacker conducted a SYN scan.

**Open Service Identified**
- TCP 3306 (MySQL)

### Vulnerable Endpoint

The attacker uploaded malicious XML files through:

```text
/review/upload.php
```

### Files Accessed

The attacker successfully accessed:

```text
/etc/passwd
```

and

```text
/var/www/html/config.php
```

### Credential Exposure

**Database User**
```text
webuser
```

**Database Password**
```text
[REDACTED]
```

### Persistence

The attacker leveraged XXE to retrieve remote content and establish persistence.

## MITRE ATT&CK

| Technique | ID |
|------------|------------|
| Network Service Scanning | T1046 |
| Exploit Public-Facing Application | T1190 |
| Valid Accounts | T1078 |
| Command and Scripting Interpreter | T1059 |

## Lessons Learned

- Disable XML external entity processing.
- Protect sensitive configuration files.
- Store credentials securely.
- Monitor unexpected XML uploads.
- Review outbound connections initiated by web applications.

## Tools Used

- Wireshark
- CyberDefenders Lab Environment
## Evidence

### XXE Payload

![XXE Payload](screenshots/xxe-payload.png)

### Config.php Disclosure

![Config Disclosure](screenshots/config-disclosure.png)

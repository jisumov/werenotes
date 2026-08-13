# HackTheBox - Certified Defensive Security Analyst

## Incident Handling

### Definition & Scope

- Event → Action
- Incident → Event with negative consequence
- Security Incident → Event with harm intent
- Defined set of procedures → Manages and Responds to security incidents

### Value & Generic Notes

- NIST's Computer Security Incident Handling Guide → NIST 800-61
- Incident Handling Team = Incident Response Team
- Incident Manager → SOC Manager, CISO/CIO or Third-party (trusted) vendor
    - Single point of commuunication
- Investigation & Remediation → Minimize damage
- Prioritization → Greater severity → Immediate attention

### Real-World Incidents

**Leaked Credentials**

- Colonial Pipeline Randomware Attack
    - Breached employee's personal password → Access to inactive VPN account and disabled MFA

**Default / Weak Credentials**

- Mirai Botnet
    - IoT devices with default credentials → DDoS botnet → Large-scale DDoS disruptions
- LogicMonitor Incident
    - Weak default passwords → Delayed password hardening → Ransomware incidents / Unauthorized access

**Outdated Software / Unpatched Systems**

- Equifax Breach
    - CVE-2017-5638 patch not applied → Exploited Apache Struts vulnerability → Exposed personal data
- Wannacrcy
    - MS17-010 patch not applied → SMB EternalBlue exploit → Ransomware via Worm

**Rogue Employee / Insider Threat**

- Cash App
    - Insufficient controls and monitoring → Unauthorized access by employee → Exposed personal data

**Phishing / Social Engineering**

- U.S. Interior Department Phishing Attack
    - Evil Twin → Fake Wi-Fi network → Stolen credentials
- 2020 Twitter Account Hijacking
    - Social Engineering → Administrative Tools → Compromised accounts → Bitcoin scams

**Supply-Chain Attack**

- SolarWinds Orion
    - Compromised build/release environment → Malicious backdoor → Espionage and unauthorized access

### Incident Reports

- Based on Cyber Kill Chain and MITRE ATT&CK

### Cyber Kill Chain

- Attack lifecycle → Recursive stages

**Reconnaissance**

- Information gathering
- Passive → Web sources or documentation
- Active → Poking external applications and IP addresses

**Weaponize**

- Malware development → Deliverable payload
- Purpose → Persist and download more tools

**Delivery**

- Approaches → Phishing, Vishing, Smishing, etc.

**Exploitation**

- Triggered payload → Gain system access

**Installation**

- Compromised machine
    - Droppers → Small piece of code → Installs malware
    - Backdoors → Ongoing access → Further attacks
    - Rootkits → Hide its presence → Evade detection

**Command and Control**

- Remote access → Multiple variants → Persistence

**Action**

- Purpose of the attack
    - Data exfiltration
    - Ransomware

### MITRE ATT&CK Framework

- Adversary tactics and techniques
- Tactic → High-level objective
    - Initial Access
    - Persistence
    - Privilege Escalation
- Technique → Specific method
    - T1105 Ingress Tool Transfer → Downloads using wget, curl, certutil, among others
    - T1021 Remote Services → Protocols such as SSH, RDP and SMB
- Sub-technique → Particular implementation
    - T1003.001 - OS Credentials: LSASS Memory → Dumping credentials from LSASS process memory
    - T1021.002 - Remote Services: SMB/Windows Admin Shares → Shares access with valid credentials

### Pyramid of Pain

- Effort for an adversary to change tactics
- Hash/IPs = Easy to evade
- Behavioral TTP detections = Hard to evade

### TheHive

- Case management platform → Efficiently handle incidents
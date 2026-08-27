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

## Cyber Kill Chain

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

## Incident Handling Process Overview

- Capability for organizations → Prepare → Detect → Respond to malicious events
    - Preparation → Detection & Analysis → Containment, Eradication & Recovery → Post-Incident Activity

### Investigation

- Discover patient zero
- Create incident timeline
- Determine tools and malware
- Document compromised systems
- Specify actions on objectives

### Recovery

- Create & implement recovery plan → Business continuity & Disaster recovery

### Handled Incident

- Report → Root cause analysis
- Lessons learned → Improvements

## Preparation Stage

- Establish incident handling capability
- Implement appropiate protective measures
    - Server hardening
    - Active Directory tiering
    - Multi-Factor Authentication
    - Privileged access management

### Preparation Prerequisites

- Skilled incident handling team members
- Trained workforce → Security awareness
- Clear policies & documentation
- Tools → Software & Hardware

### Clear Policies & Documentation

- Up-to-date information
    - Roles
        - Incident Handling Team
    - Contacts
        - Incident Handling Team
        - Legal & Compliance Department
        - Management Team
        - IT Support
        - Communication & Media Relations Department
        - Law Enforcement
        - Internet Service Providers
        - Facility Management
        - External Incident Response Team
    - Incident
        - Response policy, plan and procedures
        - Information sharing policy and procedures
    - Availability
        - Baselines → Golden image & clean state environment
        - Network diagrams
        - Asset management database
        - Forensic & Investigative cheat sheets
    - User accounts with privileges → Tackle the incident → To be disabled and password reset once it is over
    - Agile procurement process → Faster acquisitions of necessary resources

- Customer data breach → Law Enforcement time threshold → Compliance with GDPR
- Effective reporting
    - Timestamps
    - Performed activity → Actor → Results
    - Answer → Who → What → When → Where → Why → How

### Tools (Software & Hardware)

- Jump bad → Necessary tools
    - Hardware
        - Forensic workstations → Preserve disk images & logs
        - Write blockers
        - Network & power cables
        - Hard drives & Switchers
        - Screwdrivers & tweezers
        - Secure facility → Storage & Investigation
    - Software
        - Digital forensic image acquisition
        - Memory & Network capture
        - Live response capture
        - Log analysis
        - IOCs creator → Hunt across the organization
        - Encryption
        - Ticket tracking system
    - Miscellaneous 
        - Chain of Custody forms
        - Independent incident handling system
        - Secured communication channels


### Protective Measures

**DMARC**

- Built on top of SPF & DKIM
- Spoofed email → Gets rejected
- Email sending services → Failed DMARC → May be False Positives

**Endpoint Hardening & EDR**

- Corporate devices → Malware entry point
- CIS & Microsoft baselines → More robust systems
    - Disable LLMNR/NetBIOS → Legacy protocols for local networks → Does not rely on a DNS server
    - Implement LAPS → Local Administrator Password Manager
    - Remove administrative privileges from regular users
    - Disable or configure Powershell → ConstrainedLanguage → Restrictive execution mode
    - Microsoft Defender → Enable Attack Surface Reduction (ASR) rules
    - Implement whitelisting → Tough
    - Execution blocking
        - Downloads, Desktop & AppData folders
        - Scripts with extensions including .hta, .vbs, .cmd, .bat and .js
    - Monitor LOLBin files
    - Utilize host-based firewalls
        - Block Workstation-to-Workstation & outbound LOLBins traffic
    - Deploy Antimalware Scan Interface (AMSI) → Applications integrated in antimalware products → Enhanced detection

**Network Protection**

- Segmentation → Prevents spreading
- Business-critical systems → Must be isolated → Unless there is a business justification
- Internal resources → Avoid internet facing → Unless placed in a DMZ
- IDS/IPS systems → SSL/TLS interception → Identify malicious traffic based on content
- 802.1x → Port-based network access control → BYOD risk avoidance
- Entra ID → Conditional Access policies → Managed devices → Authentication & authorization

**Privilege Identity Management / MFA / Passwords**

- Stolen privileged user credentials → AD escalation
- Passphrases → Stronger than weak & complex passwords
- Administrative access → Enable MFA

**Vulnerability Scanning**

- Continuous vulnerability scans → Can be automated
- Fixes → Can be manual or requires network segmentation
- Remediate at least "Critical" & "High" vulnerabilities

**User Awareness Training**

- Trained users → Reduced compromises
- Periodic "surprises"
    - Phishing
    - USB drop attack

**Active Directory Security Assessment**

- Attacker's perspective → Detect misconfigurations or vulnerabilities
- Own reviews → Smaller attack surface for privilege escalations
- AD escalation paths & bugs → Constant catch up by administrators

**Purple Team Exercises**

- Security assessments → Performed by red team → Informs findings → Acknowledged by blue team → Incident handling testing → Continuous improvement
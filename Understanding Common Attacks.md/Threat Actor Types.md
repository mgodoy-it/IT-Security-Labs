# Understanding Common Attacks (Detection & Forensics Focus)

This lab focuses on identifying suspicious activity using log analysis and basic security detection techniques. All exercises are performed using sample data in a safe lab environment.

---

## Threat Actor Types (High-Level Overview)
- Script Kiddies: Use simple tools and scripts
- Cybercriminals: Focus on financial gain
- Insider Threats: Misuse of legitimate access
- Note: This section is for awareness, not exploitation

---

## Detection & Security Monitoring (Beginner Level)

### 1. Brute Force Login Attempts
- Detect repeated failed authentication attempts
- Log sources: authentication logs, Windows event logs
- Example tools: Splunk

### 2. Port Scanning Detection
- Identify multiple connection attempts from one source IP
- Log sources: firewall, IDS, network logs

### 3. Suspicious Login Activity
- Detect logins from multiple IPs for the same user
- Useful for identifying account misuse

### 4. DDoS (Basic Indicators)
- Identify spikes in traffic targeting a single system
- Log sources: network traffic logs

### 5. Malicious File Activity (Basic)
- Detect downloads or executions of suspicious file types
- Log sources: endpoint or HTTP logs

---

## Digital Forensics (Intro Level)

### Log Analysis
- Review logs to establish timelines
- Identify unusual patterns or anomalies

### Indicators of Compromise (IOCs)
- IP addresses, file names, hashes (sample only)
- Used to support detection and investigation

### Incident Awareness
- Understand how alerts relate to potential incidents
- Focus on observation and documentation

---

## Notes
- All exercises are beginner-friendly
- No exploitation or offensive techniques
- Lab data only (non-production environment)

## Skills Demonstrated
- Log analysis and security monitoring
- Basic incident detection
- Introductory digital forensics concepts
- SIEM usage (Splunk)

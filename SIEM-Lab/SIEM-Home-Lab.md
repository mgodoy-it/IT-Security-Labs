<!--

# SIEM Home Lab Project

This repository documents my hands‑on Security Information and Event Management (SIEM) lab environment.  
The goal of this project is to demonstrate practical cybersecurity skills, including log collection, threat detection, alerting, and investigation using **Splunk Free**, **Sysmon**, and a Windows virtual machine.

This lab serves as part of my cybersecurity portfolio and showcases my ability to work with real security telemetry and build detections similar to what a SOC analyst performs.

---

## Objectives

- Build a functional SIEM environment using Splunk Free  
- Collect and analyze Windows security logs  
- Install and configure Sysmon for enhanced visibility  
- Create detection rules for common attack behaviors  
- Investigate simulated security incidents  
- Document findings clearly and professionally  

---

## Lab Architecture

Windows VM (Sysmon + Event Logs)

- Splunk Universal Forwarder
- Splunk Enterprise (Local SIEM)


---

## Repository Structure

SIEM

- Environment-Setup
- Log-Collection
- SIEM-Platform
- Detections
- Investigations
- Dashboarding


### Folder Overview

| Folder | Description |
|--------|-------------|
| **Environment-Setup** | VM setup, network diagram, system requirements |
| **Log-Collection** | Sysmon installation, config file, sample logs |
| **SIEM-Platform** | Splunk installation, configuration, forwarder setup |
| **Detections** | Detection rules, alert logic, screenshots |
| **Investigations** | Case studies, timelines, incident analysis |
| **Dashboarding** | Splunk dashboards and visualizations |

---

## 🔧 Tools Used

- **Splunk Enterprise (Free License)**
- **Splunk Universal Forwarder**
- **Windows 10/11 Virtual Machine**
- **Sysmon (System Monitor)**
- **SwiftOnSecurity Sysmon Config**
- **Event Viewer / Windows Event Logs**

---

## 🧪 Detection Use Cases (Planned & Completed)

- [ ] Multiple failed login attempts (Event ID 4625)  
- [ ] Successful login from unusual source  
- [ ] Suspicious PowerShell execution  
- [ ] New user account creation  
- [ ] Process injection or abnormal parent/child processes  
- [ ] Brute force attack simulation  

Each detection will include:
- Description  
- Log source  
- Splunk search query  
- Alert configuration  
- Screenshots  
- Explanation of why it matters  

---

## 🔍 Investigations (Planned)

- Brute force attack investigation  
- Malicious PowerShell activity  
- Suspicious process execution  
- Lateral movement attempt  

Each investigation will include:
- Timeline  
- Evidence  
- Queries used  
- Findings  
- Analyst conclusion  

---

## What I Learned

- How SIEM platforms ingest and index logs  
- How Sysmon enhances endpoint visibility  
- How to write Splunk queries (SPL)  
- How to build detections based on real attack behaviors  
- How to document investigations like a SOC analyst  

---

## Next Steps

- Add more detections  
- Add dashboards  
- Expand to Linux logs  
- Integrate additional tools (ELK, Wazuh, etc.)  



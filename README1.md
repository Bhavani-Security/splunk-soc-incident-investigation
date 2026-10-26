# Splunk SOC Incident Investigation

## 1. Project Overview

This project documents a hands-on SOC Analyst training lab using Splunk SIEM. The objective was to investigate a simulated cyberattack by correlating logs from multiple sources and reconstructing the attack timeline.

## 2. Tools and Technologies

- Splunk SIEM
- Endpoint Detection and Response (EDR)
- Authentication logs
- Web proxy logs
- Email gateway logs
- SPL (Search Processing Language)
- MITRE ATT&CK framework

## 3. Investigation Objectives

- Investigate suspicious endpoint alerts.
- Identify unusual authentication and VPN activity.
- Analyse a suspected phishing email.
- Detect credential theft and possible lateral movement.
- Identify potentially compromised accounts and systems.
- Build a unified incident timeline.
- Recommend containment and remediation actions.

## 4. Investigation Steps

### Step 1: Alert Triage

Investigated high- and critical-severity EDR alerts to identify suspicious PowerShell execution and potential LSASS credential dumping.

### Step 2: Endpoint Investigation

Reviewed process names, parent processes, command lines and event timestamps to understand the sequence of suspicious activity on the affected workstation.

### Step 3: Authentication Analysis

Correlated identity sign-ins, VPN sessions and remote logons. Identified a suspicious foreign sign-in followed by VPN access and a remote logon to the workstation.

### Step 4: Phishing Investigation

Correlated email gateway and proxy logs to investigate a suspicious email containing a look-alike domain. The lab evidence indicated that the user visited the website and submitted credentials.

### Step 5: Threat Hunting

Investigated repeated failed logons against multiple accounts and suspicious access to a file server. The findings indicated possible lateral movement and a second compromised account.

### Step 6: Incident Timeline

Correlated four log sources in Splunk:

- EDR
- Authentication
- Proxy
- Email gateway

The combined timeline helped reconstruct the suspected attack from initial phishing delivery to subsequent suspicious server activity.

## 5. Key Findings

- A phishing email was delivered to multiple recipients.
- The lab evidence indicated that one user visited the malicious website and submitted credentials.
- Suspicious authentication and VPN activity followed.
- Endpoint alerts indicated encoded PowerShell execution and potential credential dumping.
- Password spraying and suspicious service-account activity suggested possible lateral movement.
- Additional investigation would be required to confirm the full impact and persistence.

## 6. Incident Response Recommendations

1. Disable or restrict confirmed compromised accounts.
2. Reset credentials and revoke active sessions where appropriate.
3. Block confirmed malicious indicators at relevant security controls.
4. Isolate affected endpoints when justified by the evidence.
5. Preserve logs and forensic evidence.
6. Investigate persistence, lateral movement and other affected systems.
7. Review MFA enforcement, least privilege and network segmentation.
8. Document findings and validate remediation.

## 7. Key Learnings

- An alert is the beginning of an investigation, not the conclusion.
- Email delivery does not automatically mean a user is compromised.
- Correlating multiple log sources provides a clearer picture of an incident.
- Following attacker activity can reveal additional affected systems.
- A unified timeline supports effective incident response.

## 8. Disclaimer

This is a simulated cybersecurity training lab. The findings describe the training scenario and do not represent a confirmed real-world security incident.

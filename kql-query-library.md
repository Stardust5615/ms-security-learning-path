# KQL Query Library

A personal library of KQL queries for Microsoft Sentinel, Defender XDR, and Log Analytics.  
Add queries as you write and validate them. Each section maps to a security domain.

---

## How to Use This Library

| Column | Description |
|--------|-------------|
| **Query Name** | Short descriptive name for the query |
| **Description** | What the query looks for or returns |
| **Use Case** | Threat hunting, detection, investigation, compliance, or reporting |
| **MITRE Technique** | Mapped ATT&CK technique ID(s) — e.g. T1078 |

Queries are stored in fenced code blocks beneath each table row (see template below).

---

## Identity & Authentication

| Query Name | Description | Use Case | MITRE Technique |
|------------|-------------|----------|-----------------|
| Impossible Travel Sign-In | Detects sign-ins from two geographically distant locations within a short time window | Threat Hunting | T1078 — Valid Accounts |
| MFA Failure Spike | Identifies accounts with an unusual number of MFA failures in a rolling window | Detection | T1110 — Brute Force |
| Privileged Role Assignment | Alerts when a user is added to a high-privilege Azure AD role | Detection | T1098 — Account Manipulation |
| Legacy Authentication Sign-In | Finds successful sign-ins using legacy authentication protocols | Detection | T1078.004 — Cloud Accounts |
| Guest Account Sign-In Anomaly | Detects guest users signing in outside of business hours | Threat Hunting | T1078 — Valid Accounts |
| Risky Sign-In Review | Queries Identity Protection risky sign-in events above a threshold | Investigation | T1078 — Valid Accounts |
| Service Principal Credential Added | Detects new credentials added to service principals | Detection | T1098.001 — Additional Cloud Credentials |

### Query: Impossible Travel Sign-In
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: MFA Failure Spike
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Privileged Role Assignment
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Legacy Authentication Sign-In
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Guest Account Sign-In Anomaly
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Risky Sign-In Review
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Service Principal Credential Added
```kql
// TODO: fill in after writing and validating in Sentinel
```

---

## Endpoint & Device

| Query Name | Description | Use Case | MITRE Technique |
|------------|-------------|----------|-----------------|
| Suspicious PowerShell Execution | Detects encoded or obfuscated PowerShell command lines | Detection | T1059.001 — PowerShell |
| LSASS Memory Access | Identifies processes attempting to read LSASS memory | Detection | T1003.001 — LSASS Memory |
| Lateral Movement via PsExec | Detects PsExec or similar remote execution tools | Threat Hunting | T1021.002 — SMB/Windows Admin Shares |
| Unusual Child Process from Office App | Detects Office apps spawning unusual child processes | Detection | T1566.001 — Spearphishing Attachment |
| Persistence via Scheduled Task | Finds newly created scheduled tasks with suspicious paths | Detection | T1053.005 — Scheduled Task |
| Device Missing Security Updates | Reports devices not patched within the last 30 days | Compliance | — |
| ASR Rule Triggered | Queries Attack Surface Reduction rule events | Investigation | T1059 — Command and Scripting Interpreter |

### Query: Suspicious PowerShell Execution
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: LSASS Memory Access
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Lateral Movement via PsExec
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Unusual Child Process from Office App
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Persistence via Scheduled Task
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Device Missing Security Updates
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: ASR Rule Triggered
```kql
// TODO: fill in after writing and validating in Defender XDR
```

---

## Email & Collaboration

| Query Name | Description | Use Case | MITRE Technique |
|------------|-------------|----------|-----------------|
| Phishing Mail Delivered | Finds emails classified as phishing that were delivered to inboxes | Investigation | T1566.001 — Spearphishing Attachment |
| Malicious URL Clicked | Detects users who clicked URLs that were later detonated as malicious | Detection | T1566.002 — Spearphishing Link |
| Email Forwarding Rule Created | Identifies inbox forwarding rules created to external addresses | Detection | T1114.003 — Email Forwarding Rule |
| Bulk Sender Anomaly | Detects an account sending an unusually high volume of email | Detection | T1534 — Internal Spearphishing |
| Safe Attachment Detonation Result | Reviews Safe Attachments detonation results for a time period | Investigation | T1566.001 — Spearphishing Attachment |
| Domain Impersonation Attempt | Finds emails where the sender domain closely resembles an internal domain | Threat Hunting | T1566 — Phishing |

### Query: Phishing Mail Delivered
```kql
// TODO: fill in after writing and validating in Defender XDR / Sentinel
```

### Query: Malicious URL Clicked
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Email Forwarding Rule Created
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Bulk Sender Anomaly
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Safe Attachment Detonation Result
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Domain Impersonation Attempt
```kql
// TODO: fill in after writing and validating in Defender XDR
```

---

## Data & Compliance

| Query Name | Description | Use Case | MITRE Technique |
|------------|-------------|----------|-----------------|
| DLP Policy Match by User | Summarises DLP policy match events grouped by user | Compliance | T1048 — Exfiltration Over Alternative Protocol |
| Sensitivity Label Downgrade | Detects when a sensitivity label is changed to a lower classification | Detection | T1565 — Data Manipulation |
| Bulk File Download from SharePoint | Identifies a user downloading a large number of files in a short window | Threat Hunting | T1039 — Data from Network Shared Drive |
| Purview Audit — File Access by External User | Reviews file access events by guest or external users | Investigation | T1078 — Valid Accounts |
| Retention Label Removed | Detects removal of a retention label from content | Detection | T1070 — Indicator Removal |
| eDiscovery Search Run | Logs when a content search or eDiscovery case search is executed | Compliance | — |

### Query: DLP Policy Match by User
```kql
// TODO: fill in after writing and validating in Sentinel / Purview
```

### Query: Sensitivity Label Downgrade
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Bulk File Download from SharePoint
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Purview Audit — File Access by External User
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: Retention Label Removed
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: eDiscovery Search Run
```kql
// TODO: fill in after writing and validating in Sentinel
```

---

## Threat Hunting

| Query Name | Description | Use Case | MITRE Technique |
|------------|-------------|----------|-----------------|
| Living Off the Land Binaries (LOLBins) | Finds execution of commonly abused Windows binaries | Threat Hunting | T1218 — System Binary Proxy Execution |
| Unusual Outbound Network Connection | Detects endpoints making connections to rare external IPs | Threat Hunting | T1071 — Application Layer Protocol |
| DNS Tunnelling Indicator | Identifies unusually long or high-frequency DNS queries | Threat Hunting | T1071.004 — DNS |
| New Local Admin Account Created | Detects creation of a new local administrator account | Threat Hunting | T1136.001 — Create Local Account |
| Registry Run Key Persistence | Finds additions to common registry persistence locations | Threat Hunting | T1547.001 — Registry Run Keys |
| Credential Dumping Tools | Detects known credential dumping tool names or hashes | Threat Hunting | T1003 — OS Credential Dumping |
| C2 Beacon Pattern — Regular Intervals | Identifies devices making requests to external hosts at regular intervals | Threat Hunting | T1071 — Application Layer Protocol |

### Query: Living Off the Land Binaries (LOLBins)
```kql
// TODO: fill in after writing and validating in Defender XDR / Sentinel
```

### Query: Unusual Outbound Network Connection
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: DNS Tunnelling Indicator
```kql
// TODO: fill in after writing and validating in Sentinel
```

### Query: New Local Admin Account Created
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Registry Run Key Persistence
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: Credential Dumping Tools
```kql
// TODO: fill in after writing and validating in Defender XDR
```

### Query: C2 Beacon Pattern — Regular Intervals
```kql
// TODO: fill in after writing and validating in Sentinel
```

---

## Resources

- [KQL Quick Reference — Microsoft Learn](https://learn.microsoft.com/en-us/azure/data-explorer/kql-quick-reference)
- [Microsoft Sentinel GitHub — Community Queries](https://github.com/Azure/Azure-Sentinel)
- [Defender XDR Advanced Hunting Schema](https://learn.microsoft.com/en-us/microsoft-365/security/defender/advanced-hunting-schema-tables)
- [MITRE ATT&CK Framework](https://attack.mitre.org/)

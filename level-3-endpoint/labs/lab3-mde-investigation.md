# Lab 3: Defender for Endpoint Investigation

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 3 — Endpoint Security |
| **Certification Target** | MD-102 |
| **Estimated Duration** | ~90 minutes (plus simulation wait time) |
| **Environment** | Microsoft Defender portal — Evaluation lab or enrolled device |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Trigger a detection using MDE Evaluation Lab or EICAR test file
- [ ] Investigate the generated incident: attack story, alerts, entities, evidence
- [ ] Take at least two response actions
- [ ] Resolve the incident with a classification
- [ ] Review Threat & Vulnerability Management — top 5 recommendations

## Prerequisites

- MDE Evaluation Lab provisioned (https://security.microsoft.com → Evaluation & tutorials → Evaluation lab)
- OR: enrolled device from Lab 1 + EICAR test file from https://www.eicar.org

---

## Attack Simulation

| Field | Value |
|-------|-------|
| **Simulation method** | <!-- MDE Eval Lab / EICAR test file / other --> |
| **Simulation name** | <!-- e.g. "Document drops backdoor" / "Fileless PowerShell attack" --> |
| **Device targeted** | <!-- device name --> |
| **Date/time launched** | <!-- fill in --> |
| **Alerts generated (approx.)** | <!-- count --> |

<!-- screenshot: simulation-setup.png -->
<!-- screenshot: simulation-running.png -->

---

## Incident Investigation

### Incident ID: <!-- fill in -->

| Field | Value |
|-------|-------|
| **Severity** | <!-- High / Medium / Low --> |
| **Category** | <!-- Malware / Credential theft / Lateral movement / etc --> |
| **Status** | <!-- Active / Investigating --> |
| **Assigned to** | <!-- your name --> |
| **MITRE ATT&CK techniques** | <!-- T1059.001, T1003, etc --> |

<!-- screenshot: incident-overview.png -->

### Attack Story Timeline

| Timestamp | Event | Significance |
|-----------|-------|-------------|
| <!-- time --> | <!-- event --> | <!-- why it matters --> |
| <!-- time --> | | |
| <!-- time --> | | |
| <!-- time --> | | |

<!-- screenshot: attack-story.png -->

### Alerts Generated

| Alert Name | Severity | Description |
|------------|----------|-------------|
| <!-- name --> | <!-- High/Med/Low --> | <!-- what was detected --> |
| | | |
| | | |

<!-- screenshot: alerts-tab.png -->

### Entities Involved

| Entity Type | Value | Detail |
|-------------|-------|--------|
| **Device** | <!-- name --> | OS: <!-- ver -->, Last seen: <!-- time --> |
| **User** | <!-- upn --> | Risk level: <!-- none/medium/high --> |
| **Process** | <!-- process name --> | Path: <!-- path -->, Hash: <!-- hash --> |
| **File** | <!-- filename --> | Hash: <!-- SHA256 -->, Verdict: <!-- malicious/suspicious/clean --> |
| **IP address** | <!-- IP --> | Geolocation: <!-- country --> |

<!-- screenshot: entities-tab.png -->

### Evidence Tab Summary

| Evidence Type | Count | Notable Items |
|--------------|-------|--------------|
| Files | <!-- n --> | <!-- notable filenames --> |
| Processes | <!-- n --> | <!-- notable process names --> |
| Registry keys | <!-- n --> | <!-- notable keys --> |
| Network connections | <!-- n --> | <!-- notable IPs/domains --> |

<!-- screenshot: evidence-tab.png -->

### Response Actions Taken

| Action | Time | Result |
|--------|------|--------|
| <!-- e.g. Isolate device --> | <!-- time --> | <!-- device isolated / undo worked --> |
| <!-- e.g. Run antivirus scan --> | <!-- time --> | <!-- scan results --> |
| <!-- e.g. Collect investigation package --> | <!-- time --> | <!-- package downloaded --> |

<!-- screenshot: response-actions.png -->
<!-- screenshot: device-isolation.png -->

### Resolution

| Field | Value |
|-------|-------|
| **Classification** | <!-- True positive / False positive --> |
| **Determination** | <!-- Malware / Phishing / Security testing / etc --> |
| **Remediation performed** | <!-- what was done --> |
| **Resolved by** | <!-- your name --> |
| **Resolution date** | <!-- fill in --> |

<!-- screenshot: incident-resolved.png -->

---

## Threat & Vulnerability Management Report

| # | Recommendation | Exposed Devices | Impact Score | Remediation Action |
|---|---------------|-----------------|-------------|-------------------|
| 1 | <!-- name --> | <!-- count --> | <!-- score --> | <!-- action --> |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |

<!-- screenshot: tvm-dashboard.png -->
<!-- screenshot: tvm-top-recommendations.png -->

---

## Lessons Learned

<!-- What was the most valuable part of tracing the attack story? -->
<!-- How did MITRE ATT&CK techniques help you understand the attack? -->
<!-- What would you do differently in a real incident vs this lab? -->

## Exam Relevance

<!-- MD-102: Investigate threats with Microsoft Defender for Endpoint -->
<!-- MD-102: Perform actions on a device using Microsoft Defender for Endpoint -->
<!-- SC-200 preview: Mitigate threats using Microsoft Defender for Endpoint -->

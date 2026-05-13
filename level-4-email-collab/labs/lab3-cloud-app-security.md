# Lab 3: Defender for Cloud Apps — Shadow IT Discovery & OAuth Governance

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 4 — Email, Collaboration & Cloud App Security |
| **Certification Target** | MS-500 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Defender portal → Cloud apps → Cloud discovery |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Upload sample logs to Cloud Discovery and process a snapshot report
- [ ] Review discovered apps sorted by risk score
- [ ] Mark at least 3 apps as Unsanctioned and 3 as Sanctioned
- [ ] Review OAuth apps for over-privileged or suspicious permissions
- [ ] Revoke at least one suspicious OAuth app

---

## Part A: Snapshot Report

| Field | Value |
|-------|-------|
| **Report name** | <!-- fill in --> |
| **Log format used** | <!-- e.g. Cisco ASA / Generic W3C / other --> |
| **Log source** | Sample log from Microsoft documentation |
| **Processing time** | <!-- how long it took --> |
| **Total apps discovered** | <!-- count --> |
| **Date processed** | <!-- fill in --> |

<!-- screenshot: snapshot-report-upload.png -->
<!-- screenshot: cloud-discovery-dashboard.png -->

---

## Part B: App Risk Assessment

### Top 10 Riskiest Apps Discovered

| # | App Name | Risk Score | Category | Users | Sanctioned? |
|---|----------|-----------|---------|-------|------------|
| 1 | <!-- name --> | <!-- /10 --> | <!-- category --> | <!-- count --> | <!-- Yes/No/Unsanctioned --> |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| 6 | | | | | |
| 7 | | | | | |
| 8 | | | | | |
| 9 | | | | | |
| 10 | | | | | |

<!-- screenshot: discovered-apps-by-risk.png -->

### Sanctioned / Unsanctioned Decisions

| App | Decision | Justification |
|-----|----------|--------------|
| <!-- app --> | Unsanctioned | <!-- e.g. no SOC2, no GDPR compliance --> |
| <!-- app --> | Unsanctioned | |
| <!-- app --> | Unsanctioned | |
| <!-- app --> | Sanctioned | <!-- e.g. business-critical, approved by IT --> |
| <!-- app --> | Sanctioned | |
| <!-- app --> | Sanctioned | |

<!-- screenshot: unsanctioned-apps.png -->
<!-- screenshot: sanctioned-apps.png -->

---

## Part C: OAuth App Governance

| App Name | Publisher | Permissions Requested | Risk | Action Taken |
|----------|-----------|----------------------|------|-------------|
| <!-- app --> | <!-- publisher --> | <!-- permissions --> | <!-- High/Med/Low --> | <!-- Revoked / Approved / Monitored --> |
| | | | | |
| | | | | |

**High-risk permission flags to look for:**
- `Mail.Read` or `Mail.ReadWrite` — can read all email
- `Files.ReadWrite.All` — can read/write all files
- `Directory.ReadWrite.All` — can modify directory objects
- Unverified publisher

<!-- screenshot: oauth-apps-list.png -->
<!-- screenshot: high-risk-app-permissions.png -->
<!-- screenshot: app-revoked.png -->

---

## Lessons Learned

<!-- What is shadow IT and why does it create risk? -->
<!-- What is the difference between sanctioning and blocking an app? -->
<!-- What OAuth permissions would immediately concern you in production? -->

## Exam Relevance

<!-- MS-500: Implement Microsoft Defender for Cloud Apps — cloud discovery, app governance -->
<!-- SC-300: Implement app governance and OAuth app policies -->

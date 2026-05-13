# Lab 3: Data Loss Prevention Policy

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 5 — Data Security & Compliance |
| **Certification Target** | SC-400 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Purview → Data loss prevention → Policies |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create a DLP policy for financial data using the U.S. Financial Data template
- [ ] Configure a low-volume rule (policy tip, no block) and high-volume rule (block + alert)
- [ ] Allow user override with business justification for low-volume rule
- [ ] Test with fake credit card numbers in SharePoint
- [ ] Review DLP alerts in the Purview alerts dashboard

---

## DLP Policy Configuration

| Setting | Value |
|---------|-------|
| **Policy name** | DLP — Block External Sharing of Financial Data |
| **Template used** | Financial → U.S. Financial Data |
| **Locations** | Exchange email; SharePoint sites; OneDrive accounts; Teams chat and channel messages |
| **Mode** | Test it out first (simulation) |

### Low-Volume Rule (1–9 instances)

| Setting | Value | Rationale |
|---------|-------|-----------|
| **Rule name** | Low Volume — Financial Data | |
| **Sensitive info type** | Credit Card Number (1–9 instances) | |
| **Action** | Show policy tip to user | Educate without blocking — low volume is likely accidental |
| **Incident report** | Log to DLP alerts | Build visibility |
| **User override** | Allow with business justification | Legitimate use cases must be accommodated |

### High-Volume Rule (10+ instances)

| Setting | Value | Rationale |
|---------|-------|-----------|
| **Rule name** | High Volume — Financial Data | |
| **Sensitive info type** | Credit Card Number (10+ instances) | |
| **Action: Block external sharing** | Yes | Large volumes are almost never legitimate for external sharing |
| **Action: Send incident report** | Yes — to admin email | Alert security team |
| **Action: Show policy tip** | Yes | User awareness |
| **User override** | Not allowed | High volume warrants hard block |

<!-- screenshot: dlp-policy-config.png -->
<!-- screenshot: dlp-low-volume-rule.png -->
<!-- screenshot: dlp-high-volume-rule.png -->
<!-- screenshot: dlp-policy-locations.png -->

---

## Test Results

### Test 1: Low-Volume (< 10 credit card numbers)

| Field | Value |
|-------|-------|
| Content created | Word doc with 3 fake credit card numbers |
| Uploaded to | SharePoint |
| Sharing attempted | External (outside tenant) |
| Policy tip appeared | <!-- Yes/No --> |
| Sharing blocked | <!-- Yes/No — should NOT be blocked at low volume --> |

<!-- screenshot: policy-tip-low-volume.png -->

### Test 2: High-Volume (10+ credit card numbers)

| Field | Value |
|-------|-------|
| Content created | Word doc with 15 fake credit card numbers (4111 1111 1111 1111 × 15) |
| Uploaded to | SharePoint |
| Sharing attempted | External |
| External share blocked | <!-- Yes/No --> |
| Incident report sent | <!-- Yes/No --> |

<!-- screenshot: share-blocked-high-volume.png -->
<!-- screenshot: incident-report-email.png -->

---

## DLP Alerts Review

| Alert | Policy | Rule | Severity | Date | Action Taken |
|-------|--------|------|---------|------|-------------|
| <!-- alert title --> | DLP — Block External Sharing... | <!-- rule name --> | <!-- High/Med/Low --> | <!-- date --> | <!-- Reviewed / Dismissed --> |

<!-- screenshot: dlp-alerts-dashboard.png -->
<!-- screenshot: alert-detail.png -->

---

## False Positive Analysis

| Item Flagged | Was It a False Positive? | Reason | Tuning Recommendation |
|-------------|------------------------|--------|----------------------|
| <!-- item --> | <!-- Yes/No --> | <!-- reason --> | <!-- recommendation --> |

---

## Lessons Learned

<!-- Why is the two-rule approach (low volume = tip, high volume = block) better than a single rule? -->
<!-- What is the difference between DLP in test mode vs active mode? -->
<!-- How does DLP complement sensitivity labels? (different controls, same goal) -->

## Exam Relevance

<!-- SC-400: Create and configure data loss prevention policies -->
<!-- SC-400: Implement and manage endpoint DLP -->
<!-- SC-400: Monitor DLP policy matches, alerts, and reports -->

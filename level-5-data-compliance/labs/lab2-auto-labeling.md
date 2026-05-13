# Lab 2: Auto-Labeling Policy

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 5 — Data Security & Compliance |
| **Certification Target** | SC-400 |
| **Estimated Duration** | ~45 minutes setup + up to 48 hours simulation |
| **Environment** | Microsoft Purview → Information protection → Auto-labeling |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create an auto-labeling policy targeting credit card numbers and IBAN
- [ ] Run in Simulation mode first (never deploy without simulation)
- [ ] Test with a document containing fake credit card numbers
- [ ] Review simulation results and decide: ready to enable or needs tuning?

## Prerequisites

- Lab 1 complete (Confidential label must exist)
- Sensitivity label policy published to users

---

## Auto-Labeling Policy Configuration

| Setting | Value | Rationale |
|---------|-------|-----------|
| **Policy name** | Auto-Label Confidential — Financial Data | |
| **Label to apply** | Confidential | Matches classification scheme from Lab 1 |
| **Sensitive info types** | Credit Card Number; International Banking Account Number (IBAN) | Common financial data indicators |
| **Instance count** | 1 or more | Any single occurrence triggers auto-label |
| **Locations** | Exchange email; SharePoint sites; OneDrive accounts | Covers all common content repositories |
| **Mode** | Simulation | Critical — never deploy without simulation first |

<!-- screenshot: auto-label-policy-config.png -->
<!-- screenshot: auto-label-sit-selection.png -->
<!-- screenshot: auto-label-locations.png -->
<!-- screenshot: auto-label-simulation-mode.png -->

---

## Test Data Created

| Content Type | Location | Test Data Used |
|-------------|----------|---------------|
| Word document | OneDrive | Fake credit card: 4111 1111 1111 1111 |
| Email | Exchange | Same fake credit card number in body |

> **Note:** 4111 1111 1111 1111 is the industry-standard test credit card number (Visa test number). It will never generate real charges.

<!-- screenshot: test-document-created.png -->
<!-- screenshot: test-email-sent.png -->

---

## Simulation Results

| Metric | Value |
|--------|-------|
| **Simulation run date** | <!-- fill in --> |
| **Items matched** | <!-- count --> |
| **SharePoint matches** | <!-- count --> |
| **OneDrive matches** | <!-- count --> |
| **Exchange matches** | <!-- count --> |
| **False positives identified** | <!-- count and description --> |

<!-- screenshot: simulation-results.png -->
<!-- screenshot: matched-items-list.png -->

---

## Decision: Enable or Tune?

| Question | Answer |
|----------|--------|
| Are there false positives? | <!-- Yes/No — if yes, describe --> |
| Are matches what you expected? | <!-- Yes/No --> |
| Ready to enable? | <!-- Yes / No — needs tuning --> |
| If tuning needed: what change? | <!-- e.g. Increase instance count to 3, add exception for a specific site --> |

---

## Lessons Learned

<!-- Why is simulation mode critical before enabling auto-labeling in production? -->
<!-- What is the difference between auto-labeling on the service side vs client-side automatic labeling? -->
<!-- What happens if content already has a label applied — does auto-labeling override it? -->

## Exam Relevance

<!-- SC-400: Implement auto-labeling policies for sensitivity labels -->
<!-- SC-400: Monitor label usage and activity in content explorer -->

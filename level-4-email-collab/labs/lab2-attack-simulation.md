# Lab 2: Attack Simulation Training

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 4 — Email, Collaboration & Cloud App Security |
| **Certification Target** | MS-500 |
| **Estimated Duration** | ~30 minutes setup + 2–4 hours simulation runtime |
| **Environment** | Microsoft Defender portal → Email & collaboration → Attack simulation training |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Launch a Credential Harvest simulation targeting test users
- [ ] Have one user "click and enter credentials", one report the email, one ignore it
- [ ] Review click rate, compromise rate, and report rate
- [ ] Document training recommendations based on results

## Prerequisites

- Defender for Office 365 Plan 2 (included in E5)
- At least 3 test user accounts with mailboxes

---

## Campaign Details

| Field | Value |
|-------|-------|
| **Technique** | Credential Harvest |
| **Simulation name** | Lab — Credential Harvest Test |
| **Payload selected** | <!-- e.g. "Password Expiration Notice" / "IT Support Request" --> |
| **Target users** | <!-- count and list --> |
| **Landing page** | Microsoft default (shows users they were phished + education) |
| **Launch type** | Immediately |
| **Launch date** | <!-- fill in --> |

<!-- screenshot: simulation-setup.png -->
<!-- screenshot: payload-selection.png -->
<!-- screenshot: target-users.png -->

---

## Results

| Metric | Count | Percentage |
|--------|-------|-----------|
| Emails sent | <!-- n --> | 100% |
| Emails opened | <!-- n --> | <!-- % --> |
| Links clicked | <!-- n --> | <!-- % --> |
| Credentials entered | <!-- n --> | <!-- % --> |
| Reported as phishing | <!-- n --> | <!-- % --> |

<!-- screenshot: simulation-results-dashboard.png -->

## Per-User Results

| User | Email Opened | Link Clicked | Credentials Entered | Reported as Phishing |
|------|-------------|-------------|--------------------|--------------------|
| testuser1 | <!-- Y/N --> | <!-- Y/N --> | <!-- Y/N --> | <!-- Y/N --> |
| testuser2 | <!-- Y/N --> | <!-- Y/N --> | <!-- Y/N --> | <!-- Y/N --> |
| testuser3 | <!-- Y/N --> | <!-- Y/N --> | <!-- Y/N --> | <!-- Y/N --> |

<!-- screenshot: per-user-results.png -->

---

## Analysis

- **Compromise rate of <!-- x% -->** would be <!-- acceptable/concerning --> in a production tenant
  - Industry benchmark: ~10–15% average click rate for well-crafted simulations
- **Report rate of <!-- x% -->** — a high report rate is the goal; train users to report, not just avoid clicking

### Training Recommendations

| User Group | Training Module | Reason |
|-----------|----------------|--------|
| Users who clicked | <!-- training name --> | <!-- reason --> |
| Users who entered credentials | <!-- training name --> | <!-- reason --> |
| All users | <!-- awareness module --> | Baseline awareness |

### Policy Adjustments Based on Results

- <!-- e.g. Increase anti-phishing threshold to 3 if many mails bypassed detection -->
- <!-- e.g. Add the payload's sending domain to the impersonation protection list -->

---

## Lessons Learned

<!-- What made the chosen payload effective? -->
<!-- How would you use simulation results to justify security investment to management? -->
<!-- What is the recommended cadence for running simulations in production? -->

## Exam Relevance

<!-- MS-500: Configure and review attack simulation training results -->
<!-- SC-900: Describe threat protection — phishing simulation -->

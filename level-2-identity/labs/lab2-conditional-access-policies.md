# Lab 2: Conditional Access Policy Set

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 2 — Identity Security |
| **Certification Target** | SC-300 |
| **Estimated Duration** | ~75 minutes |
| **Environment** | Microsoft Entra admin center |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create CA003 — Require compliant device for SharePoint & Exchange
- [ ] Create CA004 — Block high-risk sign-ins
- [ ] Create CA005 — Require phishing-resistant MFA for admins
- [ ] Create CA006 — Block sign-in from unapproved countries (with named location)
- [ ] Test each policy using the What-If tool and document results

## Prerequisites

- Lab 1 complete (CA001 and CA002 exist)
- SG-BreakGlass group with break-glass accounts

---

## Named Locations

### Allowed Countries

| Setting | Value |
|---------|-------|
| **Name** | Allowed Countries |
| **Type** | Countries location |
| **Countries included** | <!-- list your countries --> |
| **Date created** | <!-- fill in --> |

<!-- screenshot: named-location-config.png -->

---

## Policies Created

### CA003 — Require Compliant Device for SharePoint & Exchange

| Setting | Value |
|---------|-------|
| **Name** | CA003 — Require Compliant Device for SharePoint & Exchange |
| **Users — Include** | All users |
| **Users — Exclude** | Group: SG-BreakGlass |
| **Target resources** | Office 365 SharePoint Online; Office 365 Exchange Online |
| **Grant** | Require device to be marked as compliant |
| **Enable policy** | Report-only (will activate after Level 3 device enrolment) |
| **Note** | Policy created now; compliance requires Intune enrolment (Level 3) |

<!-- screenshot: policy-ca003.png -->

---

### CA004 — Block High-Risk Sign-Ins

| Setting | Value |
|---------|-------|
| **Name** | CA004 — Block High-Risk Sign-Ins |
| **Users — Include** | All users |
| **Users — Exclude** | Group: SG-BreakGlass |
| **Target resources** | All cloud apps |
| **Conditions — Sign-in risk** | High |
| **Grant** | Block access |
| **Enable policy** | On (safe to enable immediately for high-risk) |

<!-- screenshot: policy-ca004.png -->

---

### CA005 — Require Phishing-Resistant MFA for Admins

| Setting | Value |
|---------|-------|
| **Name** | CA005 — Require Phishing-Resistant MFA for Admins |
| **Users — Include** | Directory roles: Global Administrator, Security Administrator, Exchange Administrator, SharePoint Administrator, User Administrator |
| **Users — Exclude** | Group: SG-BreakGlass |
| **Target resources** | All cloud apps |
| **Grant** | Require authentication strength: Phishing-resistant MFA |
| **Enable policy** | Report-only (switch to On once admins have FIDO2/WHfB registered) |

<!-- screenshot: policy-ca005.png -->

---

### CA006 — Block Sign-In from Unapproved Countries

| Setting | Value |
|---------|-------|
| **Name** | CA006 — Block Sign-In from Unapproved Countries |
| **Users — Include** | All users |
| **Users — Exclude** | Group: SG-BreakGlass |
| **Target resources** | All cloud apps |
| **Conditions — Locations — Include** | Any location |
| **Conditions — Locations — Exclude** | Allowed Countries (named location) |
| **Grant** | Block access |
| **Enable policy** | Report-only first; monitor for 48 hours before switching On |

<!-- screenshot: policy-ca006.png -->

---

## What-If Test Results

| Scenario | User | App | Location | Policies Applied | Result |
|----------|------|-----|----------|-----------------|--------|
| Admin from approved country | testadmin | Exchange | <!-- country --> | <!-- CA005 --> | <!-- MFA required --> |
| User from unapproved country | testuser | SharePoint | <!-- country --> | <!-- CA006 --> | <!-- Blocked --> |
| High-risk sign-in simulation | testuser | All apps | Any | <!-- CA004 --> | <!-- Blocked --> |
| Break-glass from any location | breakglass1 | All apps | Any | <!-- None --> | <!-- Allowed --> |

<!-- screenshot: whatif-results-1.png -->
<!-- screenshot: whatif-results-2.png -->

## Conditional Access Policy Matrix (Full Stack)

| Policy ID | Name | Users | Apps | Conditions | Grant | Status |
|-----------|------|-------|------|------------|-------|--------|
| CA001 | Require MFA for All Users | All users | All apps | None | MFA | Report-only |
| CA002 | Block Legacy Authentication | All users | All apps | Legacy clients | Block | Report-only |
| CA003 | Require Compliant Device (SPO/EXO) | All users | SPO + EXO | None | Compliant device | Report-only |
| CA004 | Block High-Risk Sign-Ins | All users | All apps | Sign-in risk: High | Block | On |
| CA005 | Phishing-Resistant MFA for Admins | Admin roles | All apps | None | Phishing-resistant MFA | Report-only |
| CA006 | Block Unapproved Countries | All users | All apps | Location | Block | Report-only |

## Lessons Learned

<!-- Notes on policy ordering, exclusion logic, What-If surprises -->

## Exam Relevance

<!-- SC-300: Plan and implement Conditional Access policies -->
<!-- SC-300: Implement sign-in risk policies -->
<!-- SC-300: Configure authentication strengths -->

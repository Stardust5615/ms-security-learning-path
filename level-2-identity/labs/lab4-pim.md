# Lab 4: Privileged Identity Management (PIM)

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 2 — Identity Security |
| **Certification Target** | SC-300 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Entra admin center — Identity Governance → PIM |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Configure PIM settings for the Security Administrator role
- [ ] Assign testadmin as an eligible member of Security Administrator
- [ ] Test the full activation → approval → active → expiry workflow
- [ ] Screenshot every step of the flow

## Prerequisites

- Microsoft Entra ID P2 licence (included in E5)
- testadmin@<!-- domain --> account exists
- Your main admin account to serve as approver

---

## PIM Role Settings — Security Administrator

| Setting | Configured Value |
|---------|-----------------|
| **Maximum activation duration** | 1 hour |
| **On activation, require** | Azure MFA |
| **Require justification on activation** | Yes |
| **Require approval to activate** | Yes |
| **Approver(s)** | <!-- your admin account --> |
| **Allow permanent eligible assignment** | Yes |

<!-- screenshot: pim-role-settings.png -->
<!-- screenshot: pim-activation-settings.png -->
<!-- screenshot: pim-approval-settings.png -->

---

## Eligible Assignment

| Field | Value |
|-------|-------|
| **Role** | Security Administrator |
| **Member** | testadmin@<!-- domain --> |
| **Assignment type** | Eligible |
| **Duration** | Start: <!-- date --> / End: <!-- 90 days later --> |

<!-- screenshot: pim-eligible-assignment.png -->

---

## Activation Workflow

### Activation Request (as testadmin)

| Step | Timestamp | Notes |
|------|-----------|-------|
| Navigated to PIM → My roles | <!-- time --> | |
| Clicked Activate on Security Administrator | <!-- time --> | |
| Entered justification | <!-- time --> | Justification used: "<!-- text -->" |
| Request submitted | <!-- time --> | |

<!-- screenshot: pim-activation-request.png -->
<!-- screenshot: pim-justification-entry.png -->

### Approval (as main admin)

| Step | Timestamp | Notes |
|------|-----------|-------|
| Opened PIM → Approve requests | <!-- time --> | |
| Reviewed request | <!-- time --> | |
| Approved | <!-- time --> | |

<!-- screenshot: pim-pending-approval.png -->
<!-- screenshot: pim-approval-action.png -->

### Active Role Verification (as testadmin)

| Step | Timestamp | Notes |
|------|-----------|-------|
| Role became active | <!-- time --> | |
| Verified active in PIM → My roles | <!-- time --> | |
| Role expired or manually deactivated | <!-- time --> | |

<!-- screenshot: pim-role-active.png -->
<!-- screenshot: pim-role-expired.png -->

---

## Lessons Learned

<!-- What is the difference between eligible and active assignments? -->
<!-- Why should permanent active assignments be avoided for privileged roles? -->
<!-- What happened if you tried to do something as testadmin without activating the role first? -->

## Exam Relevance

<!-- SC-300: Plan and implement privileged identity management -->
<!-- SC-300: Configure PIM for Azure AD roles — settings, assignments, activation -->
<!-- SC-300: Monitor and maintain Azure AD PIM -->

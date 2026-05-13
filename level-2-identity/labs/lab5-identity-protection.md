# Lab 5: Identity Protection & Risk Policies

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 2 — Identity Security |
| **Certification Target** | SC-300 |
| **Estimated Duration** | ~45 minutes |
| **Environment** | Microsoft Entra admin center — Protection → Identity Protection |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Review the Identity Protection dashboard
- [ ] Configure the User Risk Policy (medium and above → require password change)
- [ ] Configure the Sign-in Risk Policy (medium and above → require MFA)
- [ ] Review Risky Users and Risky Sign-ins tabs
- [ ] Understand how these policies complement Conditional Access CA004

## Prerequisites

- Microsoft Entra ID P2 licence (included in E5)
- Conditional Access policies from Lab 1 and Lab 2 exist
- Understand the difference between user risk and sign-in risk

---

## Identity Protection Dashboard

| Metric | Value at Lab Start |
|--------|--------------------|
| Risky users (high) | <!-- fill in --> |
| Risky users (medium) | <!-- fill in --> |
| Risk detections (last 30 days) | <!-- fill in --> |
| Note | Dev tenants typically show no risk — document that this is expected |

<!-- screenshot: idp-dashboard.png -->

---

## User Risk Policy

| Setting | Value |
|---------|-------|
| **Users** | All users |
| **Exclude** | Break-glass accounts (breakglass1, breakglass2) |
| **User risk level** | Medium and above |
| **Access control** | Require password change |
| **Enforce policy** | On |

<!-- screenshot: user-risk-policy.png -->

---

## Sign-in Risk Policy

| Setting | Value |
|---------|-------|
| **Users** | All users |
| **Exclude** | Break-glass accounts |
| **Sign-in risk level** | Medium and above |
| **Access control** | Require multi-factor authentication |
| **Enforce policy** | On |

<!-- screenshot: signin-risk-policy.png -->

---

## Risk Events Review

| Tab | Items Found | Notes |
|-----|-------------|-------|
| Risky users | <!-- count --> | <!-- expected to be 0 in a new dev tenant --> |
| Risky sign-ins | <!-- count --> | |
| Risk detections | <!-- count --> | |

<!-- screenshot: risky-users-tab.png -->
<!-- screenshot: risky-signins-tab.png -->

---

## Relationship to Conditional Access

| Policy | Where Configured | Trigger |
|--------|-----------------|---------|
| CA004 — Block High-Risk Sign-Ins | Conditional Access | Sign-in risk: High |
| Sign-in Risk Policy (here) | Identity Protection | Sign-in risk: Medium+ → MFA |
| User Risk Policy (here) | Identity Protection | User risk: Medium+ → Password change |

> CA004 (in Conditional Access) blocks high-risk sign-ins immediately.
> Identity Protection policies handle medium risk with a softer response (MFA or password change).

---

## Lessons Learned

<!-- What is the difference between user risk and sign-in risk? -->
<!-- Why are break-glass accounts excluded from risk policies? -->
<!-- What would happen to a user with a High risk level? -->

## Exam Relevance

<!-- SC-300: Implement and manage Azure AD Identity Protection -->
<!-- SC-300: Configure risk-based Conditional Access policies -->

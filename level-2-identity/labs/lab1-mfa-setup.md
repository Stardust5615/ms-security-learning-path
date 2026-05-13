# Lab 1: MFA & Passwordless Setup

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 2 — Identity Security |
| **Certification Target** | SC-300 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Entra admin center + Microsoft 365 E5 tenant |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create CA001 — Require MFA for All Users (report-only first)
- [ ] Create CA002 — Block Legacy Authentication
- [ ] Register MFA for a test user via Microsoft Authenticator
- [ ] Validate break-glass exclusion using the What-If tool
- [ ] Promote both policies from Report-only to On after monitoring

## Prerequisites

- Global Administrator access to Entra admin center
- Test users created (testuser, testadmin, breakglass1, breakglass2)
- SG-BreakGlass group created and break-glass accounts added
- Microsoft Authenticator app installed on your phone

---

## Policies Created

### CA001 — Require MFA for All Users

| Setting | Value |
|---------|-------|
| **Name** | CA001 — Require MFA for All Users |
| **Users — Include** | All users |
| **Users — Exclude** | Directory role: Global Administrator; Group: SG-BreakGlass |
| **Target resources** | All cloud apps |
| **Conditions** | None |
| **Grant** | Require multi-factor authentication |
| **Session** | Default |
| **Enable policy** | Report-only → On (date switched: <!-- fill in -->) |

<!-- screenshot: policy-ca001-config.png -->
<!-- screenshot: policy-ca001-grant.png -->

---

### CA002 — Block Legacy Authentication

| Setting | Value |
|---------|-------|
| **Name** | CA002 — Block Legacy Authentication |
| **Users — Include** | All users |
| **Users — Exclude** | Group: SG-BreakGlass |
| **Target resources** | All cloud apps |
| **Conditions — Client apps** | Exchange ActiveSync clients; Other clients |
| **Grant** | Block access |
| **Enable policy** | Report-only → On (date switched: <!-- fill in -->) |

<!-- screenshot: policy-ca002-config.png -->
<!-- screenshot: policy-ca002-client-apps.png -->

---

## Test Results

### MFA Registration Test

| Field | Detail |
|-------|--------|
| **User tested** | testuser@<!-- domain --> |
| **MFA method registered** | Microsoft Authenticator app |
| **MFA prompt appeared on login** | Yes / No |
| **Date tested** | <!-- fill in --> |

<!-- screenshot: mfa-registration-flow.png -->
<!-- screenshot: mfa-prompt-at-login.png -->
<!-- screenshot: successful-mfa-sign-in.png -->

---

### What-If Tool Results

**Scenario 1 — testuser signing in to Exchange Online from unknown location**

| Field | Result |
|-------|--------|
| User | testuser |
| App | Exchange Online |
| Location | Unknown / Outside named location |
| Policies applied | <!-- list CA policies that applied --> |
| Grant result | <!-- MFA required / Blocked / Allowed --> |

<!-- screenshot: whatif-testuser.png -->

**Scenario 2 — breakglass1 signing in to Exchange Online**

| Field | Result |
|-------|--------|
| User | breakglass1 |
| App | Exchange Online |
| Policies applied | <!-- None — break-glass should be excluded --> |
| Grant result | <!-- Should be: Allowed without MFA --> |

<!-- screenshot: whatif-breakglass.png -->

---

## Lessons Learned

<!-- What went well, what was confusing, what you'd do differently in production -->

## Exam Relevance

<!-- SC-300: Plan and implement multi-factor authentication -->
<!-- SC-300: Implement and manage Conditional Access -->
<!-- SC-300: Plan and implement authentication methods -->

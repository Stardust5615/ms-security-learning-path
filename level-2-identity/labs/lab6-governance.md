# Lab 6: Access Reviews & Entitlement Management

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 2 — Identity Security |
| **Certification Target** | SC-300 |
| **Estimated Duration** | ~75 minutes |
| **Environment** | Microsoft Entra admin center — Identity Governance |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create and complete a one-time Access Review for the SG-Admins group
- [ ] Review and approve/deny members via the My Access portal
- [ ] Create an Access Package for "Security Team Access"
- [ ] Test the self-service request flow as a test user
- [ ] Approve the request and verify group membership

## Prerequisites

- Microsoft Entra ID P2 licence (included in E5)
- SG-Admins group with test users
- SG-ComplianceTeam group created
- testuser account to perform the access request

---

## Part A: Access Review

### Review Configuration

| Setting | Value |
|---------|-------|
| **Review type** | Teams + Groups |
| **Scope** | SG-Admins group |
| **Reviewers** | <!-- your admin account --> |
| **Duration** | 7 days |
| **Recurrence** | One time (lab) |
| **Auto-apply results** | No (manual for lab — observe the results first) |

<!-- screenshot: access-review-config.png -->

### Review Results

| Member | Decision | Justification |
|--------|----------|--------------|
| <!-- user 1 --> | Approve / Deny | <!-- reason --> |
| <!-- user 2 --> | Approve / Deny | <!-- reason --> |

<!-- screenshot: myaccess-review-portal.png -->
<!-- screenshot: review-completed.png -->

---

## Part B: Access Package

### Access Package Configuration

| Setting | Value |
|---------|-------|
| **Name** | Security Team Access |
| **Catalog** | General |
| **Resource roles** | SG-ComplianceTeam — Member |
| **Policy name** | Request policy — approval required |
| **Requestors** | All members of your directory |
| **Approval required** | Yes |
| **Approver** | <!-- your admin account --> |
| **Access duration** | <!-- e.g. 90 days or no expiry --> |
| **Package enabled** | Yes |

<!-- screenshot: access-package-config.png -->
<!-- screenshot: access-package-policy.png -->

### Self-Service Request Test

| Step | User | Result |
|------|------|--------|
| Navigate to https://myaccess.microsoft.com | testuser | <!-- found package --> |
| Request "Security Team Access" | testuser | <!-- request submitted --> |
| Approve request | admin | <!-- approved --> |
| Verify group membership | admin | <!-- testuser added to SG-ComplianceTeam --> |

<!-- screenshot: myaccess-request-portal.png -->
<!-- screenshot: access-package-request-submitted.png -->
<!-- screenshot: approval-notification.png -->
<!-- screenshot: group-membership-verified.png -->

---

## Lessons Learned

<!-- What is the difference between an access review and an access package? -->
<!-- When would you use entitlement management over direct group assignment? -->
<!-- What lifecycle management features exist (joiner/mover/leaver workflows)? -->

## Exam Relevance

<!-- SC-300: Plan and implement access reviews -->
<!-- SC-300: Plan and implement entitlement management — access packages, catalogs, policies -->
<!-- SC-300: Implement identity governance — lifecycle workflows -->

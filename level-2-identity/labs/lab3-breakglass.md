# Lab 3: Break-Glass Account Configuration

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 2 — Identity Security |
| **Certification Target** | SC-300 |
| **Estimated Duration** | ~30 minutes |
| **Environment** | Microsoft Entra admin center |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Verify both break-glass accounts exist
- [ ] Assign permanent Global Administrator to both accounts
- [ ] Confirm both accounts are excluded from ALL Conditional Access policies
- [ ] Document password storage method
- [ ] Configure sign-in monitoring alerts
- [ ] Validate using What-If that no CA policies apply

## What Are Break-Glass Accounts?

Break-glass accounts are emergency administrator accounts used only when all normal admin access is lost (e.g., MFA system failure, tenant misconfiguration locking out all admins). They must:
- Hold permanent Global Admin (not eligible via PIM)
- Be excluded from ALL Conditional Access policies
- Use extremely strong passwords stored in two separate secure locations
- Never be used for day-to-day administration
- Trigger an alert the instant they are used

---

## Account Configuration

| Account | Username | Role Assigned | CA Excluded | Password Storage |
|---------|----------|---------------|-------------|-----------------|
| Break-glass 1 | breakglass1@<!-- domain --> | Global Administrator (permanent) | Yes — SG-BreakGlass | <!-- describe method, not actual password --> |
| Break-glass 2 | breakglass2@<!-- domain --> | Global Administrator (permanent) | Yes — SG-BreakGlass | <!-- describe method --> |

<!-- screenshot: breakglass1-role-assignment.png -->
<!-- screenshot: breakglass2-role-assignment.png -->

---

## Conditional Access Exclusion Verification

**What-If Result — breakglass1 signing in to any app from any location:**

| Field | Expected | Actual |
|-------|----------|--------|
| Policies applied | None | <!-- result --> |
| Grant result | Allowed (no conditions) | <!-- result --> |

<!-- screenshot: whatif-breakglass-no-policies.png -->

---

## Monitoring Configuration

| Setting | Value |
|---------|-------|
| **Alert type** | Sign-in activity alert |
| **Accounts monitored** | breakglass1, breakglass2 |
| **Alert destination** | <!-- email / Sentinel rule in Level 6 --> |
| **Note** | A more robust Sentinel analytics rule will be built in Level 6 |

<!-- screenshot: monitoring-alert-config.png -->

---

## Lessons Learned

<!-- What would happen if break-glass accounts didn't exist? What's the risk? -->
<!-- How often should break-glass accounts be tested? -->

## Exam Relevance

<!-- SC-300: Plan and implement privileged access — break-glass accounts -->
<!-- SC-300: Manage Conditional Access policy exclusions -->

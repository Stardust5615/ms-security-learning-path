# Lab 1: Intune Enrollment — Enrollment Steps

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 3 — Endpoint Security |
| **Certification Target** | MD-102 |
| **Estimated Duration** | ~60 minutes (plus 30 min for policy evaluation) |
| **Environment** | Windows 10/11 device or VM + Microsoft Intune admin center |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Enrol a Windows 10/11 device into Intune
- [ ] Verify the device appears in the Intune device inventory
- [ ] Create and assign the WIN-Compliance-Baseline policy
- [ ] Review the compliance state of the enrolled device

## Prerequisites

- Windows 10/11 physical device or VM
  - VM option: Windows 11 Enterprise 90-day eval ISO from Microsoft Evaluation Center
  - Hypervisor: Hyper-V (free on Windows 10/11 Pro) or VirtualBox
- testuser@<!-- domain --> account with an Intune licence assigned

---

## Device Enrolment

### Enrolment Method: Azure AD Join via Settings

| Step | Action | Result |
|------|--------|--------|
| 1 | Settings → Accounts → Access work or school → Connect | <!-- joined --> |
| 2 | Signed in as testuser@<!-- domain --> | |
| 3 | Followed enrolment prompts | |
| 4 | Waited 5–10 minutes for enrolment | |

<!-- screenshot: settings-access-work-school.png -->
<!-- screenshot: enrolment-in-progress.png -->
<!-- screenshot: enrolment-complete.png -->

### Verification in Intune Admin Center

| Field | Value |
|-------|-------|
| **Device name** | <!-- fill in --> |
| **OS** | <!-- e.g. Windows 11 Enterprise 22H2 --> |
| **Enrolment date** | <!-- fill in --> |
| **Enrolled by** | testuser@<!-- domain --> |
| **Compliance state** | <!-- Compliant / Not compliant / Pending --> |
| **Management agent** | MDM |

<!-- screenshot: intune-device-inventory.png -->
<!-- screenshot: device-detail-page.png -->

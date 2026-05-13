# Lab 4: Teams & SharePoint External Sharing Controls

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 4 — Email, Collaboration & Cloud App Security |
| **Certification Target** | MS-500 |
| **Estimated Duration** | ~45 minutes |
| **Environment** | SharePoint admin center + Teams admin center |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Review and document current external sharing settings for SharePoint and OneDrive
- [ ] Configure sharing to "New and existing guests" (not "Anyone")
- [ ] Set default link type to "Specific people" and default permission to "View"
- [ ] Review Teams external access settings and document your recommendation

---

## SharePoint & OneDrive Sharing Settings

### Current State (Before Changes)

| Setting | SharePoint (Before) | OneDrive (Before) |
|---------|--------------------|--------------------|
| Sharing level | <!-- Anyone / New and existing guests / Existing guests / Only people in your org --> | |
| Default link type | <!-- Anyone / People in your org / Specific people --> | |
| Default link permission | <!-- View / Edit --> | |

<!-- screenshot: sharepoint-sharing-before.png -->

### Configured State (After Lab)

| Setting | SharePoint (After) | OneDrive (After) | Rationale |
|---------|--------------------|-----------------|-----------|
| Sharing level | New and existing guests | Existing guests only | OneDrive should be more restrictive than SharePoint |
| Default link type | Specific people | Specific people | Prevents accidental "anyone" link creation |
| Default link permission | View | View | Principle of least privilege |

<!-- screenshot: sharepoint-sharing-after.png -->
<!-- screenshot: onedrive-sharing-after.png -->

---

## Teams External Access Settings

| Setting | Current Value | Recommendation | Rationale |
|---------|--------------|---------------|-----------|
| Allow external Teams users to find and contact internal users | <!-- On/Off --> | <!-- your recommendation --> | <!-- reason --> |
| Allow communication with Skype users | <!-- On/Off --> | <!-- Off in most orgs --> | Skype is legacy; increased attack surface |
| Specific domains blocked/allowed | <!-- domains --> | <!-- recommendation --> | |

<!-- screenshot: teams-external-access.png -->

---

## Risk Assessment

| Sharing Risk | Impact | Current Mitigations |
|-------------|--------|-------------------|
| "Anyone" links expose files to unauthenticated users | High | <!-- now restricted --> |
| Guest users can share content further | Medium | |
| Phishing via external Teams messages | Medium | |

---

## Lessons Learned

<!-- Why should OneDrive have stricter sharing settings than SharePoint? -->
<!-- What is the difference between external access and guest access in Teams? -->
<!-- How would you audit existing "Anyone" links already shared before your policy change? -->

## Exam Relevance

<!-- MS-500: Manage Microsoft Teams security — external access, guest access -->
<!-- MS-500: Manage SharePoint Online security — sharing settings, sensitivity labels -->

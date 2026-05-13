# Lab 5: eDiscovery Case — Project Apollo

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 5 — Data Security & Compliance |
| **Certification Target** | SC-400 |
| **Estimated Duration** | ~90 minutes |
| **Environment** | Microsoft Purview → eDiscovery → Standard |
| **Difficulty** | Advanced |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Seed test data (emails + documents) containing the keyword "Project Apollo"
- [ ] Create an eDiscovery case and place a legal hold on a custodian
- [ ] Run a content search across all mailboxes and SharePoint sites
- [ ] Export search results
- [ ] Release the hold and close the case

## Prerequisites

- At least 2 test user mailboxes with content
- testuser@<!-- domain --> and testadmin@<!-- domain --> accounts
- eDiscovery Manager role assigned to your admin account

---

## Case Details

| Field | Value |
|-------|-------|
| **Case name** | Lab — Project Apollo Investigation |
| **Case number** | <!-- auto-generated --> |
| **Created** | <!-- date --> |
| **eDiscovery Manager** | <!-- your admin account --> |
| **Purpose** | Demonstrate full eDiscovery Standard workflow for a fictional internal investigation |

<!-- screenshot: case-created.png -->

---

## Legal Hold

| Setting | Value |
|---------|-------|
| **Hold name** | Hold — testuser mailbox |
| **Custodians** | testuser@<!-- domain --> |
| **Locations** | testuser mailbox; testuser OneDrive |
| **Keywords** | "Project Apollo" |
| **Hold created** | <!-- date/time --> |

<!-- screenshot: hold-configuration.png -->
<!-- screenshot: hold-created-confirmation.png -->

> **What the hold does:** Any content matching the keyword "Project Apollo" in testuser's mailbox and OneDrive is preserved and cannot be deleted — even by the user. This is the legal hold.

---

## Content Search

| Setting | Value |
|---------|-------|
| **Search name** | Search — Project Apollo |
| **Locations** | All mailboxes + all SharePoint sites |
| **Keywords** | "Project Apollo" |
| **Date range** | <!-- fill in or leave blank --> |
| **Search started** | <!-- date/time --> |
| **Search completed** | <!-- date/time --> |

### Search Results

| Metric | Value |
|--------|-------|
| Total items found | <!-- count --> |
| Total size | <!-- MB/GB --> |
| Mailbox items | <!-- count --> |
| SharePoint/OneDrive items | <!-- count --> |

<!-- screenshot: content-search-config.png -->
<!-- screenshot: search-results-summary.png -->
<!-- screenshot: sample-items-review.png -->

---

## Export

| Setting | Value |
|---------|-------|
| **Export format** | PST for email; native for documents |
| **Items included** | All items including unrecognised formats, encrypted, and unindexed |
| **Export job name** | <!-- auto-generated --> |
| **Items exported** | <!-- count --> |
| **Export file size** | <!-- size --> |

<!-- screenshot: export-config.png -->
<!-- screenshot: export-job-status.png -->

---

## Process Timeline

| Step | Timestamp | Notes |
|------|-----------|-------|
| Test data seeded (emails + documents sent) | <!-- time --> | |
| Case created | <!-- time --> | |
| Hold placed on testuser | <!-- time --> | |
| Content search executed | <!-- time --> | |
| Results reviewed | <!-- time --> | |
| Export completed | <!-- time --> | |
| Hold released | <!-- time --> | |
| Case closed | <!-- time --> | |

---

## Lessons Learned

- **What went smoothly:** <!-- notes -->
- **What was difficult:** <!-- notes -->
- **How long the full process took:** <!-- notes -->
- **How is eDiscovery Standard different from eDiscovery Premium?** <!-- answer: Premium has custodian management, review sets, analytics, legal hold notifications -->
- **What is the difference between a hold and a retention policy?** <!-- holds are case-specific and override retention; retention is org-wide lifecycle policy -->

## Exam Relevance

<!-- SC-400: Implement eDiscovery — content search, hold, export -->
<!-- SC-400: Manage a content search — locations, keywords, conditions -->
<!-- SC-400: Manage eDiscovery cases — Standard vs Premium -->

# Lab 4: Records Management & Retention

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 5 — Data Security & Compliance |
| **Certification Target** | SC-400 |
| **Estimated Duration** | ~75 minutes |
| **Environment** | Microsoft Purview → Records management → File plan |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Design a file plan for Contoso Ltd with 5 record categories
- [ ] Create 3 retention labels (3-year auto-delete, 7-year review, permanent record)
- [ ] Publish labels to all locations
- [ ] Apply a label to a SharePoint library and verify it's locked as a record
- [ ] Attempt to delete a labelled record — verify it's blocked

---

## File Plan — Contoso Ltd

| Category | Examples | Retention Period | Trigger | Disposition |
|----------|----------|-----------------|---------|------------|
| Contracts | Vendor agreements, SOWs | 7 years | After contract expiry | Disposition review then delete |
| Financial Records | Invoices, budgets, audits | 7 years | Creation date | Auto-delete |
| HR Records | Offer letters, performance reviews | 5 years | After employee termination | Disposition review then delete |
| Legal | Litigation files, legal opinions | 10 years | Creation date | Permanent — never delete |
| General Correspondence | Emails, memos | 3 years | Creation date | Auto-delete |

---

## Retention Labels Created

### Label 1: Retain — 3 Years — Delete

| Setting | Value |
|---------|-------|
| **Label name** | Retain — 3 Years — Delete |
| **Retention period** | 3 years |
| **Retention trigger** | When items were created |
| **At end of retention** | Delete items automatically |
| **Mark as record** | No — not a record |
| **Assigned to file plan categories** | General Correspondence |

<!-- screenshot: label-3yr-delete.png -->

### Label 2: Retain — 7 Years — Review

| Setting | Value |
|---------|-------|
| **Label name** | Retain — 7 Years — Review |
| **Retention period** | 7 years |
| **Retention trigger** | When items were last modified |
| **At end of retention** | Start a disposition review |
| **Mark as record** | Yes — A record (locks the item — cannot be modified or deleted) |
| **Disposition reviewers** | <!-- your admin account --> |
| **Assigned to file plan categories** | Contracts, Financial Records, HR Records |

<!-- screenshot: label-7yr-review.png -->
<!-- screenshot: label-7yr-disposition.png -->

### Label 3: Retain — Permanent Record

| Setting | Value |
|---------|-------|
| **Label name** | Retain — Permanent Record |
| **Retention period** | Retain items forever |
| **At end of retention** | N/A — permanent |
| **Mark as record** | Yes — A regulatory record (strongest protection — cannot be removed even by admins) |
| **Assigned to file plan categories** | Legal |

<!-- screenshot: label-permanent-record.png -->

---

## Label Policy (Publishing)

| Setting | Value |
|---------|-------|
| **Policy name** | Retention Labels — Standard |
| **Labels published** | All 3 retention labels |
| **Locations** | SharePoint, OneDrive, Exchange |

<!-- screenshot: retention-label-policy.png -->

---

## SharePoint Application Test

| Test | Expected | Actual |
|------|----------|--------|
| Create a SharePoint "Contracts" library | Library created | <!-- result --> |
| Set "Retain — 7 Years — Review" as the default label for the library | Label applied automatically to new items | <!-- result --> |
| Upload a test document | Label "Retain — 7 Years — Review" applied | <!-- result --> |
| Attempt to delete the labelled document | Blocked — item is a record | <!-- result --> |
| Attempt to modify the labelled document | Blocked or only minor edits allowed | <!-- result --> |

<!-- screenshot: sharepoint-library-default-label.png -->
<!-- screenshot: document-with-label.png -->
<!-- screenshot: delete-blocked-record.png -->

---

## Disposition Review Process (Documentation)

Even though items in a new tenant won't reach end-of-retention during this lab, document the process:

1. When a labelled item reaches the end of its retention period, it appears in **Records management → Disposition**
2. The designated reviewer receives an email notification
3. The reviewer must: Approve disposal (item is deleted) OR Extend retention OR Relabel the item
4. Items not actioned within the review period are auto-disposed (if configured) or held indefinitely

<!-- screenshot: disposition-tab-overview.png -->

---

## Lessons Learned

<!-- What is the difference between a record and a regulatory record? -->
<!-- Can a user remove a retention label from an item they labelled themselves? -->
<!-- What happens to an item under legal hold if its retention period expires? -->

## Exam Relevance

<!-- SC-400: Implement retention labels and retention policies -->
<!-- SC-400: Implement records management — file plan, records vs regulatory records, disposition -->

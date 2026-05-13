# Lab 1: Sensitivity Labels — Classification & Encryption

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 5 — Data Security & Compliance |
| **Certification Target** | SC-400 |
| **Estimated Duration** | ~75 minutes |
| **Environment** | Microsoft Purview compliance portal (https://compliance.microsoft.com) |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create 4 sensitivity labels: Public, Internal, Confidential, Highly Confidential
- [ ] Configure encryption and content marking for Confidential and Highly Confidential
- [ ] Publish all 4 labels via a label policy with "Internal" as the default
- [ ] Test labels in Microsoft Word (web or desktop)
- [ ] Verify the justification prompt appears when downgrading a label

---

## Label Taxonomy

| Label | Encryption | Content Marking | Auto-label | Typical Use |
|-------|-----------|----------------|------------|------------|
| Public | None | None | No | Press releases, public docs |
| Internal | None | Header: "INTERNAL — Do Not Share Externally" | Default for all new content | Day-to-day work |
| Confidential | Yes — org-wide viewer, specific Co-Author | Header + Watermark (red) | Credit card, IBAN, SSN (Lab 2) | Finance, HR, legal |
| Highly Confidential | Yes — admin + testadmin only | Header + Watermark (red) | Manual only | Board, M&A, disciplinary |

---

## Label Configurations

### Label: Public

| Setting | Value |
|---------|-------|
| **Name** | Public |
| **Display name** | Public |
| **Description for users** | Information that can be freely shared externally |
| **Scope** | Items (Files, Emails) |
| **Encryption** | None |
| **Content marking** | None |

<!-- screenshot: label-public.png -->

### Label: Internal

| Setting | Value |
|---------|-------|
| **Name** | Internal |
| **Display name** | Internal |
| **Description for users** | Information for internal use only — not for external sharing |
| **Scope** | Items (Files, Emails) |
| **Encryption** | None |
| **Content marking — Header** | "INTERNAL — Do Not Share Externally" / Font 10 / Gray |

<!-- screenshot: label-internal.png -->

### Label: Confidential

| Setting | Value |
|---------|-------|
| **Name** | Confidential |
| **Description for users** | Sensitive information — restricted to authorised employees |
| **Scope** | Items (Files, Emails) |
| **Encryption** | Enabled — Assign permissions now |
| **User access expires** | Never |
| **Allow offline access** | 7 days |
| **Assign permissions — Tenant domain** | Viewer (View, Open, Read) |
| **Assign permissions — Co-Author group** | <!-- specific user/group --> Co-Author |
| **Content marking — Header** | "CONFIDENTIAL" / Font 12 / Red |
| **Content marking — Watermark** | "CONFIDENTIAL" / Red / Size 48 |

<!-- screenshot: label-confidential-encryption.png -->
<!-- screenshot: label-confidential-marking.png -->

### Label: Highly Confidential

| Setting | Value |
|---------|-------|
| **Name** | Highly Confidential |
| **Description for users** | Most sensitive — board, legal, M&A, HR disciplinary |
| **Scope** | Items (Files, Emails) |
| **Encryption** | Enabled — Assign permissions now |
| **Allow offline access** | 1 day |
| **Assign permissions** | Admin + testadmin only — Co-Owner |
| **Content marking — Header** | "HIGHLY CONFIDENTIAL" / Red |
| **Content marking — Watermark** | "HIGHLY CONFIDENTIAL" / Red / Size 48 |

<!-- screenshot: label-highly-confidential-encryption.png -->
<!-- screenshot: label-highly-confidential-marking.png -->

---

## Label Policy: Standard Label Policy

| Setting | Value |
|---------|-------|
| **Policy name** | Standard Label Policy |
| **Labels included** | Public, Internal, Confidential, Highly Confidential |
| **Published to** | All users |
| **Default label for documents** | Internal |
| **Default label for emails** | Internal |
| **Require users to apply a label** | Yes |
| **Require justification to remove or lower a label** | Yes |

<!-- screenshot: label-policy-settings.png -->
<!-- screenshot: label-policy-default.png -->

---

## Test Results

| Test | Expected | Actual |
|------|----------|--------|
| Open Word — Sensitivity button visible in ribbon | Yes (after 15–30 min propagation) | <!-- result --> |
| Apply "Confidential" label — header and watermark appear | Yes | <!-- result --> |
| Save to OneDrive as Confidential — try to share externally | Share blocked or recipient can't open | <!-- result --> |
| Change label from Confidential → Public | Justification prompt appears | <!-- result --> |

<!-- screenshot: word-sensitivity-button.png -->
<!-- screenshot: confidential-label-applied-word.png -->
<!-- screenshot: watermark-in-document.png -->
<!-- screenshot: justification-prompt.png -->
<!-- screenshot: external-share-blocked.png -->

---

## Lessons Learned

<!-- Why is "Internal" a better default than "Public"? -->
<!-- What is the difference between "Assign permissions now" and "Let users assign permissions"? -->
<!-- Why should Highly Confidential NOT allow Do Not Forward? -->

## Exam Relevance

<!-- SC-400: Create and configure sensitivity labels -->
<!-- SC-400: Publish sensitivity labels and label policies -->
<!-- SC-400: Apply sensitivity labels to Microsoft 365 services -->

# Lab 1: Anti-Phishing, Safe Attachments & Safe Links

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 4 — Email, Collaboration & Cloud App Security |
| **Certification Target** | MS-500 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Defender portal → Email & collaboration → Policies & rules → Threat policies |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Configure the Anti-Phishing policy with impersonation protection and mailbox intelligence
- [ ] Create a Safe Attachments policy in Dynamic Delivery mode
- [ ] Create a Safe Links policy with URL tracking enabled
- [ ] Document the rationale for each key setting

---

## Anti-Phishing Policy

| Setting | Value | Rationale |
|---------|-------|-----------|
| **Policy target** | All recipients in your domain | |
| **Phishing threshold** | 2 — Aggressive | Lab tenant; in production use 3 |
| **Enable users to protect** | Yes — admin + testadmin | Protect high-value accounts from impersonation |
| **Enable domains to protect** | Yes — your tenant domain | Protect against domain spoofing |
| **If impersonated user detected** | Quarantine | Strongest action for lab |
| **If impersonated domain detected** | Quarantine | |
| **Safety tips** | All enabled | Helps users identify suspicious mail |
| **Mailbox intelligence** | Enabled | Learns normal sending patterns per user |
| **Mailbox intelligence impersonation protection** | Enabled | Acts on intelligence-based detections |

<!-- screenshot: antiphishing-policy-threshold.png -->
<!-- screenshot: antiphishing-impersonation-users.png -->
<!-- screenshot: antiphishing-impersonation-domains.png -->
<!-- screenshot: antiphishing-actions.png -->
<!-- screenshot: antiphishing-safety-tips.png -->

---

## Safe Attachments Policy

| Setting | Value | Rationale |
|---------|-------|-----------|
| **Policy name** | Safe Attachments — All Users | |
| **Target** | All recipients in your domain | |
| **Action** | Dynamic Delivery | Delivers email immediately; replaces attachment with placeholder while scanning; restores clean attachment. No email delay. |
| **Redirect** | Enabled | Malicious attachments forwarded to admin mailbox for review |
| **Redirect address** | <!-- admin@domain --> | |

<!-- screenshot: safe-attachments-policy.png -->
<!-- screenshot: safe-attachments-dynamic-delivery.png -->

---

## Safe Links Policy

| Setting | Value | Rationale |
|---------|-------|-----------|
| **Policy name** | Safe Links — All Users | |
| **Target** | All recipients | |
| **Check URLs in email** | Enabled | Core protection |
| **Apply Safe Links to email sent within organisation** | Enabled | Internal phishing is real |
| **Track when users click protected links** | Enabled (do NOT disable) | Required for investigation — must know who clicked what |
| **Do not let users click through to original URL** | Enabled | Prevents bypassing Safe Links on known-bad URLs |
| **Apply to Microsoft Teams** | Enabled | Phishing via Teams links is common |
| **Real-time URL scanning** | Enabled | Catches zero-day links not yet in the list |

<!-- screenshot: safe-links-policy.png -->
<!-- screenshot: safe-links-url-settings.png -->
<!-- screenshot: safe-links-teams.png -->

---

## Test Results

| Test | Expected | Actual |
|------|----------|--------|
| Send email with EICAR attachment — does Safe Attachments intercept? | Attachment quarantined or replaced | <!-- result --> |
| Send email with known-bad URL — does Safe Links rewrite it? | URL rewritten to safe-links prefix | <!-- result --> |
| Verify Dynamic Delivery placeholder appears | Email delivered, attachment shows "scanning" | <!-- result --> |

<!-- screenshot: email-with-safe-links-rewrite.png -->
<!-- screenshot: dynamic-delivery-placeholder.png -->

---

## Lessons Learned

<!-- Why is Dynamic Delivery preferred over Block for Safe Attachments in most tenants? -->
<!-- Why should you never disable "track when users click" in Safe Links? -->
<!-- How does mailbox intelligence improve impersonation detection over a static protected users list? -->

## Exam Relevance

<!-- MS-500: Implement and manage Microsoft Defender for Office 365 -->
<!-- SC-300: Configure anti-phishing, Safe Attachments, Safe Links -->

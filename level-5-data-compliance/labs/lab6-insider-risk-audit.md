# Lab 6: Insider Risk Management & Audit Log Review

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 5 — Data Security & Compliance |
| **Certification Target** | SC-400 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Purview → Insider risk management + Audit |
| **Difficulty** | Advanced |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Complete the Insider Risk Management setup wizard
- [ ] Configure relevant risk indicators
- [ ] Create an "IRM — Departing User Data Theft" policy
- [ ] Review the IRM dashboard
- [ ] Run an audit log search for testuser's file activity (last 7 days)
- [ ] Export audit results to CSV and identify any interesting patterns

## Prerequisites

- Microsoft 365 E5 Compliance or Insider Risk Management licence (included in E5)
- Microsoft Purview audit logging enabled (Settings → Audit)

---

## Part A: Insider Risk Management Setup

### Prerequisites Check

| Prerequisite | Status |
|-------------|--------|
| Audit logging enabled in Purview | <!-- Yes/No --> |
| Microsoft 365 HR connector | <!-- Not required for lab — note if skipped --> |
| Insider Risk Management role assigned | <!-- Yes/No --> |

### Indicators Configured

| Indicator | Enabled | Rationale |
|-----------|---------|-----------|
| Downloading content from SharePoint | Yes | High-exfiltration signal |
| Sending email with attachments to external recipients | Yes | Data exfiltration via email |
| File copied to USB (if endpoint DLP active) | Yes | Removable media risk |
| File uploaded to cloud (if endpoint DLP active) | Yes | Cloud exfiltration risk |

<!-- screenshot: irm-indicator-settings.png -->

### Policy Configuration

| Setting | Value |
|---------|-------|
| **Policy name** | IRM — Departing User Data Theft |
| **Template** | Data theft by departing users |
| **Priority user groups** | None (lab — in production: executives, finance, R&D) |
| **Indicators** | All enabled indicators above |
| **Policy timeframe** | Default |

<!-- screenshot: irm-policy-config.png -->
<!-- screenshot: irm-policy-created.png -->

### IRM Dashboard Review

| Metric | Value |
|--------|-------|
| Alerts (last 30 days) | <!-- count — expected 0 in new tenant --> |
| Cases open | <!-- count --> |
| Policy matches | <!-- count --> |
| Note | Dev tenants typically have no IRM alerts — document that this is expected and explain what would trigger an alert |

<!-- screenshot: irm-dashboard.png -->

---

## Part B: Audit Log Review

### Audit Log Search Configuration

| Setting | Value |
|---------|-------|
| **Date range** | Last 7 days |
| **Activities searched** | Accessed file; Downloaded file; Sent email |
| **User filter** | testuser@<!-- domain --> |

<!-- screenshot: audit-search-config.png -->

### Audit Log Results

| Activity | Count | Most Recent Timestamp | Notable Findings |
|----------|-------|----------------------|-----------------|
| File accessed | <!-- n --> | <!-- time --> | <!-- notes --> |
| File downloaded | <!-- n --> | <!-- time --> | <!-- notes --> |
| Email sent | <!-- n --> | <!-- time --> | <!-- notes --> |
| Other | <!-- n --> | | |

<!-- screenshot: audit-search-results.png -->

### Interesting Patterns Identified

| Pattern | Significance | Action Required |
|---------|-------------|----------------|
| <!-- e.g. Large download spike at 11pm --> | <!-- unusual off-hours activity --> | <!-- investigate --> |
| | | |

### CSV Export

<!-- Export results: Audit → Export. File saved as: audit-export-testuser-[date].csv -->
<!-- screenshot: audit-csv-export.png -->

---

## Audit Log Standard vs Premium

| Feature | Standard | Premium |
|---------|---------|---------|
| Retention period | 90 days | Up to 10 years |
| High-value events (e.g. MailItemsAccessed) | No | Yes |
| Log bandwidth | Lower priority | Higher priority |
| Required licence | Microsoft 365 E3 | Microsoft 365 E5 / add-on |

---

## Lessons Learned

<!-- What types of activities does IRM detect that Conditional Access does not? -->
<!-- What is the difference between an IRM alert and an IRM case? -->
<!-- Why is the "Departing User Data Theft" template particularly important? -->
<!-- What would you do differently in production vs this lab setup? -->

## Exam Relevance

<!-- SC-400: Implement insider risk management — policies, indicators, case management -->
<!-- SC-400: Implement and manage Microsoft Purview Audit -->
<!-- SC-400: Distinguish Audit Standard vs Audit Premium -->

# Lab 3: Zero Trust Gap Analysis

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 1 — Security Fundamentals |
| **Certification Target** | SC-900 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft 365 E5 Developer Tenant + Microsoft Zero Trust Assessment |
| **Difficulty** | Beginner |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Complete the Microsoft Zero Trust Assessment for your dev tenant
- [ ] Document the current state of all 6 Zero Trust pillars
- [ ] Identify gaps in each pillar
- [ ] Produce a prioritised remediation plan that maps to future levels

## Prerequisites

- Microsoft 365 E5 tenant with admin access
- Complete Lab 1 first (Secure Score gives context)

## Steps

### Step 1: Take the Microsoft Zero Trust Assessment

<!-- URL: https://learn.microsoft.com/en-us/security/zero-trust/zero-trust-assessment -->
<!-- Answer based on your dev tenant's CURRENT state — most will be "no" or "not implemented" -->

### Step 2: Document each pillar

<!-- Work through each section below honestly -->

---

## Pillar Assessment

### 1. Identity

- [ ] MFA enabled for all users
- [ ] Conditional Access policies configured
- [ ] Identity Protection enabled
- [ ] PIM configured for privileged roles
- [ ] Legacy authentication blocked

**Current state:** <!-- describe what is and isn't configured in your tenant right now -->

**Gaps:** <!-- list what's missing -->

**Covered in:** Level 2 — Identity Security

---

### 2. Devices

- [ ] Devices enrolled in Intune
- [ ] Compliance policies configured
- [ ] Defender for Endpoint onboarded
- [ ] BitLocker enabled
- [ ] ASR rules configured

**Current state:** <!-- describe -->

**Gaps:** <!-- list -->

**Covered in:** Level 3 — Endpoint Security

---

### 3. Applications

- [ ] Cloud App Discovery enabled
- [ ] OAuth app governance configured
- [ ] Conditional Access App Control active
- [ ] App permissions reviewed

**Current state:** <!-- describe -->

**Gaps:** <!-- list -->

**Covered in:** Level 4 — Email, Collaboration & Cloud App Security

---

### 4. Data

- [ ] Sensitivity labels published
- [ ] DLP policies configured
- [ ] Retention policies configured
- [ ] Auto-labeling configured

**Current state:** <!-- describe -->

**Gaps:** <!-- list -->

**Covered in:** Level 5 — Data Security & Compliance

---

### 5. Infrastructure

- [ ] Azure Defender / Defender for Cloud enabled
- [ ] Security baselines applied
- [ ] Vulnerability management active

**Current state:** <!-- describe -->

**Gaps:** <!-- list -->

**Covered in:** Level 7 — Cloud Security

---

### 6. Network

- [ ] Named locations configured in Entra
- [ ] Network segmentation in place
- [ ] Conditional Access location-based policies active

**Current state:** <!-- describe -->

**Gaps:** <!-- list -->

**Covered in:** Level 2 (named locations) + Level 7 (network security)

---

## Remediation Plan — Top 5 Priorities

| Priority | Gap | Action | Covered in Level |
|----------|-----|--------|-----------------|
| 1 | <!-- gap --> | <!-- action --> | <!-- level --> |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

## Screenshots

<!-- screenshot: zero-trust-assessment-results.png -->
<!-- screenshot: assessment-identity-pillar.png -->
<!-- screenshot: assessment-device-pillar.png -->

## Note

> This document is a living checklist. Return to it after completing each level and check off items as you implement controls. By Level 8, all boxes should be ticked.

## Exam Relevance

<!-- SC-900: Describe Zero Trust methodology — verify explicitly, least privilege, assume breach -->
<!-- SC-900: Describe Zero Trust pillars — Identity, Devices, Applications, Data, Infrastructure, Network -->

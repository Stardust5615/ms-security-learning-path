# Lab 2: Endpoint Security Configuration (ASR + Antivirus + BitLocker)

## Lab Overview

| Field | Details |
|-------|---------|
| **Level** | Level 3 — Endpoint Security |
| **Certification Target** | MD-102 |
| **Estimated Duration** | ~60 minutes |
| **Environment** | Microsoft Intune admin center |
| **Difficulty** | Intermediate |
| **Date Completed** | <!-- fill in --> |
| **Status** | Not Started |

## Objectives

- [ ] Create a Microsoft Defender Antivirus baseline policy
- [ ] Create an Attack Surface Reduction rules policy (audit mode first)
- [ ] Create a BitLocker disk encryption policy
- [ ] Assign all three policies and verify application

---

## Policy 1: Microsoft Defender Antivirus Baseline

| Setting | Value |
|---------|-------|
| **Policy name** | AV-Baseline-Windows |
| **Platform** | Windows 10, Windows 11, and Windows Server |
| **Profile** | Microsoft Defender Antivirus |
| **Cloud-delivered protection** | Enabled |
| **Cloud-delivered protection level** | High |
| **Real-time protection** | Enable |
| **Behaviour monitoring** | Enable |
| **Scan all downloaded files and attachments** | Enable |
| **PUA (potentially unwanted app) protection** | Enable — Block |
| **Assignment** | All devices |

<!-- screenshot: av-policy-settings.png -->
<!-- screenshot: av-policy-assignment.png -->

---

## Policy 2: Attack Surface Reduction Rules

> **Critical:** All rules set to **Audit** mode first. Review audit events for 1–2 weeks before switching any rule to Block. Premature Block mode can break legitimate business applications.

| ASR Rule | Mode | Justification for Mode |
|----------|------|----------------------|
| Block executable content from email client and webmail | Audit | Common malware delivery vector — monitor first |
| Block all Office applications from creating child processes | Audit | Can affect legitimate macros — audit before blocking |
| Block Office applications from creating executable content | Audit | Macro-based malware prevention |
| Block Office applications from injecting code into other processes | Audit | Memory injection technique prevention |
| Block JavaScript or VBScript from launching downloaded executable content | Audit | Drive-by download prevention |
| Block credential stealing from the Windows local security authority subsystem (LSASS) | Audit | Credential dumping prevention — high risk of FP |
| Block process creations originating from PSExec and WMI commands | Audit | Lateral movement prevention |
| Block untrusted and unsigned processes that run from USB | Audit | Removable media attack prevention |

| Setting | Value |
|---------|-------|
| **Policy name** | ASR-Audit-Baseline |
| **Platform** | Windows 10 and later |
| **Profile** | Attack surface reduction rules |
| **Assignment** | All devices |
| **Review date** | <!-- when you'll review audit events and consider switching to Block --> |

<!-- screenshot: asr-policy-config.png -->
<!-- screenshot: asr-rules-list.png -->
<!-- screenshot: asr-assignment.png -->

---

## Policy 3: BitLocker Disk Encryption

| Setting | Value |
|---------|-------|
| **Policy name** | BitLocker-Baseline |
| **Platform** | Windows 10 and later |
| **Profile** | Disk encryption (BitLocker) |
| **Require device encryption** | Yes |
| **Compatible TPM startup** | Required |
| **Encryption method for OS drives** | XTS-AES 256-bit |
| **Assignment** | All devices |

<!-- screenshot: bitlocker-policy-settings.png -->
<!-- screenshot: bitlocker-assignment.png -->

---

## Policy Application Verification

| Policy | Device | Applied? | Status |
|--------|--------|----------|--------|
| AV-Baseline-Windows | <!-- device name --> | <!-- Yes/No --> | <!-- Succeeded/Pending --> |
| ASR-Audit-Baseline | <!-- device name --> | <!-- Yes/No --> | |
| BitLocker-Baseline | <!-- device name --> | <!-- Yes/No --> | |

<!-- screenshot: policy-application-status.png -->

## ASR Audit Events (Review After 24–48 Hours)

| Rule | Events Generated | Applications Affected | Decision: Keep Audit or Block? |
|------|-----------------|----------------------|-------------------------------|
| <!-- rule name --> | <!-- count --> | <!-- app names --> | <!-- decision --> |

## Lessons Learned

<!-- What is the difference between an ASR rule in Audit vs Block mode? -->
<!-- Why should you never deploy ASR rules in Block mode without testing first? -->
<!-- Which rules were most likely to cause false positives in your environment? -->

## Exam Relevance

<!-- MD-102: Deploy endpoint security using Microsoft Intune -->
<!-- MD-102: Configure and manage Microsoft Defender Antivirus -->
<!-- MD-102: Configure Attack Surface Reduction -->

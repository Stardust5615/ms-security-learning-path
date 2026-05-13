# Lab 1: Intune Enrollment — Compliance Policy Configuration

## Policy: WIN-Compliance-Baseline

### Policy Settings

| Category | Setting | Value | Justification |
|----------|---------|-------|--------------|
| **Device Health** | Require BitLocker | Yes | Data at rest protection |
| **Device Health** | Require Secure Boot | Yes | Firmware integrity |
| **Device Properties** | Minimum OS version | 10.0.19041 (Windows 10 2004+) | Ensure patched baseline |
| **System Security** | Require a password | Yes | Authentication |
| **System Security** | Minimum password length | 8 | Baseline security |
| **System Security** | Firewall | Require | Network protection |
| **System Security** | Antivirus | Require | Malware protection |
| **System Security** | Antispyware | Require | Malware protection |
| **System Security** | Microsoft Defender Antimalware | Require | Malware protection |
| **Actions for noncompliance** | Mark device noncompliant | Immediately | |
| **Actions for noncompliance** | Send email to end user | After 1 day | |

### Policy Assignment

| Setting | Value |
|---------|-------|
| **Assigned to** | All users (or device group — note which you used) |
| **Date assigned** | <!-- fill in --> |

<!-- screenshot: compliance-policy-settings.png -->
<!-- screenshot: compliance-policy-assignment.png -->

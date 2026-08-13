# UserAssist-Host-Based-Forensics

I performed a Windows host-based UserAssist investigation against an extracted `NTUSER.DAT` Registry hive to identify program execution activity, execution frequency, focus time and last execution timestamps using Registry Explorer.

> [!IMPORTANT]
> **Disclaimer**
>
> This case study was completed as part of a digital forensics training exercise for educational and portfolio purposes.
>
> The evidence, artifacts and findings presented in this repository are intended to demonstrate forensic methodology, evidence handling, artifact analysis and reporting techniques.
>
> This exercise was performed in a controlled laboratory environment.
>
> This repository does not contain legal opinions and should not be interpreted as evidence of criminal activity.

## Case Information

| Property | Value |
|-----------|---------|
| Investigation Type | UserAssist Analysis |
| Evidence | NTUSER.DAT |
| Primary Tool | Registry Explorer |
| Artifact | UserAssist |
| Analyst | Philip Oppong Adanse |
| Status | Completed |

## Skills Demonstrated

- Registry Hive Analysis
- Evidence Preservation
- Hash Verification
- UserAssist Analysis
- Program Execution Analysis
- Timeline Reconstruction
- Forensic Documentation
- Report Writing

## Tools Used

| Tool | Version |
|--------|--------|
| FTK Imager | 4.7.3.81 |
| Sherlock Forensics | Web Application |
| Registry Explorer | Current Release |

## Table of Contents

1. Evidence Acquisition
2. Hash Generation
3. Hash Verification
4. Load NTUSER.DAT
5. Navigate to UserAssist
6. Program Execution Analysis
7. Key Timeline
8. Findings
9. Limitations
10. Conclusion



---

## 1. Evidence Acquisition

The `NTUSER.DAT` Registry hive was extracted from my Windows system using FTK Imager v4.7.3.81. The extraction was performed at **15:50 UTC** to preserve the artifact for forensic examination.

### Evidence Information

| Property | Value |
|-----------|---------|
| Evidence Type | Registry Hive |
| Hive Name | NTUSER.DAT |
| Acquisition Tool | FTK Imager v4.7.3.81 |
| Acquisition Time | 15:50 UTC |
| Examiner | Philip Oppong Adanse |

### Figure 1. NTUSER.DAT Extraction

![NTUSER.DAT Extraction](Evidence/01-ftk-hive-extraction.png.png)

---

## 2. Hash Generation

To ensure evidence integrity, hash values were generated for the extracted `NTUSER.DAT` file using Sherlock Forensics. Hash generation was performed at **15:54 UTC**.

### Generated Hash Values

| Algorithm | Hash Value |
|-----------|-----------|
| MD5 | 1b8a47485bf13a0e188a06b4be3de726 |
| SHA256 | 19908a4698d6213170d42cd31f7ae25f62c10938d36c27b4484457e658fb5cdd |

### Figure 2. Hash Generation

![Hash Generation](Evidence/Screenshot%202026-08-13%20155412.png)

---

## 3. Hash Verification

The generated hash values were verified before analysis to confirm that the evidence had not been modified. Hash verification was completed at **15:57 UTC**.

### Verification Result

| Status | Result |
|----------|----------|
| MD5 Verification | Successful |
| SHA256 Verification | Successful |
| Evidence Integrity | Verified |

The matching hash values confirmed that the evidence remained unchanged throughout the acquisition process.

### Figure 3. Hash Verification

![Hash Verification](Evidence/Screenshot%202026-08-13%20155613.png)

---

## 4. Load NTUSER.DAT

I launched the Registry Explorer v2026.5.0 and the extracted `NTUSER.DAT` hive which was loaded for examination. The hive was loaded at **15:58 UTC**.

### Figure 4. NTUSER.DAT Loaded in Registry Explorer

![NTUSER.DAT Loaded](Evidence/Screenshot%202026-08-13%20155841.png)



















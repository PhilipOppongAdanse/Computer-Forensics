# Shellbags-Host-Based-Forensics

A Windows host-based Shellbags investigation performed against an extracted `UsrClass.dat` Registry hive to identify folder and drive activity, examine Shellbag metadata, review timestamps, and determine what the artifact can and cannot prove.

## Case Information

| Property | Value |
|---|---|
| Investigation Type | Windows Shellbags Forensics |
| Evidence | Windows Registry Hive |
| Evidence Name | `UsrClass.dat` |
| Primary Tool | ShellBags Explorer v2.1.0 |
| Acquisition Tool | FTK Imager v4.7.3.81 |
| Hashing Tool | Sherlock Forensics |
| Primary Artifact | Shellbags |
| Analyst | **PHILIP OPPONG ADANSE** |
| Status | In Progress |
| Classification | Training Exercise |

## Table of Contents

1. [Evidence Acquisition](#1-evidence-acquisition)
2. [Hash Generation](#2-hash-generation)
3. [Hash Verification](#3-hash-verification)
4. [Open ShellBags Explorer](#4-open-shellbags-explorer)
5. [Load the Evidence](#5-load-the-evidence)
6. [Shellbag Parsing](#6-shellbag-parsing)
7. [Identify Interesting Entries](#7-identify-interesting-entries)
8. [Analyze E: Drive](#8-analyze-e-drive)
9. [Analyze E:\new new](#9-analyze-enew-new)
10. [Timestamp Analysis](#10-timestamp-analysis)
11. [Findings](#11-findings)
12. [Conclusion](#12-conclusion)


## 1. Evidence Acquisition

At 04:25, I extracted the Registry hive using FTK Imager v4.7.3.81. The file extracted for this investigation was: `UsrClass.dat`

The purpose of this step was for me to obtain the Registry hive for forensic analysis while keeping the original evidence unchanged.


## Acquisition Details

| Property | Value |
|---|---|
| Evidence | `UsrClass.dat` |
| Acquisition Tool | FTK Imager v4.7.3.81 |
| Acquisition Time | 04:25 |
| Analyst | **PHILIP OPPONG ADANSE** |



![Registry hive extraction](Evidence/01-ftk-hive-extraction.png.png)

`Figure 1. Registry hive extraction using FTK Imager`



## 2. Hash Generation

At 04:33, I generated hash values for the extracted `UsrClass.dat` file using Sherlock Forensics. Hashing gives us a way to check whether the evidence has changed during the investigation.

### Hash Values

| Hash Type | Value |
|---|---|
| MD5 | `210c8ab2b2a2fb41615608e166e4a893` |
| SHA-256 | `fc4bddcdbb84dc20c968cc8dae66c903c628b14bd5e5f17af87bdc508b99cd4a` |


![Hash generation](Evidence/Screenshot%202026-08-11%20163525.png)

`Figure 2. Hash generation using Sherlock Forensics`


## 3. Hash Verification

At 04:35, I verified the SHA-256 hash of the extracted `UsrClass.dat` file. The verification showed that the calculated SHA-256 hash matched the reference hash generated earlier.

### Verification Result

**INTEGRITY VERIFIED - SHA-256 MATCH**

The verified SHA-256 value was: `fc4bddcdbb84dc20c968cc8dae66c903c628b14bd5e5f17af87bdc508b99cd4a`

This confirms that the `UsrClass.dat` file used for the examination matched the file that was previously hashed.


![SHA-256 verification](Evidence/Screenshot%202026-08-11%20163642.png)

`Figure 3. SHA-256 hash verification`


## 4. Open ShellBags Explorer

At 04:37, I opened ShellBags Explorer v2.1.0 to begin examining the Shellbag artifacts from the extracted Registry hive. ShellBags Explorer was used to parse and display the Shellbag records found in the `UsrClass.dat` file.


![E Drive Shellbag](Evidence/Screenshot%202026-08-11%20184446.png)

`Figure 4. ShellBags Explorer v2.1.0`


## 5. Load the Evidence

At 04:38, I loaded the extracted `UsrClass.dat` file into ShellBags Explorer. The tool processed the Registry hive and displayed the Shellbag records found in the file. The `UsrClass.dat` file was used as the source for the Shellbag analysis.


![UsrClass.dat loaded into ShellBags Explorer](Evidence/Screenshot%202026-08-11%20164437.png)

**Figure 5.  `UsrClass.dat`  loaded into ShellBags Explorer**



## 6. Shellbag Parsing

After loading the `UsrClass.dat` file, ShellBags Explorer parsed the Shellbag records stored within the Registry hive. The parser successfully processed all available Shellbag entries.

### Parsing Results

| Property | Value |
|---|---|
| Shellbags Found | 741 |
| Shellbags Parsed | 741 |
| Parsing Status | Successful |

The parsed results included drive letters, folders, shell objects and other Windows Explorer locations that had been recorded by the operating system.


![ShellBags Explorer](Evidence/Screenshot%202026-08-11%20163840.png)

`Figure 6. Shellbag parsing results`


## 7. Identify the E: Drive

During analysis, a Shellbag entry associated with the drive letter `E:\` was identified. The Shellbag record shows that Windows Explorer recorded the presence of the drive and stored it within the user's Shellbag data.

### E: Drive Details

| Property | Value |
|---|---|
| Drive Letter | E:\ |
| Shell Type | Users property view: Drive letter |
| MRU Position | 72 |
| Child Bags | 1 |

The presence of the `E:\` Shellbag entry indicates that the drive was visible to Windows Explorer and that a child item was recorded beneath it.


![E Drive Shellbag](./Evidence/Screenshot%202026-08-11%20165233.png)

`Figure 7. E:\ drive Shellbag entry`


## 8. Analyze E:\new new

Expanding the `E:\` Shellbag entry revealed a folder named `new new`. ShellBags Explorer recorded metadata relating to the folder, including timestamps, file system information and Shellbag interaction data.

### Folder Details

| Property | Value |
|---|---|
| Folder Name | new new |
| Full Path | E:\new new |
| Shell Type | Directory |
| File System Hint | exFAT |
| MRU Position | 0 |
| Child Bags | 0 |
| Node Slot | 253 |
| MFT Entry Number | 5506624 |

The folder was stored as a directory Shell Item and was associated with an exFAT file system.

![Shellbag entry for E:\new new](./Evidence/Screenshot%202026-08-11%20165632.png)

`Figure 8. Shellbag entry for E:\new new`



## 9. Timestamp Analysis

The `new new` folder contained both file system timestamps and Shellbag interaction timestamps. These timestamps provide insight into when the folder existed on the source device and when Windows Explorer recorded interaction with the folder.

### File System Timestamps

| Timestamp | Value |
|---|---|
| Created On | 2026-03-15 03:41:58 |
| Modified On | 2026-03-15 03:41:58 |
| Last Accessed | 2026-03-15 03:41:56 |

### Shellbag Interaction Timestamps

| Timestamp | Value |
|---|---|
| First Interacted | 2026-04-28 08:24:56.082 |
| Last Interacted | 2026-04-28 08:24:56.082 |
| Registry Last Write Time | 2026-04-28 08:24:56.082 |

The file system timestamps indicate when the folder metadata was recorded on the source file system. The Shellbag timestamps indicate when Windows Explorer recorded interaction with the folder. In this case, the first and last interaction times are identical, suggesting that only a single recorded interaction was preserved within the Shellbag artifact.

The folder was associated with an exFAT file system, indicating that the folder likely originated from removable storage such as a USB flash drive or external storage device.

![Timestamp information for E:\new new](./Evidence/Screenshot%202026-08-11%20165658.png)

`Figure 9. Timestamp information for E:\new new`



## 10. Findings

The analysis of the UsrClass.dat registry hive using ShellBags Explorer v2.1.0 identified evidence of interaction with a removable storage device assigned the drive letter E:\. The Shellbag records showed a folder named **new new** located on the E:\ drive.

The artifact contained the following information:

- Drive Letter: E:\
- File System: exFAT
- Folder Name: new new
- Folder Path: Desktop\E:\new new
- Created On: 2026-03-15 03:41:58
- Modified On: 2026-03-15 03:41:58
- Last Accessed On: 2026-03-15 03:41:56
- First Interacted With: 2026-04-28 08:24:56
- Last Interacted With: 2026-04-28 08:24:56

The Shellbag artifact confirms that Windows Explorer recorded interaction with the E:\ drive and the folder named **new new**. The artifact also indicates that the removable device used the exFAT file system.

No evidence was identified to determine the contents of the folder or the files stored within it.



## 11. Conclusion

A forensic examination of the UsrClass.dat registry hive was conducted using ShellBags Explorer v2.1.0. The Shellbag records provided evidence that a removable storage device assigned the drive letter E:\ was connected to the system and interacted with through Windows Explorer.

Analysis identified a folder named **new new** on the device. Metadata stored within the Shellbag artifact recorded folder timestamps, interaction timestamps and the file system type as exFAT. Shellbags are useful for demonstrating that folders and locations were viewed through Windows Explorer, even when the original device is no longer connected.

Based on the available artifact, it can be concluded that the user interacted with the E:\ drive and viewed the folder **new new**. However, Shellbags alone cannot determine the contents of the folder, whether files were opened, copied or deleted, or who created the folder.










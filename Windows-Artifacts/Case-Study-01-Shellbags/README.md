Case-Study-01-Shellbags/README.md

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








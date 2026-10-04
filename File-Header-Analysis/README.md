# Project Chimera - Hidden Data and Multi-Layer Artifact Analysis

## Overview

In this investigation, I examined a PDF document named **HIVE-FSA.pdf** that was suspected to contain hidden information beyond its visible contents. At first glance, the document appeared to be an ordinary one-page board audit report. However, the case brief indicated that additional evidence might be concealed within the file.

The objective of this investigation was to identify, extract, and validate four genuine flags while distinguishing them from misleading decoy artifacts.

Throughout the examination, I discovered that the PDF contained multiple hidden layers, including embedded ZIP archives, Base64-encoded content, email artifacts, image files, and an additional concealed archive. By following a structured forensic methodology, I successfully recovered all genuine flags and identified the decoys.

---

## Case Information

| Item | Description |
|--------|-------------|
| Case Name | Project Chimera |
| Case Reference | HIVE-FSA-009E |
| Organization | HIVE CONSULT |
| Exhibit | HIVE-FSA.pdf |
| Classification | Confidential |
| Difficulty | Advanced |
| Examiner | Philip Oppong Adanse |
| Objective | Recover four genuine flags and identify decoy artifacts |

---

## Investigation Objectives

The primary objectives of this investigation were:

- Examine the supplied PDF document.
- Determine whether hidden information existed within the file.
- Recover any concealed artifacts.
- Identify all genuine flags.
- Separate genuine evidence from decoy data.
- Maintain forensic integrity throughout the examination process.

---

# Examination Environment

The analysis was performed in a controlled forensic environment.

| Component | Details |
|------------|---------|
| Operating System | Kali Linux 2026.1 |
| Virtualization | VMware Workstation |
| User Account | cobra6golf |
| Working Directory | ~/chimera |
| Primary Evidence Folder | s1 |
| Secondary Evidence Folder | s1/s2 |

---

# Tools Used

During the investigation, I utilized several forensic and command-line tools.

| Tool | Purpose |
|--------|---------|
| sha256sum | Integrity verification |
| file | File identification |
| strings | Artifact discovery |
| exiftool | Metadata analysis |
| pdfinfo | PDF analysis |
| grep | Searching extracted content |
| tail | Data carving |
| dd | Manual extraction |
| unzip | Archive extraction |
| base64 | Decoding encoded data |
| Python 3 | Parsing and extraction |
| pdftotext | PDF text extraction |
| xdg-open | Reviewing recovered artifacts |

---

# Evidence Integrity Verification

Before beginning the examination, I created a working copy of the evidence and generated a cryptographic hash to preserve integrity.

## Original Evidence

| Item | Value |
|---------|--------|
| File Name | HIVE-FSA.pdf |
| Size | 192,947 Bytes |
| Type | PDF 1.4 |
| Pages | 1 |
| SHA256 | b2590294b85a82595e02ccacf4826b41a509736040d5520b8830bb7266415209 |

The hash was documented before analysis to ensure the file remained unchanged throughout the investigation.

---

## Evidence Acquisition

### Figure 01 – Evidence Verification

```text
Evidence Hash Verification
SHA256 Validation
File Identification
```

![Evidence Verification](Evidence/01-hash-verification.png)

---

# Phase 1 – Initial PDF Examination

I first opened the PDF to understand its visible contents.

The document appeared to be a standard board audit report containing several security recommendations regarding:

- Access control
- Administrative account reviews
- Removable media monitoring
- Evidence hashing procedures

Nothing visible within the document suggested the existence of hidden information.

However, further structural analysis revealed anomalies.

---

## PDF Metadata Analysis

Using ExifTool, I reviewed the metadata associated with the PDF.

The most notable observation was:

```text
Warning: Invalid XREF Table
```

While this warning alone did not prove the existence of hidden content, it suggested that the file structure warranted further examination.

---

### Figure 02 – PDF Metadata Examination

![Metadata Analysis](Evidence/02-exiftool-analysis.png)

---

# Phase 2 – Discovery of Hidden Data

To determine whether additional content existed beyond the visible PDF structure, I examined the file manually.

I searched for the PDF end marker:

```text
%%EOF
```

During examination, I observed additional data beyond the legitimate PDF ending.

This immediately indicated the possibility of appended content.

---

## Identification of Embedded Archive

Further inspection revealed a ZIP archive signature:

```text
PK
```

The presence of the ZIP header after the PDF end marker confirmed that an archive had been appended to the PDF.

This explained why the file opened normally while still carrying hidden content.

---

### Figure 03 – Embedded ZIP Archive Discovery

![ZIP Discovery](Evidence/03-hidden-zip-discovery.png)

---

# Phase 3 – Archive Extraction

After identifying the appended archive, I carved the hidden ZIP data from the PDF.

The extracted archive contained a text file consisting of a large Base64-encoded block.

At this stage, the investigation moved from file carving into content reconstruction.

---

### Figure 04 – Extracted Archive Contents

![Archive Extraction](Evidence/04-archive-extraction.png)

---

# Phase 4 – Base64 Decoding

The extracted text did not contain human-readable information.

I identified it as Base64-encoded content and performed a decoding operation.

After decoding, the content transformed into an email message.

This represented the first major hidden artifact recovered from the evidence.

---

### Figure 05 – Base64 Decoding Process

![Base64 Decoding](Evidence/05-base64-decoding.png)

---

# Phase 5 – Email Reconstruction

The decoded content contained a complete email message.

The email included:

- Sender information
- Recipient information
- Subject details
- An attachment

The attachment appeared to be a normal data file but required further validation.

As part of forensic best practice, I never rely on filenames alone.

Instead, I validated the true file type.

---

### Figure 06 – Email Reconstruction

![Email Reconstruction](Evidence/06-email-reconstruction.png)

---

# Phase 6 – Attachment Analysis

The attachment's filename suggested it was a generic data file.

However, file signature analysis revealed a different story.

The file was actually:

```text
JPEG Image
```

This demonstrated an attempt to disguise the artifact by using a misleading filename.

The image was extracted for further analysis.

---

### Figure 07 – Hidden JPEG Attachment

![JPEG Attachment](Evidence/07-jpeg-analysis.png)

---

# Phase 7 – Secondary Hidden Archive

While examining the JPEG, I discovered additional appended data.

The image contained another ZIP archive hidden beyond its normal file structure.

This represented a second layer of concealment.

The archive was extracted and analyzed separately.

---

### Figure 08 – Secondary ZIP Archive

![Second Archive](Evidence/08-secondary-archive.png)

---

# Phase 8 – Final PDF Recovery

The second archive contained another PDF document.

This PDF ultimately contained the final genuine flag required for the investigation.

At this point, all artifact layers had been successfully reconstructed.

---

### Figure 09 – Final PDF Recovery

![Final PDF](Evidence/09-final-pdf.png)

---

# Flag Analysis

Throughout the examination, six flag-like strings were encountered.

Not all recovered flags represented valid evidence.

Careful validation was required to distinguish genuine findings from intentionally placed decoys.

## Results

| Flag Type | Status |
|------------|---------|
| Flag 1 | Genuine |
| Flag 2 | Genuine |
| Flag 3 | Genuine |
| Flag 4 | Genuine |
| Decoy 1 | False |
| Decoy 2 | False |

---

# Findings

During this investigation, I determined that:

- The original PDF contained hidden appended data.
- A ZIP archive was embedded after the PDF end marker.
- The archive contained Base64-encoded content.
- The Base64 content decoded into an email message.
- The email contained a disguised JPEG attachment.
- The JPEG contained a second hidden ZIP archive.
- The second archive contained another PDF.
- Four genuine flags were successfully recovered.
- Two additional flags were identified as decoys.

---

# Conclusion

This investigation demonstrates how a seemingly ordinary document can conceal multiple layers of evidence.

By applying forensic principles and validating each artifact at every stage, I successfully uncovered hidden archives, reconstructed encoded communications, identified disguised files, and recovered all genuine flags associated with the case.

The examination highlights the importance of looking beyond visible content and verifying file structures rather than relying solely on filenames or application output.

What initially appeared to be a simple one-page PDF ultimately contained several layers of concealed data that required systematic forensic analysis to uncover.

---

# Disclaimer

This case study was completed in a controlled forensic laboratory environment for educational and professional development purposes.

All evidence examined during this investigation was provided as part of a forensic challenge scenario. The findings documented in this repository reflect the results obtained during my examination of the supplied exhibit and are intended to demonstrate digital forensic methodology, evidence handling, artifact recovery, and analytical reporting techniques.

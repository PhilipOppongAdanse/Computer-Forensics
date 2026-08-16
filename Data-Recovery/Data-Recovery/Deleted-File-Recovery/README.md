# USB Data Recovery & Forensic Analysis Using FTK Imager and Magnet AXIOM

## Case Overview

This exercise demonstrates the forensic recovery and analysis of data from a formatted USB storage device. The objective was to determine whether user data could be recovered after formatting and to identify any evidential artifacts remaining on the device.

The examination was conducted using a forensically acquired image of the USB drive and analyzed using industry-standard digital forensic tools.

---

## Investigation Details

| Item | Description |
|--------|-------------|
| Examination Type | USB Data Recovery & Artifact Analysis |
| Evidence Type | USB Flash Drive |
| File System | FAT32 |
| Capacity | Approximately 4GB |
| Acquisition Tool | FTK Imager |
| Analysis Tool | Magnet AXIOM |
| Image Format | E01 |
| Examiner | Philip Oppong Adanse |
| Examination Date | August 2026 |

---

# Objective

The primary objectives of this examination were:

- Recover data from a formatted USB drive.
- Identify recoverable files and deleted content.
- Extract available metadata from recovered files.
- Determine whether ownership or usage information could be identified.
- Validate that forensic recovery remains possible after formatting.

---

# Chain of Custody

| Date/Time | Action | Handler |
|------------|---------|----------|
| Acquisition Date | USB drive received for examination | Philip Oppong Adanse|
| Acquisition Date | Forensic image created using FTK Imager | Philip Oppong Adanse |
| Acquisition Date | Image hash verified | Philip Oppong Adanse |
| Analysis Date | E01 image processed in Magnet AXIOM | Philip Oppong Adanse |
| Analysis Date | Recovered artifacts reviewed and documented | Philip Oppong Adanse |

---

# Tools Used

## FTK Imager

FTK Imager was used to create a forensic image of the USB storage device in E01 format while preserving the integrity of the original evidence.

### Purpose

- Forensic acquisition
- Evidence preservation
- Image verification
- Hash generation

---

## Magnet AXIOM

Magnet AXIOM was used to process and analyze the image acquired from FTK imager. 

### Purpose

- Artifact extraction
- File recovery
- Metadata extraction
- EXIF analysis
- File system examination

---

# Stage 1: Evidence Acquisition

A forensic image of the USB drive was created using FTK Imager where hashes very generated and verified.

### Actions Performed

1. Connected USB device.
2. Launched FTK Imager.
3. Selected physical drive.
4. Created forensic image.
5. Saved image in E01 format.
6. Verified image integrity.

### Screenshot

> Insert FTK Imager acquisition screenshot here.

---

# Stage 2: Processing Evidence in Magnet AXIOM

The E01 image was loaded into Magnet AXIOM Process for examination.

### Evidence Source

```
PENDRIVE.E01
```

### Processing Method

```
Parsing and Carving
```

### Observations

The USB drive had been formatted; however, AXIOM successfully parsed the file system and carved recoverable artifacts from unallocated space.

### Screenshot

> Insert AXIOM evidence source configuration screenshot here.

---

# Stage 3: File System Examination

AXIOM identified the following file system information:

| Attribute | Value |
|------------|---------|
| File System | FAT32 |
| Volume Name | NO NAME |
| Volume Serial Number | 1A506229 |
| Total Capacity | 4,018,143,232 Bytes |
| Drive Type | Fixed |

### Findings

The FAT32 structure remained partially recoverable, enabling AXIOM to identify residual metadata and recover deleted content.

### Screenshot

> Insert File System Information screenshot here.

---

# Stage 4: Artifact Recovery Results

AXIOM successfully recovered multiple artifacts from the formatted drive.

## Recovered Artifact Categories

| Category | Count |
|-----------|--------|
| Pictures | 75 |
| Photoshop Files | 1 |
| PDF Documents | 1 |
| Device Identifiers | 3 |
| People Identifiers | 1 |

### Observation

Despite formatting, numerous files remained recoverable due to data remnants located in unallocated space.

### Screenshot

> Insert Artifact Categories screenshot here.

---

# Stage 5: Image Recovery

A total of 75 image files were recovered.

Recovered photographs appeared intact and viewable through AXIOM's preview pane.

### Examples

Recovered images included:

- Residential property photographs
- Outdoor scenes
- General image files

### Significance

The successful recovery of image files demonstrates that formatting does not immediately destroy file content. Data remnants often remain available until overwritten.

### Screenshot

> Insert recovered image gallery screenshot here.

---

# Stage 6: EXIF Metadata Analysis

Several recovered images contained embedded EXIF metadata.

### Metadata Recovered

| Field | Value |
|---------|---------|
| Camera Manufacturer | Hasselblad |
| Camera Model | L2D-20c |
| Camera Serial Number | 5Z9FL9P1AA0NHH |
| Lens Model | 24mm f/2.8-11 |
| Software Version | 00.04.89.27 |
| Original Image Width | 5280 |
| Original Image Height | 3956 |

### GPS Metadata

| Field | Value |
|---------|---------|
| Latitude | 5.660111111111111 |
| Longitude | -0.03508611111111111 |
| Altitude | 51.781 m |

### Significance

The embedded metadata revealed:

- Device used to capture the image.
- Geographical location of image capture.
- Date and time information.
- Camera serial number.

Such metadata can be valuable during investigations involving:

- Ownership attribution.
- Location verification.
- Timeline reconstruction.
- Device identification.

### Screenshot

> Insert EXIF Metadata screenshot here.

---

# Stage 7: Document Recovery

AXIOM recovered a PDF document from the formatted USB drive.

### Document Information

| Attribute | Value |
|------------|---------|
| Type | PDF |
| Author | Philip Adanse |
| Last Modified | 28 July 2026 |

### Observation

The document remained recoverable despite the formatting operation.

The metadata identified a potential user associated with the document.

### Screenshot

> Insert recovered PDF screenshot here.

---

# Key Findings

## Finding 1

A formatted USB drive does not necessarily result in complete data destruction.

### Evidence

75 image files, 1 PDF document, and additional artifacts were successfully recovered.

---

## Finding 2

EXIF metadata remained intact within recovered images.

### Evidence

GPS coordinates, camera model, camera serial number, and image creation information were extracted.

---

## Finding 3

User-related information was recoverable.

### Evidence

The recovered PDF document identified:

```
Philip Adanse
```

as the document author.

---

## Finding 4

The original storage structure remained partially identifiable.

### Evidence

FAT32 file system metadata and volume information were successfully parsed.

---

# Conclusion

The forensic examination demonstrated that substantial data remained recoverable from the formatted USB drive. Using FTK Imager for acquisition and Magnet AXIOM for analysis, multiple files and artifacts were successfully recovered, including photographs, document files, device identifiers, and metadata.

Of particular significance was the recovery of EXIF metadata containing camera information and GPS coordinates, as well as a PDF document linked to a named user. These findings illustrate the importance of forensic imaging and artifact recovery techniques when examining formatted storage media.

The examination confirms that formatting alone is insufficient to securely erase data and that valuable evidential artifacts may persist until overwritten.

---

# Evidence Screenshots

## Figure 1 – Case Creation in Magnet AXIOM

*Insert Screenshot*

## Figure 2 – Evidence Source Selection

*Insert Screenshot*

## Figure 3 – Processing Configuration

*Insert Screenshot*

## Figure 4 – File System Information

*Insert Screenshot*

## Figure 5 – Artifact Categories

*Insert Screenshot*

## Figure 6 – Recovered Images

*Insert Screenshot*

## Figure 7 – EXIF Metadata Analysis

*Insert Screenshot*

## Figure 8 – Recovered PDF Document

*Insert Screenshot*

---

**Examiner:** MrPhilGhana  
**Tools Used:** FTK Imager 4.7.x, Magnet AXIOM 9.11  
**Examination Type:** USB Data Recovery & Artifact Recovery

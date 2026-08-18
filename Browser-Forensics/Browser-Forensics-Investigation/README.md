# Browser Forensics Investigation Using FTK Imager and Autopsy

## Case Information

| Field | Details |
|---------|---------|
| Case Title | Browser History and Activity Analysis |
| Examiner | MRPHILGHANA |
| Tools Used | FTK Imager 4.7.3.8, Autopsy 4.22.1 |
| Evidence Type | Google Chrome Browser Artifacts |
| Acquisition Method | Logical Acquisition |
| Examination Date | August 2026 |

---

# Overview

This investigation focused on the acquisition, preservation, verification, and analysis of Google Chrome browser artifacts. The examination was conducted using FTK Imager for evidence acquisition and Autopsy 4.22.1 for forensic analysis.

The objective was to identify user browsing activity, search behavior, frequently visited websites, browser-generated artifacts, and evidence of online activity while maintaining forensic integrity throughout the investigation process.

---

# Table of Contents

- [Overview](#overview)
- [Phase 1: Evidence Acquisition](#phase-1-evidence-acquisition)
  - [FTK Imager Initialization](#ftk-imager-initialization)
  - [Browser Artifact Extraction](#browser-artifact-extraction)
  - [Evidence Tree Examination](#evidence-tree-examination)
  - [Chrome Default Profile Artifacts](#chrome-default-profile-artifacts)
- [Phase 2: Evidence Integrity Verification](#phase-2-evidence-integrity-verification)
  - [BookmarkMergedSurfaceOrdering](#bookmarkmergedsurfaceordering)
  - [Favicons](#favicons)
  - [History](#history)
  - [Login Data](#login-data)
  - [Shortcuts](#shortcuts)
  - [Top Sites](#top-sites)
- [Phase 3: Forensic Analysis Using Autopsy](#phase-3-forensic-analysis-using-autopsy)
  - [Ingest Configuration](#ingest-configuration)
  - [Evidence Successfully Loaded](#evidence-successfully-loaded)
  - [Browser History Analysis](#browser-history-analysis)
  - [Search Activity Analysis](#search-activity-analysis)
  - [SQLite Database Statistics](#sqlite-database-statistics)
  - [Top Sites Analysis](#top-sites-analysis)
- [Findings](#findings)
- [Conclusion](#conclusion)
- [Tools Used](#tools-used)
- [Examiner](#examiner)

---

# Phase 1: Evidence Acquisition

## FTK Imager Initialization

FTK Imager was launched to perform a logical acquisition of browser artifacts from the target system.

![FTK Imager](01-FTK-IMAGER.png)

---

## Browser Artifact Extraction

The Google Chrome browser data directory was identified and selected for extraction.

![Browser Artifact Extraction](02-FTK-EXTRACTION-IN-PROGRESS.png)

The extraction process preserved browser artifacts in their original state for forensic analysis.

---

## Evidence Tree Examination

The evidence tree was reviewed to locate Google Chrome browser data.

![Evidence Tree](03-EVIDENCE-TREE-OF-CHROME.png)

The browser profile structure revealed multiple artifacts containing historical user activity.

---

## Chrome Default Profile Artifacts

The Chrome Default profile contained several browser databases of forensic value.

![Chrome Default Artifacts](04-ARTIFACTS-IN-CHROME-DEFAULT.png)

### Identified Artifacts

- BookmarkMergedSurfaceOrdering
- Favicons
- History
- Login Data
- Shortcuts
- Top Sites

These artifacts collectively provide evidence relating to browsing history, saved logins, bookmarks, frequently visited websites, and user browsing behavior.

---

# Phase 2: Evidence Integrity Verification

To maintain forensic integrity, cryptographic hashes were generated and verified for each recovered artifact.

---

## BookmarkMergedSurfaceOrdering

### Hash Generation

![Bookmark Hash Generation](05-HASH-GENERATION-BOOKMARK.png)

### Hash Verification

![Bookmark Hash Verification](06-HASH-VERIFICATION-BOOKMARK.png)

**Result:** MD5 Verification Successful

---

## Favicons

### Hash Generation

![Favicon Hash Generation](07-HASH-GENERATION-FAVICON.png)

### Hash Verification

![Favicon Hash Verification](08-HASH-VERIFICATION-FAVICON.png)

**Result:** MD5 Verification Successful

---

## History

### Hash Generation

![History Hash Generation](09-HASH-GENERATION-HISTORY.png)

### Hash Verification

![History Hash Verification](10-HASH-VERIFICATION-HISTORY.png)

**Result:** MD5 Verification Successful

---

## Login Data

### Hash Generation

![Login Data Hash Generation](11-HASH-GENERATION-LOGIN-DATA.png)

### Hash Verification

![Login Data Hash Verification](12-HASH-VERIFICATION-LOGIN-DATA.png)

**Result:** MD5 Verification Successful

---

## Shortcuts

### Hash Generation

![Shortcuts Hash Generation](13-HASH-GENERATION-SHORTCUT.png)

### Hash Verification

![Shortcuts Hash Verification](14-HASH-VERIFICATION-SHORTCUT.png)

**Result:** MD5 Verification Successful

---

## Top Sites

### Hash Generation

![Top Sites Hash Generation](15-HASH-GENERATION-TOP-SITES.png)

### Hash Verification

![Top Sites Hash Verification](16-HASH-VERIFICATION-TOP-SITES.png)

**Result:** MD5 Verification Successful

---

# Phase 3: Forensic Analysis Using Autopsy

## Ingest Configuration

The recovered browser artifacts were imported into Autopsy and processed using forensic ingest modules.

![Autopsy Ingest](17-AUTOPSY-INGEST.png)

### Enabled Modules

- Recent Activity
- Keyword Search
- Hash Lookup
- File Type Identification
- Embedded File Extractor
- Interesting Files Identifier
- Email Parser
- Picture Analyzer

These modules assisted in reconstructing browser activity and identifying relevant artifacts.

---

## Evidence Successfully Loaded

The browser artifacts were successfully loaded into the Autopsy case.

![Evidence Loaded](18-AUTOPSY-EVIDENCE-LOADED.png)

The evidence source contained browser databases associated with user browsing activity.

---

## Browser History Analysis

Autopsy parsed the browser history database and recovered thousands of browsing records.

![History Analysis](19-AUTOPSY-HISTORY-URL.png)

The recovered URLs revealed user activity involving:

- Artificial Intelligence platforms
- Cybersecurity resources
- Digital Forensics research
- Communication services
- Online productivity platforms

---

## Additional Browser History Records

Additional URL records were recovered from the browser history database.

![Additional URL Records](20-AUTOPSY-HISTORY-URL-1.png)

Examples included visits to:

- ChatGPT
- Claude AI
- Telegram Web
- Canva
- Google Docs
- Flightradar24

---

## Search Activity Analysis

Autopsy recovered keyword searches from browser artifacts.

![Keyword Search Analysis](21-AUTOPSY-KEYWORD-SEARCH-TERM.png)

### Recovered Search Terms

- email location tracker
- blockchain sender email
- event ticket ghana
- dns
- cia
- jpg to png
- digital forensics schools in israel
- Israel Cyber Campus
- ICCP
- KerneliOS

### Observation

The recovered searches indicate interest in:

- Digital Forensics
- Cybersecurity
- Technical Research
- Professional Development

---

## SQLite Database Statistics

Browser database statistics were extracted from the History database.

![SQLite Statistics](22-SQLITE-SEQUENCE.png)

### Database Records

| Table | Records |
|---------|---------|
| URLs | 6,984 |
| Visits | 13,903 |
| Clusters | 1,513 |
| Visited Links | 9,226 |

These records demonstrate substantial browser activity over time.

---

## Top Sites Analysis

The Top Sites database identified the browser's most frequently visited websites.

![Top Sites](23-TOP-SITES.png)

### Frequently Visited Websites

| Rank | Website |
|---------|---------|
| 1 | GitHub |
| 2 | RedHatPentester GitHub Profile |
| 3 | ChatGPT |
| 4 | Claude AI |
| 5 | Canva |
| 6 | Google Lens |
| 7 | Pinterest |
| 8 | HIVE SQLite Explorer |
| 9 | Flightradar24 |
| 10 | Telegram Web |

### Observation

The browser activity demonstrates regular interaction with:

- Open-source repositories
- AI platforms
- Design platforms
- Communication services
- Digital forensics resources

---

# Findings

## Finding 1

A total of approximately **3,447 URL records** were recovered from browser history.

## Finding 2

Telegram Web was among the most frequently visited communication platforms.

## Finding 3

Artificial Intelligence platforms including ChatGPT and Claude AI were accessed regularly.

## Finding 4

Multiple searches associated with cybersecurity and digital forensics were recovered.

## Finding 5

Canva-related artifacts indicate content creation and graphic design activities.

## Finding 6

Google Docs and collaborative platforms were identified throughout browser history.

## Finding 7

Multiple Flightradar24 entries indicate repeated aviation tracking activity.

## Finding 8

All examined browser artifacts successfully passed integrity verification checks.

---

# Conclusion

The forensic examination successfully acquired, preserved, verified, and analyzed Google Chrome browser artifacts using FTK Imager and Autopsy.

Analysis of browser history, search activity, top sites, and supporting browser databases revealed extensive interaction with artificial intelligence platforms, cybersecurity resources, digital forensics learning materials, communication services, productivity tools, and aviation tracking websites.

The recovered evidence demonstrates regular use of ChatGPT, Claude AI, Telegram Web, GitHub, Canva, Google Docs, and Flightradar24. Search activity further suggests ongoing research into cybersecurity, digital forensics, and professional development opportunities.

Hash verification confirmed the integrity of all examined artifacts, supporting the reliability and authenticity of the findings presented in this investigation.

---

# Tools Used

- FTK Imager 4.7.3.8
- Autopsy 4.22.1

---

# Examiner

**MRPHILGHANA**  
Digital Forensics Examiner

---

*End of Report*

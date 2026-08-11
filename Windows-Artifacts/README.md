# Windows Artifact Analysis

Windows computers are always saving little bits of information about what a user or the system has done. These bits of information are called "artifacts." They help investigators figure out what happened on a computer, put events in order, find out what programs were run and understand how the device was used.

Learning to read Windows artifacts is a basic skill in computer forensics. This is because most investigations depend on the small traces that users and the operating system leave behind.

---

## Why Windows Artifacts Matter
Windows artifacts shows:

- What the user did
- Which programs were run
- Which files were opened
- Whether a USB device was plugged in or not
- When someone logged in
- What was viewed in a web browser
- Changes made to the system

When investigators look at several artifacts together, they can build a solid, trustworthy picture of what really happened on the computer.

---

## Areas Covered
| Artifact | Purpose |
|----------|---------|
| Prefetch | Proof that a program was run |
| Event Logs | Records of system and user events |
| LNK Files | Proof that a file or folder was opened |
| Jump Lists | Recently used applications |
| UserAssist | Proof that a program was opened through the GUI (Graphical User Interface) |
| Shellbags | History of folders that were opened |
| Recycle Bin | Proof of deleted files |
| Recent Files | Documents that were recently opened |

---

## Tools Used

- Autopsy
- FTK Imager
- Eric Zimmerman's Tools
- Registry Explorer
- Shellbag explorer

- ## Investigations

Case studies and hands-on exercises will be added here as soon as i finish them.

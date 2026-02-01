# USB Device Investigation
---

## Objective
Determine **if**, **when**, and **how** an external USB storage device was connected to a Windows system, and what user activity occurred involving that device.

---

## When to Use This Technique
- Suspected data exfiltration
- Insider threat investigations
- Malware delivery via USB
- CTF challenges involving removable media
- Timeline reconstruction involving external devices

---

## Core Questions This Technique Answers
- Was a USB storage device connected?
- When was it first and last connected?
- What device (vendor/product/serial)?
- Which user interacted with it?
- What files were accessed or executed from it?

---

## Inputs (Evidence Sources)

### Logs
- SetupAPI logs (`setupapi.dev.log`)

### Registry
- USBSTOR
- Enum\\USB
- MountedDevices

### Execution / User Activity
- LNK (Shortcut) files
- Jump Lists (optional, case-dependent)

### Filesystem
- File timestamps on removable paths
- Recycle Bin (if applicable)

---

## Core Workflow (Standard Investigation)

### 1️⃣ Establish Device Connection Evidence
**Goal:** Prove the USB device was connected.

- Parse **SetupAPI logs**
- Identify:
  - First installation timestamp
  - Device class (USBSTOR)
  - Vendor / Product information

> This establishes *fact of connection*.

---

### 2️⃣ Identify the Device Uniquely
**Goal:** Avoid confusing multiple USB devices.

- Extract:
  - Vendor ID
  - Product ID
  - Serial Number
- Correlate across:
  - SetupAPI logs
  - Registry USB artifacts

> Serial number = strongest identifier.

---

### 3️⃣ Map Device to System Timeline
**Goal:** Anchor USB usage in time.

- Correlate:
  - SetupAPI timestamps
  - Registry LastWrite times
  - User logon events (if available)

> This defines *when the device existed on the system*.

---

### 4️⃣ Attribute User Interaction
**Goal:** Prove what a user did with the device.

- Analyze **LNK (shortcut) files**
  - Paths pointing to removable drives
  - Volume serial numbers
  - File names accessed
- Optional:
  - Jump Lists for application-file interaction

> This establishes *user action*, not just presence.

---

### 5️⃣ Reconstruct Activity
**Goal:** Move from evidence to narrative.

- What files were opened?
- Were executables run?
- Was data copied *to* or *from* the device?
- Does activity align with working hours?

---

## Artifact-Specific Usage Notes

### SetupAPI Logs
- Best source for **first-time connection**
- Survives reboots
- Does **not** prove file access

See: `../../02-Artifacts/logs/setupapi-logs.md`

---

### LNK Files in USB Cases
- High-value for:
  - File access evidence
  - Removable media correlation
- Look for:
  - Drive letters
  - Volume serial numbers
  - Network or removable paths

See: `../../02-Artifacts/execution/lnk-files.md`

---

### Registry USB Artifacts
- Tracks device enumeration
- Can persist long after removal
- Useful for:
  - Device fingerprinting
  - Cross-system correlation

See: `../../02-Artifacts/registry/usb-artifacts.md`

---

## Failure Points & Pitfalls

- ❌ Assuming presence = usage  
- ❌ Ignoring timezone conversions  
- ❌ Mixing up multiple USB devices  
- ❌ Treating copied LNKs as execution proof  
- ❌ Over-trusting a single artifact  

USB cases **require correlation**. Single artifacts lie.

---

## Speed Version (CTF / Triage Mode)

**Minimum viable flow:**
1. SetupAPI → prove connection
2. LNK files → prove access
3. Timeline correlation → answer the question

Skip deep registry parsing unless required.

---

## Tool Mapping

| Tool | Use |
|----|----|
| Autopsy | High-level USB + LNK review |
| MFTECmd | File system & removable paths |
| RegRipper | Registry USB artifacts |
| mftExplorer | Contextual file access |

---

## Output (What You Should End With)

- Confirmed USB device identity
- Connection timeline
- User activity involving the device
- Confidence level of conclusions

---

## Case Links
- Used in: `../../06-Case-Studies/`
- Related techniques:
  - `user-activity-reconstruction.md`
  - `timeline-analysis.md`

---

## Investigator Mindset Reminder

> **USB forensics is about intent, not just insertion.**  
> Devices connect all the time. Actions are what matter.

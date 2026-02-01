# User Activity Reconstruction
---

## Objective
Reconstruct **what a user did**, **when they did it**, and **how confidently it can be proven**, using correlated Windows forensic artifacts.

This technique focuses on **user intent and behavior**, not just system events.

---

## When to Use This Technique
- Insider threat investigations
- Data exfiltration cases
- Malware execution analysis
- CTF forensic challenges
- Incident response timelines
- USB and removable media investigations

---

## Core Questions This Technique Answers
- Which user performed the activity?
- What actions were taken?
- When did those actions occur?
- Were files opened, copied, or executed?
- How strong is the evidence for each claim?

---

## Inputs (Primary Evidence Sources)

### Execution & Interaction
- LNK (Shortcut) files
- Jump Lists
- Prefetch (context-dependent)

### Filesystem
- File and folder timestamps
- Recycle Bin artifacts
- MFT entries

### Logs
- Windows Event Logs (logon, process, file access)
- SetupAPI logs (for removable media)

### Registry
- User hives (NTUSER.DAT)
- USB-related keys
- Application usage keys

---

## Core Workflow (Standard Reconstruction)

### 1️⃣ Identify the User Context
**Goal:** Anchor actions to a specific user.

- Determine:
  - Username
  - SID
  - Profile directory
- Confirm logon/logoff times if available

> Activity without user attribution is incomplete.

---

### 2️⃣ Establish Execution Evidence
**Goal:** Identify what was launched or opened.

- Analyze:
  - LNK files
  - Jump Lists
- Extract:
  - File paths
  - Application names
  - Volume serial numbers
  - Timestamps

> Execution artifacts carry **high evidentiary weight**.

---

### 3️⃣ Identify File Interaction
**Goal:** Determine what data the user touched.

- Look for:
  - LNK targets pointing to documents
  - Recent files in Jump Lists
  - MFT timestamp changes
- Distinguish:
  - Opened vs executed
  - Local vs removable media

---

### 4️⃣ Correlate with Timeline
**Goal:** Order actions logically.

- Correlate:
  - Execution timestamps
  - File timestamps
  - Logon events
  - Device connection times (if applicable)

> Timelines turn artifacts into narratives.

---

### 5️⃣ Attribute Intent
**Goal:** Move from “what happened” to “why it matters”.

Ask:
- Was the action manual or automated?
- Was the activity normal or anomalous?
- Does behavior align with job role or time-of-day?

Intent is inferred, **never assumed**.

---

## Artifact-Specific Interpretation Notes

### LNK Files
- Strong indicators of user-initiated access
- Can reveal:
  - Original file location
  - Removable media usage
- Pitfall:
  - Copied LNKs ≠ execution proof

See: `../../02-Artifacts/execution/lnk-files.md`

---

### Jump Lists
- Show application–file interaction
- Useful even when files are deleted
- Pitfall:
  - Application-specific behavior varies

See: `../../02-Artifacts/execution/jumplists.md`

---

### Browser Artifacts
- Reveal user intent and research behavior
- Useful for:
  - Exfil preparation
  - Malware acquisition
- Pitfall:
  - Private browsing gaps

See: `../../02-Artifacts/filesystem/browser-artifacts.md`

---

## Correlation Patterns (High Value)

| Pattern | Interpretation |
|------|---------------|
| LNK + USB artifact | File accessed from removable device |
| Browser download + Prefetch | Executable likely run |
| Jump List + MFT timestamp | File accessed even if deleted |
| SetupAPI + LNK | USB used by specific user |

---

## Failure Points & Common Mistakes

- ❌ Treating access as execution
- ❌ Ignoring timezone offsets
- ❌ Over-trusting single artifacts
- ❌ Missing user profile boundaries
- ❌ Forgetting artifact persistence differences

Reconstruction **requires multiple artifacts**.

---

## Speed Version (CTF / Rapid Triage)

**Minimal viable reconstruction:**
1. Identify user profile
2. Parse LNK + Jump Lists
3. Build a rough timeline
4. Answer the question, not the story

Depth only if required.

---

## Tool Mapping

| Tool | Contribution |
|----|-------------|
| Autopsy | Broad artifact correlation |
| MFTECmd | File system timelines |
| RegRipper | User registry analysis |
| Timeline tools | Sequence validation |

---

## Output (What You Should Produce)

- A clear activity timeline
- User attribution confidence
- Supporting artifacts per action
- Explicit uncertainty where evidence is weak

---

## Related Techniques
- `timeline-analysis.md`
- `usb-investigation.md`
- `file-recovery.md`

---

## Case Links
- Applied in: `../../06-Case-Studies/`

---

## Investigator Rule

> **Users leave patterns, not logs.**  
> Your job is to recognize and prove those patterns.

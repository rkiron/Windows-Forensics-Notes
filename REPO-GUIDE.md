# 📘 REPO-GUIDE.md  
*(How this repository is structured and how to use it while learning Windows Forensics)*

---

# 🎯 Purpose of this repository

This repository is not a notes dump.

It is a **Windows Forensics knowledge base + investigation playbook + CTF preparation system.**

Every file in this repo must serve at least one of these goals:

- Improve investigation thinking  
- Deepen artifact understanding  
- Increase forensic speed  
- Capture applied experience  

If a note does not strengthen one of these, it does not belong here.

---

# 🧱 Core Structure and How to Use It

---

## 🔹 00 – Methodology  
**Focus:** *How investigations are structured and approached.*

This folder defines how I think and operate as a forensic analyst.

### What goes here
- Evidence handling principles  
- Investigation phases and workflows  
- Triage models  
- Hypothesis building methods  
- Checklists  
- Reporting structure  
- Mistake-prevention systems  

### What does NOT go here
- Tool commands  
- Artifact details  
- Windows internals  

### When to update this folder
- After making an investigation mistake  
- After discovering a better workflow  
- After solving complex cases  
- When my approach evolves  

This folder becomes my **personal DFIR doctrine.**

---

## 🔹 01 – Windows Internals  
**Focus:** *How Windows works under the hood.*

This folder builds system understanding so forensic reasoning is grounded, not memorized.

### What goes here
- NTFS design and behavior  
- Registry architecture  
- Event logging pipeline  
- Memory fundamentals  
- Windows time systems  
- Process and user profile structure  

### What does NOT go here
- Extraction workflows  
- Artifact forensic interpretation  
- CTF tricks  

### When to update this folder
- When learning a new Windows component  
- When an artifact doesn’t make sense  
- When forensic behavior needs explanation  

This folder prevents shallow learning.

---

## 🔹 02 – Artifacts  
**Focus:** *Windows evidence sources and their forensic value.*

This is the core forensic encyclopedia.

Every artifact note should clearly answer:
- What it is  
- Where it is located  
- What creates it  
- What forensic questions it answers  
- How reliable it is  
- How it can be manipulated or lost  

### What goes here
- Registry hives and keys  
- Filesystem artifacts  
- Execution traces  
- Persistence mechanisms  
- Log sources  

### What does NOT go here
- Full investigations  
- Generic Windows explanations  
- Tool tutorials  

### When to update this folder
- When studying a new artifact  
- After every lab or CTF  
- When misunderstandings are corrected  
- When deeper insight is gained  

This folder becomes my **forensic weapon library.**

---

## 🔹 03 – Tools  
**Focus:** *Practical interaction with forensic utilities.*

This folder exists to reduce friction and improve speed.

### What goes here
- Purpose of each tool  
- What it extracts  
- Core commands  
- Output interpretation  
- Strengths and weaknesses  
- Common errors and traps  

### What does NOT go here
- Artifact theory  
- Investigation doctrine  
- Full case logic  

### When to update this folder
- When learning a new tool  
- When discovering better workflows  
- When encountering tool failures  
- When optimizing speed  

This folder becomes my **operational manual.**

---

## 🔹 04 – Techniques  
**Focus:** *How evidence is analyzed and correlated.*

This folder turns extracted data into conclusions.

### What goes here
- Timeline construction methods  
- Correlation strategies  
- User behavior reconstruction  
- Malware hunting logic  
- Noise filtering systems  
- Persistence detection frameworks  

### What does NOT go here
- Chain of custody  
- Tool usage tutorials  
- Windows architecture  

### When to update this folder
- After solving harder challenges  
- When patterns emerge  
- When new investigation methods are learned  
- When a technique fails and is refined  

This folder becomes my **analysis skill tree.**

---

## 🔹 05 – CTF Notes  
**Focus:** *Competition-specific optimization.*

This folder exists because CTFs reward speed and pattern recognition, not full forensic rigor.

### What goes here
- Common forensic challenge types  
- Artifact-to-flag patterns  
- CTF traps and misdirections  
- Speed workflows  
- Typical flag locations  
- Competition heuristics  

### What does NOT go here
- Deep theory  
- Real-world forensic documentation  
- Long explanations  

### When to update this folder
- After every CTF  
- After timed practice  
- When a pattern repeats  
- When a shortcut is discovered  

This folder becomes my **competitive playbook.**

---

## 🔹 06 – Case Studies  
**Focus:** *End-to-end investigations and applied learning.*

This is where all knowledge is validated.

Each case study should include:
- Scenario  
- Initial hypotheses  
- Methodology followed  
- Artifacts analyzed  
- Tools used  
- Techniques applied  
- Timeline built  
- Final conclusions  
- Mistakes and improvements  

### What goes here
- Lab writeups  
- CTF forensic cases  
- Simulated investigations  
- Full challenge breakdowns  

### What does NOT go here
- Isolated notes  
- Theory  
- Tool documentation  

### When to update this folder
- After every serious lab  
- After realistic challenges  
- After competitions  

This folder becomes my **proof of competence.**

---

## 🔹 07 – Cheatsheets  
**Focus:** *Speed and compression.*

This folder contains condensed, high-utility references.

### What goes here
- Artifact maps  
- Fast triage paths  
- Command collections  
- Timeline templates  
- CTF quick references  

### What does NOT go here
- Tutorials  
- Explanations  
- Deep notes  

### When to update this folder
- Before competitions  
- After repeated challenges  
- When a process stabilizes  
- When speed becomes a bottleneck  

This folder becomes my **forensic combat layer.**

---

# 🔁 How to use this repo while learning

1. Learn a concept → update **Internals or Artifacts**  
2. Use a tool → update **Tools**  
3. Solve a challenge → write a **Case Study**  
4. Extract patterns → update **Techniques**  
5. Optimize for speed → update **CTF Notes / Cheatsheets**  
6. Improve thinking → update **Methodology**

---

# ⚠ Operating rules

- No orphan notes  
- No copy-paste theory  
- Every case improves at least one other folder  
- Every mistake becomes a rule, checklist, or technique  
- Cheatsheets are built only from experience  

---

# 🏁 End goal

This repository should evolve into:

- a forensic reference system  
- an investigation doctrine  
- a competition playbook  
- and a long-term DFIR knowledge base.

If it doesn’t make me a better investigator, it doesn’t belong here.

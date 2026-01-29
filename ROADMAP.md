
# Windows Forensics Roadmap

This roadmap defines the progression of this repository from foundations → artifacts → investigations → competition mastery.

The goal is not to “cover topics.”  
The goal is to build **forensic thinking and operational speed.**

---

## 🟩 Phase 1: Foundations (Windows + Forensics Core)

Focus: understanding how Windows works and how investigations are structured.

### Methodology
- [ ] Evidence handling and chain of custody  
- [ ] Forensic workflow design  
- [ ] Triage vs deep investigation  
- [ ] Investigation checklist system  

### Windows Internals
- [ ] NTFS fundamentals  
- [ ] Registry architecture  
- [ ] Windows event logging  
- [ ] Memory basics  

📌 Output of Phase 1:
- You can explain where evidence comes from.
- You understand what Windows is doing under the hood.
- You stop guessing and start reasoning.

---

## 🟨 Phase 2: Artifact Mastery

Focus: deep, practical understanding of Windows evidence sources.

### Registry
- [ ] SAM, SYSTEM, SOFTWARE, NTUSER
- [ ] User activity traces
- [ ] Persistence locations
- [ ] Execution evidence

### File System
- [ ] MFT and timestamps  
- [ ] USN Journal  
- [ ] Prefetch  
- [ ] Recycle Bin  

### Execution & Persistence
- [ ] Shimcache, Amcache  
- [ ] Jump Lists  
- [ ] Services, tasks, run keys  

📌 Output of Phase 2:
- You can reconstruct “what happened” from raw artifacts.
- You know what artifacts answer which forensic questions.
- You can design an investigation plan instead of blindly running tools.

---

## 🟦 Phase 3: Tools + Techniques

Focus: turning knowledge into investigation capability.

### Tools
- [ ] Volatility (memory)  
- [ ] KAPE (collection)  
- [ ] RegRipper  
- [ ] Autopsy  
- [ ] Timeline generation tools  

### Techniques
- [ ] Timeline analysis  
- [ ] User activity reconstruction  
- [ ] Log correlation  
- [ ] Malware and intrusion hunting  

📌 Output of Phase 3:
- You can move from artifacts to timelines.
- You can justify conclusions.
- You can investigate, not just extract.

---

## 🟧 Phase 4: Applied Forensics

Focus: full investigations and simulations.

- [ ] End-to-end forensic labs  
- [ ] Memory + disk combined cases  
- [ ] Realistic attack simulations  
- [ ] Detailed case documentation  

📌 Output of Phase 4:
- You can run a complete forensic investigation.
- You can explain and defend your findings.
- Your notes become operational playbooks.

---

## 🟥 Phase 5: CTF Specialization

Focus: speed, pattern recognition, and scoring.

- [ ] Common CTF forensic traps  
- [ ] Artifact-to-flag patterns  
- [ ] Speed extraction workflows  
- [ ] Competition-grade cheatsheets  
- [ ] Time-attack playbooks  

📌 Output of Phase 5:
- You recognize forensic questions instantly.
- You know what to extract first.
- You stop brute forcing and start targeting.

---

## 🏁 Long-Term Goals

- Build a complete Windows forensic artifact encyclopedia  
- Maintain an evolving investigation playbook  
- Convert notes into a publishable forensic reference  
- Use this repository as proof of forensic competence  

---

## 📅 Maintenance Rules

- Every lab or CTF → update artifacts or techniques  
- Every new concept → mapped to an investigation question  
- Every weak area → added to Phase tracking  

This roadmap is not static.  
It evolves based on case complexity, CTF experience, and forensic maturity.

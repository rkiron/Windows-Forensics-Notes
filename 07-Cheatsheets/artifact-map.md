# 🧠 Windows Forensics Brain Map
*A rapid-decision artifact reference for triage, CTFs, and investigations*

This file answers one question only:

> **“What artifact do I go to when I need to prove X?”**

---

# 🧩 CORE QUESTION MAP

---

## 👤 Who used this system?

| Artifact     | Location                                                   |
| ------------ | ---------------------------------------------------------- |
| SAM          | `C:\Windows\System32\config\SAM`                           |
| SECURITY     | `C:\Windows\System32\config\SECURITY`                      |
| Profile list | `SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList` |
| NTUSER.DAT   | `C:\Users\<user>\NTUSER.DAT`                               |

Proves:
- Local accounts  
- Account creation  
- User SIDs  
- Enabled/disabled users  

Cannot prove:
- Successful logon (needs Event Logs)

---

## 🔐 Who logged in and when?

| Artifact      | Source                    |
| ------------- | ------------------------- |
| Security.evtx | Logons, logoffs, failures |
| SYSTEM hive   | Last shutdown/start       |
| SECURITY hive | Logon policy              |
| ProfileList   | First logon mapping       |

Event IDs:
- 4624 → successful logon  
- 4625 → failed logon  
- 4634 → logoff  
- 4672 → admin logon  

---

## ▶ What programs were executed?

| Artifact   | Strength                    |
| ---------- | --------------------------- |
| UserAssist | GUI execution + count       |
| ShimCache  | Program presence + mod time |
| AmCache    | Strong execution + hashes   |
| BAM/DAM    | Background execution        |
| Prefetch   | Execution proof + frequency |
  
Golden rule:
> Never rely on a single execution artifact.

---

## 📂 What files did the user open?

| Artifact     | Evidence                 |
| ------------ | ------------------------ |
| RecentDocs   | Recently opened files    |
| Office MRU   | Office documents         |
| OpenSave MRU | Open/save dialogs        |
| Jump Lists   | File + app relationships |
| ShellBags    |  Folder interaction      |

---

## 🧠 What did the user search or type?

| Artifact       | Source               |
| -------------- | -------------------- |
| TypedPaths     | Explorer address bar |
| WordWheelQuery | Search terms         |
| RunMRU         | Win+R commands       |
 

---

## 🔌 What USB or external devices were used?

| Artifact          | Purpose           |
| ----------------- | ----------------- |
| USBSTOR           | Device identity   |
| Enum\USB          | Hardware history  |
| Device Properties | First/last insert |
| MountedDevices    | Drive mapping     |
| Portable Devices  | Volume names      |
| SetupAPI.dev.log  |  Install timeline |


---

## 🏗 Was persistence established?

| Artifact        | Type                   |
| --------------- | ---------------------- |
| Run keys        | User & machine startup |
| Services        | Service-based malware  |
| Scheduled Tasks | Timed persistence      |
| Startup folders | User persistence       |
| WMI             | Fileless persistence   |


---

## 🕒 When did things happen?

| Artifact            | Timeline value            |
| ------------------- | ------------------------- |
| MFT                 | File create/modify/access |
| USN Journal         | File system activity      |
| Registry timestamps | Key changes               |
| Event Logs          | Ground truth              |
| Prefetch            | Execution window          |
| AmCache             | Program history           |


---

## 🗑 Did someone try to hide?

| Artifact      | What it reveals       |
| ------------- | --------------------- |
| Recycle Bin   | Deletions             |
| ShellBags     | Deleted folder traces |
| AmCache       | Deleted executables   |
| Shadow Copies | Previous state        |
| Registry logs |  Rolled-back changes  |
 

---

## 🧬 Was malware present?

| Artifact        | Why                |
| --------------- | ------------------ |
| Services        | Malicious services |
| Run keys        | Startup loaders    |
| BAM/DAM         | Silent execution   |
| ShimCache       | Dropped binaries   |
| AmCache         | Hashes & paths     |
| Scheduled Tasks | Triggers           |
  

---

# 🗺 HIVE RESPONSIBILITY MAP

| Hive        | Primary Use               |
| ----------- | ------------------------- |
| SAM         | Accounts, RIDs, hashes    |
| SYSTEM      | Boot, services, devices   |
| SECURITY    | Logons, secrets           |
| SOFTWARE    | Installed apps, OS config |
| NTUSER      | User behavior             |
| USRCLASS    | Shellbags, COM artifacts  |
| Amcache.hve | Execution & install       |


---

# ⚖️ EVIDENCE STRENGTH HIERARCHY

Strongest (hard to fake):
- Event logs
- AmCache
- MFT + USN
- Prefetch

Medium:
- BAM/DAM
- ShimCache
- UserAssist

Weak alone (supporting evidence only):
- RecentDocs
- TypedPaths
- Jump lists

---

# ⚠️ COMMON FORENSIC TRAPS

- SAM ≠ proof of login  
- ShimCache ≠ guaranteed execution  
- Deleted file ≠ gone  
- One artifact ≠ conclusion  
- Tool output ≠ evidence  

---

# 🧠 TRIAGE DECISION FLOW

Start →  
Who used system? → SAM, ProfileList  
Who logged in? → Security.evtx  
What ran? → Prefetch, AmCache, BAM  
What did user do? → NTUSER, JumpLists  
Any USB? → USBSTOR, SetupAPI  
Persistence? → Run keys, services, tasks  
Covering tracks? → Recycle bin, shadow copies


---

# 🎯 CTF FAST MODE

If time is low, hit in this order:

1. Users → SAM  
2. Execution → Prefetch + AmCache  
3. User activity → NTUSER  
4. USB → USBSTOR  
5. Persistence → Run keys + Tasks  
6. Timeline → MFT + Event logs  

---

# 🧱 FINAL RULE

> **If an artifact cannot answer a question, stop forcing it.  
> Move to the artifact that was built to answer that question.**


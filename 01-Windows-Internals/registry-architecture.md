# Windows Registry Architecture

## Accessing the Registry

- **Live system:** `regedit.exe`  
- **Disk image / triage:** Exported registry hives

Primary system hive location:
`C:\Windows\System32\config\`


---

## Core System Hives

| Hive File | Mounted Registry Key        |
| --------- | --------------------------- |
| DEFAULT   | HKEY_USERS\.DEFAULT         |
| SAM       | HKEY_LOCAL_MACHINE\SAM      |
| SECURITY  | HKEY_LOCAL_MACHINE\Security |
| SOFTWARE  | HKEY_LOCAL_MACHINE\Software |
| SYSTEM    | HKEY_LOCAL_MACHINE\System   |


---

## User Hives

Each user account maintains its own registry hive:
```
C:\Users<username>\NTUSER.DAT  
C:\Users<username>\AppData\Local\Microsoft\Windows\UsrClass.dat
```

| Hive         | Purpose                                             |
| ------------ | --------------------------------------------------- |
| NTUSER.DAT   | User activity, execution history, dialogs, Run keys |
| UsrClass.dat | Shellbags, Explorer classes, folder views           |
⚠️ Both files are hidden by default.

---

## Amcache Hive

Tracks executed programs and binary metadata.
Contains:
- Execution paths  
- First/last run timestamps  
- SHA1 file hashes  
- Installation artifacts  

---

## Transaction Log Files

Registry writes are first stored in transaction logs.

Location: same directory as the hive file.

Examples:
```
SAM.LOG  
SYSTEM.LOG1  
SOFTWARE.LOG2
```
⚠️ Transaction logs often contain newer data than the hive itself.

---

## Registry Backups

`C:\Windows\System32\config\RegBack\`
Contains:
- Periodic hive backups  
- Useful when keys were deleted or modified

---

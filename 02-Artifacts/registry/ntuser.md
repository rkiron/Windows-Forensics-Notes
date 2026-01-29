# NTUSER.DAT - User Activity Hive

Each local user account has a personal registry hive.

Location: `C:\Users<username>\NTUSER.DAT`

Mounted as: `HKEY_CURRENT_USER`

---

## Recent Files
Location:
`Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs`

Per-extension view: `...\RecentDocs.pdf` (for .pdf type files)

Contains: 
- File names
- MRU order 
- Last opened timestamps

---


## Microsoft Office Recent Files
```
Software\Microsoft\Office<VERSION>  
Software\Microsoft\Office<VERSION>\UserMRU\LiveID_####\FileMRU
```

Contains:
- Full file paths  
- Cloud-linked documents  
- Document open history  

---

## Open/Save Dialog MRUs
```
Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU  
Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU
```

Tracks:
- Files opened/saved  
- Application-specific paths  

---

## Explorer Search & Address Bar
```
...\Explorer\TypedPaths  
...\Explorer\WordWheelQuery
```

Tracks:
- Typed directories  
- Search queries

---

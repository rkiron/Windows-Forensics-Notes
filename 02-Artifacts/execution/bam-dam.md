# BAM & DAM – Background Execution Evidence

BAM (Background Activity Monitor) and DAM (Desktop Activity Moderator) track background application usage.

Locations:
```
SYSTEM\CurrentControlSet\Services\bam\UserSettings{SID}  
SYSTEM\CurrentControlSet\Services\dam\UserSettings{SID}
```

Contains:
- Full executable paths  
- Last execution times  
- Per-user activity correlation  

Used to detect:
- Background malware  
- Persistence loaders  
- Suspicious scheduled execution


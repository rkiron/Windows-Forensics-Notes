# Windows 10 Timeline
Windows 10 stores recently used applications and files in an SQLite database called the Windows 10 Timeline.


Location: 
`C:\Users\<username>\AppData\Local\ConnectedDevicesPlatform\{randomfolder}\ActivitiesCache.db`

Contains:
- Info about last used applications/programs
- focus time of application

Used to find:
- for how long was a particular/any application used

Tools to parse:
- WxtCmd.exe

Commands:
```bash
WxTCmd.exe -f <path-to-timeline-file> --csv <path-to-save-csv>
```

Limitations:
- Not available on Windows 11
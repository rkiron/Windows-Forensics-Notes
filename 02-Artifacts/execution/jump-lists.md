# Windows Jump Lists
Helps users go directly to their recently used files from the taskbar.

Location: 
`C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations`

Contains: 
- info about executed applications
- first time of execution
- last time of execution against AppID

Tools to parse: 
- JLECmd.exe

Commands:
```bash
JLECmd.exe -f <path-to-Jumplist-file> --csv <path-to-save-csv>
```

Limitations:
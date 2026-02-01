# Windows Prefetch Files
Files with info about the programs/applications run on windows. (.pf extension)

Location: `C:\Windows\Prefetch`directory

Contains:
- Last run time of application
- No of times run
- Files and device handles used by the file.

Used to find:
- last executed programs
- last executed/used files 
- time of execution of a certain program

Tools to parse:
- PECmd.exe (Prefetch Parser)

*Commands*:

on a file: 
```bash
PECmd.exe -f <path-to-Prefetch-files> --csv <path-to-save-csv>
```

on a directory: 
```bash
PECmd.exe -d <path-to-Prefetch-directory> --csv <path-to-save-csv>
```

# IE/Edge History
---

Location:
`C:\Users\<username>\AppData\Local\Microsoft\Windows\WebCache\WebCacheV*.dat`

Contains:
- files opened in the system

Note: 
The files/folders accessed appear with a `file:///*` prefix in the IE/Edge history.

Tools to parse:
- Autopsy

Guide: 
(*Using Autopsy*)

- Open Autopsy and make a new case
- In data source type select "Logical Files"
- Set the path for the data source
- For module: select "Recent Activity"
- In left panel you will get a folder named "Web history", click on it and inspect
- The details will be shown in the right panel (top:overall and bottom: detailed)


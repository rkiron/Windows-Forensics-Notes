# Shortcut Files 
---

Windows creates a shortcut file for each file opened either locally or remotely.

Location:
```
C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\

C:\Users\<username>\AppData\Roaming\Microsoft\Office\Recent\
```


Contains:
- what was opened/accessed
- from where: path of opened file
- by whom
- when: first, last opening times of file

Tools to parse: 
- LECmd.exe (Lnk explorer)

Commands:
```bash
LECmd.exe -f <path-to-shortcut-files> --csv <path-to-save-csv>
```

Note: 
- creation date  -> when the file was first opened
- modification date -> when the file was last accessed
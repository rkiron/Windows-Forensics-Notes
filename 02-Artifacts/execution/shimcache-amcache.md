# ShimCache & AmCache – Program Execution Artifacts

---

## ShimCache (AppCompatCache)

SYSTEM hive:
`SYSTEM\CurrentControlSet\Control\Session Manager\AppCompatCache`


Tracks:
- Executed binaries  
- File paths  
- Last modified timestamps  

Tool:
```bash
AppCompatCacheParser.exe --csv out/ -f SYSTEM -c ControlSet001
```

---

## Amcache
`C:\Windows\AppCompat\Programs\Amcache.hve`


Contains:
- Program execution evidence  
- Install/uninstall artifacts  
- SHA1 hashes  
- Deleted binary remnants  

Primary path:
`Root\File{Volume GUID}\`


# KAPE – Registry Acquisition

KAPE (Kroll Artifact Parser and Extractor) is a forensic triage framework designed for fast, targeted evidence collection.

---

## Typical Registry Output Locations
```
Triage/Registry/  
Triage/C/Windows/System32/config/
```

Expected files:
- SAM  
- SYSTEM  
- SECURITY  
- SOFTWARE  
- DEFAULT  
- Amcache.hve  
- *.LOG, *.LOG1, *.LOG2  

---

## Why KAPE is Used

- Rapid incident response triage  
- Selective artifact targeting  
- Automated parsing modules (RECmd, RegRipper, EvtxECmd)

---

## Post-Collection Validation

Verify hive integrity:

```bash
file SAM
file SYSTEM
```

Expected: 
```bash
MS Windows registry file, NT/2000 or above
```

---

## Local Account Extraction
```bash
impacket-secretsdump -sam SAM -system SYSTEM LOCAL
```

Extracts: 
- Local Users
- RIDs
- NTLM password hashes
- Account status

---

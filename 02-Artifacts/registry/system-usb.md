# USB & External Device Forensics

---

## Device Identification

```
SYSTEM\CurrentControlSet\Enum\USBSTOR  
SYSTEM\CurrentControlSet\Enum\USB
```


Stores:
- Vendor ID  
- Product ID  
- Serial numbers  

---

## First and Last Connection Times

`SYSTEM\CCS\Enum\USBSTOR<device>\Properties{83da6326-97a6-4088-9453-a19231573b29}\####`

"####" sign can be replaced by the following digits

| Value | Information           |
| ----- | --------------------- |
| 0064  | first connection time |
| 0066  | last connection time  |
| 0067  | last removal time     |

---

## USB Device Volume Names

Device name of connection drive
`SOFTWARE\Microsoft\Windows Portable Devices\Devices`


---





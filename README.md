![image](https://user-images.githubusercontent.com/53458032/218345232-227d4831-cc13-4d87-93ce-a858c689f26b.png)

### Windows ISO & Activation
[massgrave.dev](https://massgrave.dev/index.html)

Windows Shortcuts:
[https://ss64.com/nt/run.html](https://ss64.com/nt/run.html)

```
WIN + R - SystemPropertiesPerformance

☐  Animate controls and elements inside windows
☐  Animate widnows when minimzing and maximizing
☐  Animations in the taskbar
☐  Enable Peek
☐  Fade or slide menus into view
☐  Fade or slide ToolTips into view
☐  Fade out menu items after clicking
☐  Save taskbar thumbnail previews
☐  Show shadows under mouse pointer
☐  Show shadows under windows
☑  Show thumbnails instead of icons
☐  Show translucent selection rectangle
☐  Show window contents while dragging
☐  Slide open combo boxes
☑  Smooth edges of screen fonts
☐  Smooth-scroll list boxes
☐  Use drop shadows for icons labels on the desktop
```

```
WIN + R - ncpa.cpl - Select NIC, then select Properties.

☐  Client for Microsoft Networks
☐  File and Printer Sharing for Microsoft Networks
☑  Npcap Packet Driver (NPCAP)  <-- Wireshark
☐  QoS Packet Scheduler
☑  Internet Protocol Version 4 (TCP/IPv4)
☐  Microsoft Network Adapter Multiplexor Protocol
☐  Microsoft LLDP Protocol Driver
☑  Internet Protocol Version 6 (TCP/IPv6)
☐  Link-Layer Topology Discovery Responder
☐  Link-Layer Topology Discovery Mapper I/O Driver
```

```
WIN + R - mmsys.cpl

Playback | WIN + R - control mmsys.cpl,,0
☐ Show Disabled Devices
☐ Show Disconnected Devices

Recording Tabs | WIN + R - control mmsys.cpl,,1
☐ Show Disabled Devices
☐ Show Disconnected Devices

Sounds Tab | WIN + R - control mmsys.cpl,,2
Sound Scheme:
- No Sounds

Communications Tab | WIN + R - control mmsys.cpl,,3
☐ Do nothing
```

### BIOS Keys by Manufacturer
`shutdown /r /fw /f /t 0`
|Manufacturer|Key/Sequence|
|-|-|
|ASRock|`F2` or `DEL`|
|ASUS|`F2` for all PCs, `F2` or `DEL` for Motherboards|
|Acer|`F2` or `DEL`|
|Dell|`F2` or `F12`|
|ECS |`DEL`|
|Gigabyte / Aorus|`F2` or `DEL`|
|HP|`F10`|
|Lenovo (Consumer Laptops)|`F2` or `Fn` + `F2`|
|Lenovo (Desktops)|`F1`|
|Lenovo (ThinkPads)|Enter then `F1`.|
|MSI|`DEL` for motherboards and PCs|
|Microsoft Surface Tablets|Press and hold `volume up` button.|
|Origin PC|`F2`|
|Samsung|`F2`|
|Toshiba|`F2`|
|Zotac|`DEL`|

### Installation Error Code 2502 & 2503 FIX
Open CMD as admin then paste these commands in:
```batch

msiexec /unreg
msiexec /regserver

takeown /f “%systemroot%\Temp” /R /A /D Y
icacls “%systemroot%\Temp” /inheritance:r /grant:r Users:(OI)(CI)F /T
icacls “%systemroot%\Temp” /inheritance:r /grant:r Everyone:(OI)(CI)F /T
icacls “%systemroot%\Temp” /grant Administrators:F /T
icacls “%systemroot%\Temp” /grant Users:F /T
icacls “%systemroot%\Temp” /grant SYSTEM:F /T
icacls “%systemroot%\Temp” /grant Everyone:F /T
takeown /f “%temp%” /R /A /D Y
icacls “%temp%” /inheritance:r /grant:r Users:(OI)(CI)F /T
icacls “%temp%” /inheritance:r /grant:r Everyone:(OI)(CI)F /T
icacls “%temp%” /grant Administrators:F /T
icacls “%temp%” /grant Users:F /T
icacls “%temp%” /grant SYSTEM:F /T
icacls “%temp%” /grant Everyone:F /T
```

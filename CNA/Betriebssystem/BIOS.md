BIOS steht für Basic Input Output System

Das BIOS enthält ein sehr einfaches [[Betriebssysteme|OS]] in einem Flash-[[Speicher]]

Das BIOS ist in einem separaten Chip realisiert

Heute: UEFI-BIOS mehr Optionen, ermöglicht Secure Boot → Alternative Coreboot

Beim Einschalten des Rechners wird folgendermassen forgegangen:
- Start des BIOS
- POST (Power On Self-Tests)
- Abfrage aller angeschlossenen Geräten und statischen Adressbereichen (für [[Interrupts|Interrupt]] Requests und I/O)
- Optionaler Start des Benutzerinterfaces mittels F1, F2, F10, F11, F12, Esc, Del
- Rückübermittlung der dynamisch zugewiesenen Adressbereiche an Gerätecontroller
- Ermittlung des Boot Device
- Laden der ersten Routinen des [[Betriebssysteme|OS]] 
- Start des [[Betriebssysteme|OS]]
- [[Betriebssysteme|OS]] übernimmt Geräteinforrmationen, überprüft Vorhandensein der Treiber und lädt die Treiber
- Start von Hintergrund und Vordergrundprozessen
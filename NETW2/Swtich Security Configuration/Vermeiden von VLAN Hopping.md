3 Arten für Vlan Hopping: 
- DTP Spoofing, 
- Rouge Switch, 
- double tagging

**Schritte**
- `swtichport mode access|runk` explizit setzen
- unused ports disalbed und in leeres vlan
- Bei trunks `switchport nonegotiate` setzen
- Native VLAN setzen `switchport trunk native vlan ID`
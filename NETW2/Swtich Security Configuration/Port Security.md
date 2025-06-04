**Disable Unused Ports**
Unused Ports mit `S1(config-if)# shutdown` deaktivieren.

Portsecurity limitiert die Anzahl der gültigen MACs pro Port.
Erlaube MACS können **statisch** konfiguriert oder **erlernt** werden.

Damit Port-Security eingeschaltet werden kann, muss sich der Port im Access/Trunk-Mode befinden.


## Commands
**Port-Security einschalten:**
```
S1(config-if)# switchport port-secuirty
```

**Max Anzahl an MAC setzen**
Default ist `1`
```
S1(config-if)# switchport port-secuirty maximum value
```

**MAC statisch Konfigurieren**
```
S1(config-if)# switchport port-secuirty mac-address MAC-ADDRESS
```

**MAC Lernen-Sticky**
Defaultmässig werden MAC-Adressen gelernt, gehen aber nach einem Reboot verloren.
Mit `sticky` kann das verhindert werden.
```
S1(config-if)# switchport port-secuirty sticky
```

**Aging**
Bei Port-Security-Aging gibt es zwei Modi: 
- **Absolute**: Löschen der gespeicherten MAC nach Ablauf der Zeit
- **Inactivity**: Löschen der gespeicherten MAC nachdem für gewisse Zeit inaktiv.
```
S1(config-if)# switchport port-secuirty aging time TIME
S1(config-if)# switchport port-secuirty aging type absolute|inactivity
```

**Port Disabled-State**
Wenn eine MAC-Adresse ein Port anspricht und die Reglen verletzt kommt der Port in den error-disabled-state.

```
S1(config-if)# switchport port-secuirty violation OPTION
```

| Mode               | Beschreibung                                                                                     |
| ------------------ | ------------------------------------------------------------------------------------------------ |
| shutdown (default) | Syslog-Msg, Security-Counter ++, Port muss manuell enabled werden (`shutdown` und `no shutdown`) |
| restrict           | Syslog-Msg, Drop von Paketen von Unbekannten MAC, Security-Counter ++                            |
| protect            | Drop von Paketen von Unbekannten MAC                                                             |


**Abfragen**
```
S1# show port-security inteface INTERFACE
S1# show port-security address
S1# show port-security
```

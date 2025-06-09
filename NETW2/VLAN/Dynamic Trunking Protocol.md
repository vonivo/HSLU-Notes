Dynamic Trunking Protocol ist ein Cisco proprietäres Protokoll welches das automatische Etablieren eines [[Trunk-Link]] erlaut:


## Optionen
Folgende Optionen werden mit `swtichport mode <mode>` gesetzt:

| Optioan           | Beschreibung                                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------ |
| access            | Permanente Zuweisung zu Access. Versucht gegenüberligenden Link zu Access zu bringen                                     |
| dynamic auto      | Wird zu Trunk wenn das gegenüberliegende Interface ein Trunk oder Desirable ist.                                         |
| dynamic desirable | Versucht aktiv zu einem Trunk zu werden. Verhandelt mit gegenüberligenden Interface wenn es `auto` oder `desirable` ist. |
| trunk             | Permanenter `trunk`. Versucht gegenüberligenden Link zu `trunk` zu bringen.                                              |

|                   | Dynamic Auto | Dynamic desirable | Trunk   | Access   |
| ----------------- | ------------ | ----------------- | ------- | -------- |
| Dynamic Auto      | `access`     | `trunk`           | `trunk` | `access` |
| Dynamic desirable | `trunk`      | `trunk`           | `trunk` | `access` |
| trunk             | `trunk`      | `trunk`           | `truk`  | fehler   |
| Access            | `access`     | `access`          | fehler  | `access` |


## Konfiguration
**Ausschalten**
DTP kann ausgeschaltet werden, mit `nonegotiate`.
```
S1(config-if)# switchport nonegotiate
```
Wird ein Port statisch als Trunk oder Access konfiguriert, gibt es keine Verhandlungs-Issues.

**Auslesen**
```
S1# show dtp interface <interface>
```

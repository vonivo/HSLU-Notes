Ein Switch kann in Voll-Duplex und Halb-Duplex laufen.

## Voll-Duplex
Die Leitung kann **gleichzeitiges** **Senden** und **Empfange**.
- Steigert Bandbreiten-Effektivität.
- Keine Collision Domain.
- Verdoppelung der Bandbreite.
## Halb-Duplex
- Switch kann nicht gleichtzeitig Senden und Empfangen.
- Erzeugt Performance-Probleme und Kollisionen.
- 10 Gb Interfaces benötigen Voll-Duplex.

## Konfiguration
Der Standard für `duplex` und `speed` ist auto. So vereinbart der Switch passende Werte mit dem Kommunikationspartner.

```
S1(config-if)# duplex full
S1(config-if)# speed 100
```

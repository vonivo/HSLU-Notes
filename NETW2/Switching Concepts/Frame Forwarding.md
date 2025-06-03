Ein [[Frame]] in einem Switch kann auf zwei Arten klassifiziert werden:
- **Ingress** -> [[Frame]] "betritt" das Interface
- **Egress** -> [[Frame]] "verlässt" das Interface.

Ein Switch leitet ein [[Frame]] basierend auf dem **Ingress-Interface** und der **Ziel-MAC-Adresse** weiter.

>[!error]
>Ein Switch erlaubt niemals das Forwarden auf das Ingress-Interface.



## Prozess
Der Prozess gliedert sich in 2 Schritte:
1. Learn - Untersuchen der Source-Adresse
	- Source-Adresse zu Tabelle hinzufügen (falls nicht vorhanden)
	- Timeout auf 5min resetten, falls Eintrag vorhanden.
2. Forward - Untersuchen der Ziel-Adresse
	- Wenn die Ziel-Adresse in der Tabelle vorhanden ist, an Egress-Interface weiterleiten.
	- Wenn Ziel-Adresse nicht vorahnden, auf alle Interfaces ausser dem Ingress flooden.

## Forwarding Methoden
Ein Switch kennt zwei forwarding Methoden:
- [[Store-and-Forward]]
- [[Cut-Through]]

Ein Switch nutzt folgendes um Congestions zu vermeiden:

| Protocol                | Funktion                                                          |
| ----------------------- | ----------------------------------------------------------------- |
| Fast Port Speeds        | Bis zu 100 Gbps port speed                                        |
| Fast Internal Switching | Nutzt schnelle busse oder shared memory -> perfomance improvement |
| Lagre Frame buffers     | Temporäres speicher während dem verarbeiten von vielen Frames     |
| Hig Port Density        | Mehr lokaler Traffic.                                             |

Die Überlastüberwachung stellt sicher, dass das [[Netzwerke|Teilnetzwerk]] in der Lage ist, den Verkehr zu bewältigen.

# Überlast
>[!info] Definition
>Eine Überlast liegt vor, wenn die Last des Netzes grösser ist, als die verfügbaren Ressourcen.

Wenn eine Überlast eingetreten ist, sinkt die Leistung rapide ab.
![[Überlast.png]]

# Prinzipien der Überlastüberwachung
Die Überlastüberwachung läuft in drei Punkte ab, welche immer wieder wiederholt werden:

1. Überwachung des Systems.
	Erkennen von Überlastungen: wann und wo.
2. Weitergabe dieser Information and die Stelle, welche Gegenmassnahmen ergreifen kann.
3. Anpassung des Systembetriebs, um das Problem zu korrigieren:
	- durch Reduktion der Last,
	- durch Erhöhung der Ressourcen

# Massnahmen

| Schicht             | Massnahme                                                                                                                                                              |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [[Transport-Layer]] | - Timeout für erneute Übermittlung<br>- Zwischenspeichern von Out-of-Order-Pakete<br>- Bestätigungen (einzeln oder gesammelt)<br>- Flusskontrolle (straff oder locker) |
| [[Network-Layer]]   | - Warteschlangen für Pakete<br>- Verwerfen von Paketen (bei niedriger Prio / Lebensdauer / neue Pakete)<br>- Managment der Paket-Lebensdauer                           |
| [[Data-Link-Layer]] | - Timeout für erneute Übertragung<br>- Zwischenspeicherung von Out-of-Order-Frames<br>- Bestätigugn einzeln oder gesammelt<br>- Flusskontrolle                         |
![[Überlastüberwachung.png]]
## Lastabwurf
Kann die Überlastung nicht eingedämmt werden, so können Router die Pakete einfach verwerfen: **Lastabwurf**
- Abwurf nach Zufallsprinzip
- Abwurf nach ältesten/neusten Pakete
- Abwurf der tief priorisierten Pakete

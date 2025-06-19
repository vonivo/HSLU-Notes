>[!Definition]
>Das Gesamtsystem konvergiert gegen die aktuellen Daten. Die Konsistenzanforderung **Eventual Consistency** erlaubt, dass ein System zu einem Zeitpunkt $T$ noch mit veralteten Daten arbeitet.

Eventual Consistency wird typischerweise in Verbindung mit **Monotonic Reads** genutzt:
- Aufeinanderfolgende Leseoperationen auf ein Objekt O sehen entweder den gleichen oder einen aktuelleren Wert als den zuletz gelesenen.

**Nutzen**
- Zeitliche Entkoppelung, Verfügbarkeit, tolerieren von Netzpartitionierung.

**Einsatz**
Falls Daten nicht immer aktuell sein müssen und
	Falls nur eine Instanz die Hoheit über Modifikationen besitzt oder
	nur Schreiboperationen getätigt werden.

## Beispiel
Besucher eines Profils $P$ werden in Liste $L$ gespeichert. Beim Betrachten von Profil $P$ sieht der Besitzer Liste $L$.

- $P\implies L_{t}$ erhalte Liste der letzten Besucher von Profil $P$ zum Zeitpunkt $t$
- $L_{t}\implies P$ füge Besucher $B$ zur Liste von Profil $P$ hinzu.

**Erfüllt**:
![[eventualConsistency.png]]
$$
L_{1} \implies P|P\implies L_{1}|L_{2}\implies P|L_{3} \implies P|P\implies L_{3}|\dots
$$

**Nicht Erfüllt:**
![[eventualConsistency2.png]]

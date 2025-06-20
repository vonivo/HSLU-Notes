Jede Maschine hat eine eigene Zeit mit konstanten aber unterschiedlichen 
Geschwindigkeiten.
![[Lamport.png]]
- Ein Prozess sendet eine Nachricht mit dem Zeitstempel (eigen Zeit) an einen anderen Prozess.
- Einem Ereignis $a$ wird ein Zeitwert $C(a)$ zugeordnet.
	- Alle Prozesse sind sich über den Zeitwert einig
	-  Wenn $a->$ gilt auch $C(a) -> C(b)$
- Ein Prozess, welcher eine Nachricht zur eigenen Zeit $b$ empfängt, dann müssen $C(a)$ und $C(b)$ so zugewiesen werden, dass $C(a) < C(b)$ ist.
- Die Zeit **muss immer vorwärtslaufen**
- Korrektur durch Addition von positiven Werten

![[Lamport2.png]]Weiter dürfen zwei Ereignisse nie zu genau derselben (logischen) Zeit auftreten.
Daher wird der Zeitstempel um die Prozessnummer ergänzt.

## Eigenschaften
- Lamports Uhren erfüllen die Happened Before Relation: $a->b => C(a) -> C(b)$
- Definiert eine partielle Ordnung auf der Menge der Ereignisse, welche kausalen 
  Zusammenhang erhält.
- Ergänzung zu einer totalen Ordnung ist möglich

## Einschränkung
- Anhand der Zeitstempel lässt sich nicht sagen, ob zwei Ereignisse kausal 
  voneinander abhängen.

## Beispiel
Generationclock (GCL)
- Ein logischer Zeitstempel, welcher monoton inkrementiert wird pro Leader Election
- Persistente und transaktionssichere Speicherung
- Ziel: Nachrichten vergangener Leader können erkannt und ignoriert werden

**Ablauf**: 
1. Jeder Prozess P startet als Follower
2. P liest seine GCL von der Disk
3. Gibt es einen Leader übernimmt P dessen GCL
4. Ansonsten gibt es eine Leader Election (P inkrementiert sein GCL)
5. Leader sendet GCL bei jeder Request
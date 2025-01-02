Ein Spiel mit folgenden Bedingungen lässt sich als Baum darstellen:
- Es sind nur endlich viele Spielstellungen möglich.
- Es git keine Züge, die zu bereits vorgekommenen Stellungen führen.
- Es handelt sich um ein Spiel mit vollständiger Information, d.h. die Spieler kennen zu jedem Zeitpunkt die vollständige Spielsituation.
- Die Spielzüge sind nicht von Zufall bestimmt.

>[!Theorem]
>Wenn sich beide Spieler rational verhalten, d.h. das für sie jeweils beste tun, dann ist der Ausgang eines solchen Spiels immer derselbe.


Wir haben folgendes Spiel:
1. Ein Spielstein wird auf die Wurzel gesetzt.
2. Spieler 1 und 2 ziehen den Spielstein jeweils abwechselnd auf einer Kante in Pfeilrichtung auf einen neuen Knoten.
3. Natürlich kommt man irgendwann auf ein Blatt, dann ist das Spiel zu Ende.
4. Steht auf diesem Blatt eine positive (bzw. negative) Zahl, so hat Spieler 1 (bzw. 2) gewonnen. Eine 0 bedeutet Unentschieden.

**Ablauf:**
1. Für jede Ecke des Baumes wird ermittelt, welcher der beiden Spieler am Zug ist. Dazu muss nur bestimmt werden, wie weit diese Ecke von der Wurzel entfernt ist.
![[Pasted image 20250102153047.png]]
2. Nun betrachtet man nacheinander alle Knoten, die keine Blätter sind, an denen aber nur Blätter hängen.
   
   Der Spieler der in dieser Stellung angekommen und am Zug ist, wird natürlich den für ihnbesten Zug wählen. Damit ist der Spielausgang eigentlich schon hier klar!
   
   Man kann also den Wert des Zuges, den der Spieler wählen würde, in diesen Knoten schreiben (und alle Blätter wegwerfen).
![[Pasted image 20250102153211.png]]
2. In dem neuen (beschnittenen) Baum betrachtet wir wieder alle Knoten, die keine Blätter sind, an denen aber nur Blätter hängen. Der Spieler der in dieser Stellung angekommen und am Zug ist, wird natürlich den für ihn besten Zug wählen. Damit ist der Spielausgang schon hier klar!
   
   Man kann also den Wert des Zuges, den der Spieler wählen würde, in diesen Knoten schreiben (und alle Blätter wegwerfen).
   ![[Pasted image 20250102153308.png]]
   3. Dieses Verfahren wird nun so lange wiederholt, biss der Baum komplett ausgefüllt ist.![[Pasted image 20250102153341.png]]

Ist die Zahl an der Wurzel:
- **positiv** so bestitzt Spieler 1 eine Gewinnstrategie.
- **negativ** so bestitz Spieler 2 eine Gweinnstrategie.
- **gleich 0** so können beide Spieler ein Unentschieden erzwingen.

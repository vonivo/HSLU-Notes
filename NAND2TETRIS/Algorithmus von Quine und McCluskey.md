>[!Definition]
>Der Algorithmus von Quine und McCluskey erlaubt das Optimieren der Darstellung einer [[Boolesche Funktion]] durch [[Minterm|Minterme]]

Zuerst werden alle Minterme gesucht und per [[OR]] verknüpft.
![[Pasted image 20260615140602.png]]
In einem zweiten Schritt werden alle Minterme, welche sich nur in einer Stelle unterscheiden, zusammenaddiert.
Diese Stelle fällt dann weg:
![[Pasted image 20260615140848.png]]
Wenn ein Term nicht mehr weiter zusammenaddiert werden kann, wird er mit einem $P_{x}$ versehen
![[Pasted image 20260615141019.png]]

Nun wird folgende Tabelle erstellt:
![[Pasted image 20260615141117.png]]
Die Zellen erhalten einen Punkt, wenn der Term $P_{x}$ den Minterm $m_{y}$ enthält.
>[!Error]
>Spalten die eine **Erweiterung** einer anderen Spalte sind, müssen nicht mehr betrachtet werden.




Nun wird nach der Spaltendominanz geprüft und alle dominierten Spalten entfernt:
![[Pasted image 20260615141346.png]]
>[!Error]
>Zeilen, die ein Teil einer anderen Zeile sind, können gestrichen werden.

![[Pasted image 20260615141621.png]]

Nun wird abwechslungsweise weiter gearbeitet, bis nichts mehr gestrichen werden kann.
![[Pasted image 20260615141718.png]]

Resultat: $Y= P_{3}+P_{5}+P_{6}= x_{0}x_{1}x_{3}+\bar{x_{1}}\bar{x_{2}}+x_{2}\bar{x_{3}}$


![[VektorZeitstempel.png]]
Da beim Leitstand das Signal "Druck erhöhen" schneller ankommt als "Druckverlust" macht er eine falsche Schlussfolgerung.

**Definition**
- Ein Vektorzeitstempel $VT(a)$, der einem Ereignis $a$ zugewiesen wurde, hat die 
  Eigenschaft, dass das Ereignis $a$ dem Ereignis $b$ kausal vorausgeht, wenn: $VT(a) < VT(b)$ gilt.
- Jeder Prozess $P_i$ besitzt einen Vektor $V_i$ für jeden Prozess im System
  die Anzahl der Ereignisse enthält mit den Eigenschaften
	- $V_i$ ist die Anzahl der Ereignisse, welche in $P_i$ bisher aufgetreten sind.
	- wenn gilt $V_i [j]=k$ erkennt $P_i$, dass in $P_j$ k Ereignisse aufgetreten sind.
- Der Vektor $V_i$ wird den gesendeten Nachrichten mitgegeben.

*Algorithmus*
+ Jeder Prozess $P_i$ hält Vektor bestehend aus $n$ Zeilen ($n$ = Anzahl Prozesse)
+ Initial ist der Vektorzeitstempel der Null-Vektor
+ Tritt beim Prozess $P_i$ ein Ereignis auf, so inkrementiert er die $i$-te Komponente seines Vektors
+ Sendet $P_i$ eine Nachricht, so wird der Vektor mitgesendet
+ Empfängt $P_i$ eine Nachricht
	- Bildet neuen Vektor mit dem komponentenweise Maximum
	- Inkrementiert beim neuen Vektor die Komponenten $i$
![[VektorZeitstempel2.png]]

Der Vektorzeitstempel enthält:
- die Anzahl Ereignisse die in $P_i$ aufgetreten sind.
- wie viele Ereignisse in anderen Prozessen der Nachricht vorausgegangen sind.
- wie viele vorangegangene Ereignisse möglicherweise kausal abhängig sind.

Ereignis $A$ ist eine Ursache von Ereignis $B$ wenn:
- der Zähler für jeden Prozess im Zeitstempel $VT(A)$ kleiner oder gleich dem
  Zähler im Zeitstempel $VT(B)$ für den korrespondierenden Prozess ist.
- Mindestens ein Zähler kleiner ist.

**Beispiel**
- $vec(2,0,0)$ ist Ursache für $vec(4,0,1)$
- $vec(1,1,2)$ ist Ursache für $vec(1,2,3)$
- $vec(2,1,3)$ ist keine Ursache für $vec(1,3,4)$
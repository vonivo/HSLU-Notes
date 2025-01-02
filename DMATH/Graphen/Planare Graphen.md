>[!Definition]
>Ein [[DMATH/Graphen/Graph|Graph]] (oder eine [[Isomorphie|isomorphie]] dazu.) heisst **planar**, wenn er sich in der Ebene **ohne Kantenkreuzung** zeichnen lässt.

>[!Theorem]
>Ein Graph ist genau dann **nicht** planar, wenn er einen Untergraphen vom Typ $K_{3,3}$ oder $K_{5}$ enthält. Somit sind sicher $K_{3,3}$ und $K_{5}$ nicht planar.



**Beispiel 1**
Is der folgende Graph planar?
![[Pasted image 20250102112335.png]]
Ja, denn es gibt einen isomorphen Graphen dazu, welcher planar ist:
![[Pasted image 20250102112357.png]]


**Beispiel 2**
Zeige dass der vollständige Graph $K_{3,3}$ nicht planar ist.
![[Pasted image 20250102112543.png]]
1. Wir beginnen mit den Knoten $v_{1},v_{2},v_{3},5$ und sie verbindenden Kanten.
![[Pasted image 20250102112724.png]]
	dadurch schaffen wir die Flächen $F_{1}, F_{2}, F_{21}, F_{22}$,
2. Da $v_{6}$ mit $v_{1},v_{2},v_{3}$ verbunden werden muss, können wir ihn nicht mehr platziere, ohne eine Kante zu schneiden, egal inwelcher Fläche.
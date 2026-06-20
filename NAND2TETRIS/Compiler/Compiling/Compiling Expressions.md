Es gibt verschiedene Arten eine Expression überhaupt zu notieren:
- **Infix**: `x+y-2` → wird von Menschen verwendet.
- **Postfix**: `x y + 2 -` → geeignet für [[Stack-Machine]]

Postfix is für den Stack gut geignet, da immer das letzte Resultat oben auf dem Stack anliegt.

Beim Parsen von Programmcode könnte der Baum so aussehen:
![[Pasted image 20260620104521.png]]
Um nun die Postfixnotation zu erhalten werden immer die beiden Blätter nacheinander auf den Stack gelegt und dann der Parent.

**Beispiel:**
![[Pasted image 20260620104720.png]]
Wird zu `x y 1 + 7 - call foo`

## Rekursive Kompilation
Da die Grammatik von einer `Expression` sich rekursiv aufrufen kann, kann auch die Kompilation rekursiev gemacht werden:
![[Pasted image 20260620104950.png]]
Hier wird mit `compileExpression` und `compileTerm` gearbeitet, welche sich gegenseitig aufrufen können.
>[!Error]
>Ein Funktionsaufruf wird hier wie jeder andere Term behandelt. Einfacher Trick, welcher viel Arbeit erspart.

Durch die Stack-Semantik und die Postifxnotation liegt immer der Wert welcher interessant ist zu oberst auf dem Stack.
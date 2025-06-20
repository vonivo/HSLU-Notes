Leslie Lamport zeigte, dass es ausreichend ist, wenn alle Maschinen
innerhalb eines Systems über dieselbe Zeit einig sind. Eine **Übereinstimmung mit der Zeit ausserhalb des Systems ist nicht notwendig**. Diese Form von Zeit wird **Logische Zeit** genannt.

Logische Zeit findet vor allem in Bereichen Anwendung, in denen Kausalitäten und 
Verlässlichkeit wichtig ist. Verfahren zur **Synchronisation von logischen Uhren** 
sind in grossen Systemen **im Allgemeinen ineffizient**.

Methoden:
- [[Lamport Zeitstempel]]
- [[Vektorzeitstempel]]

## Happended Before Relation
Der Ausdruck $a -> b$ wird gelesen als "a passiert vor b" und bedeutet, dass **alle 
Prozesse einig** sind, dass **zuerst** Ereignis **a** stattfindet und **dann** **b**.

+ Wenn $a$ und $b$ Ereignisse im selben Prozess sind, und $a$ vor $b$ auftritt, gilt $a -> b$
+ wenn $a$ das Senden einer Nachricht bei einem Prozess und $b$ das Empfangen derselben Nachricht bei einem anderen Prozess ist, gilt $a->b$

Zwei Ereignisse $a!=b$ sind kausal unabhängig, geschrieben als $a || b$, wenn weder $a->b$ oder $b->a$ gilt.

Die Happended Before-Relation ist *transitiv*: $(a->b and b->c) -> (a->c)$
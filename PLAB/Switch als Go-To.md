Die Go-To Anweisung erschwert das lesen und verstehen von Code erheblich. Da es Sprünge im Code generiert.

Dies kann auch auf das switch-Statement angewendet werden, da Switches den Programfluss unterbrechen und an einer anderen Stelle weitermachen. Für Switch-Statements gibt es meist eine bessere Alternative, welche die Prinzipien von OOP nicht verletzen.

**Beispiel**
```java
class Character{...}
class Hobbit extends Character {...}
class Goblin extends Character {...}

switch (c)
	case c instanceof Hobbit {...}
	case c instanceof Goblin {...}
```
Wenn dieser Code so umgesetzt werden würde, muss jedes mal der Switch erweitert werden, wenn eine neue Subklasse von `Character` hinzukommt. Dies kann oft vergessen werden, was dann zu Fehler im Code führt.

Besser alternative wäre hier [[Polymorphie]] mit einer Abstract-[[Methode]] auf der `Character`-[[Klasse]].
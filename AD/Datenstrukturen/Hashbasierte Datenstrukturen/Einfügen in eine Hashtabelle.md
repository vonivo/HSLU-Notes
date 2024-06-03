Beim Einfügen in eine [[Hashtabelle]] wird zuerst der Index berechnet und Anhand einer potenziellen Sondierungskette der Platz im Array gesucht.

## Beispiel
Array-Grösse: 10
Hash-Berechnung: `ascii(x) - 97 = hashCode`
Index-Berechnung: `hashCode % 10 = index`

Nun werden die Buchstaben `o` (`index('o') = 4`), `o` (`index('x') = 3`) und `h` (`index('h') = 7`) eingefügt.
![[HashTable_insert.png]]

Die [[AD/Algorithmen/Komplexität]] für das Einfügen ist $O(1)$.

### Kollision
Nun soll das Element `d` (`index('d') = 3`) eingefügt werden.
Da der Platz `3` schon besetzt ist, wird der nächst freie auf der rechten Seite gesucht, in diesem Fall `5`.
![[HashTablle_insert_collision.png]]
$\implies$ Es entsteht eine **Sondierungskette** (x -> o -> d).
[[AD/Algorithmen/Komplexität]]: im Schlimmsten Fall $O(n)$.
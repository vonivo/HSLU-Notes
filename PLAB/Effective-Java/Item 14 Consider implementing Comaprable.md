Mit der Implementation von `Comparable<>` [[compareTo & Comparable#compareTo ( Interface Comparable)|Comparable]]
erlauben wir dieser Klasse mit allen generischen Algorithmen und Collection-Implementationen zu interagieren.

Wenn eine Value-Klasse eine natürliche Ordnung besitzt, sollte `Comarable<>` unbedingt implementiert werden.

## Vertrag
- Gibt `-1`, `0` oder `1` zurück. Basierende darauf ob das Objekt kleiner, gleich oder grösser ist.
- `sgn(x.compareTo(y) == -sgn(y.compareTo(x)`
- Transitiv: `(x. compareTo(y) > 0 && y.compareTo(z) > 0)` impliziert `x.compareTo(z) > 0`
- Es ist sehr stark empfohlen, dass `(x.compareTo(y) == 0) == (x.equals(y))` ist. Wenn dies nicht der Fall ist, **muss dies dokumentiert werden**.


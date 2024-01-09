## Equals-Vertrag
- **Reflexivität** bei Vergleichen mit sich selbst:
	`x.equals(x)` liefert immer `true`.
- **Symmetrie**:
	`x.equals(y)` und `y.equals(x)` liefern dasselbe Resultat.
- **Transitivität**:
	Falls `x.equals(y) == true` und `y.equals(z) == true` dann soll auch `x.equals(z)` das Resultat `true` liefern.
- **Konsistenz** bei wiederholten Vergleichen:
	Bei unveränderten Objekten gibt es immer das gleiche Resultat
- **Vergleich mit null**:
	`x.equals(null)` liefert immer `false`, **keine** `NullPointerException`.
- Sobald die `equals()` Methode überschrieben wird muss auch die [[HashCode-Methode|`hashCode()`-Methode]] überschreiben werden.

## Schema für die Implementation für Valuetypes
1. Test auf Identität mit `==`: $\implies$ `true` bei Identität sehr schnell.
2. Test auf `null`: $\implies$ `false`, weitere Aktionen nicht möglich
3. Test auf Typen-Vergleichbarkeit: $\implies$ `false` wenn anderer Typ.
4. Vergleich aller relevanten Attribute der Klasse.
	- Elementare Datentype: Vergleich mit `==`.
	- Referenzvariablen: Vergleich an `equals()` delegieren.
>[!info]
>Schritt **2** und **3** können bei der Verwendung von `instanceof` **gemeinsam** erledigt werden, weil der `null`-Test dort integriert ist.

## Beispiel
```
@Override 
public boolean equals(final Object object) { 
	if (object == this) { 
		return true; 
	} 
	
	return (object instanceof Person p) 
		&& (Objects.equals(p.name, this.name)) 
		&& (Objects.equals(p.lastname, this.lastname));
}
```

Folgende Zugriffsmodifizierer bestimmen die Sichtbarkeit von [[Attribut|Attributen]], [[Klasse|Klassen]], [[Abstrakte Klasse|Abstrakten Klassen]], [[Interface|Interfaces]](sind implizit immer public) und [[Methode|Methoden]].

`private` → nicht sichtbar ausserhalb der Klasse 
` ` → Package default sichtbar wenn im gleiche Package 
`protected` → sichtbar egal in welchem Package
`public` → sichtbar für alle Klassen

## Best Practices
- **So verschlossen wie möglich so offen wie nötig**
# public
- Maximale Sichtbarkeit, vollständig Öffentlich
	- Sichtbar in der Klasse selbst und auch in allen anderen Klassen egal in welchem Package

→ Was einmal öffentlich ist kann man nicht mehr zurücknehmen
**→ Bei Attributen sehr selten einsetzen**

UML Darstellung: +

# private
- Maximale Kapselung, vollständig privat
	- Ausschliesslich sichtbar in der Klasse selbst
	- Auch für eine [[Vererbung|Spezialisierung]] nicht sichtbar

→ Wird häufig bei Attributen und internen (Hilfs-)Methoden gebraucht

UML Darstellung: -


# package default
- Sichtbar in der Klasse selbst und für jede Klasse des selben Package
- Hat kein Schlüsselwort

→ Einsatz selten und wenn dann [[Klasse|Klassen]] und [[Methode|Methoden]]

UML Darstellung: ~


# protected
- Sichtbarkeit wie bei package default zusätzlich aber von allen [[Vererbung|spezialisierten]] Klassen.

→ Einsatz selten ehere bei [[Methode|Methoden]]

UML Darstellung: #

# Übersicht
![[Accessmodifiers.png]]
Der Musterautomat macht sich wie der [[Optimierter Suchautomat|optimierte Suchautomat]] einen [[Automaten]] zunutze um eine Zeichenkette zu [[Suchalgorithmen|durchsuchen]].

# Grundidee
Pattern "abcaab".
Alphabet: $\{ a,b,c,d,\dots \}$

Für den Idealfall wird wieder ein [[Endliche Automaten#Deterministischer endlicher Automat|DEA]] definiert.
![[Musterautomat_1.png]]
Angenommen im Zustand $z_{4}$ kommt nicht das gewünschte Zeichen $a$, kann im Zustand $z_{1}$ geschaut werden, ob das Zeichen einem $b$ entspricht.

Im Zustand $z_{4}$ hat schon den Anfang $abca$ des Patterns erkannt.
Im Fall $!a$ stellt sich die Frage, wie weit das Ende von $abca$ (von rechts) bereits wieder am Anfang des gesuchten Patterns sein kann. ([[Rand eines Wortes]])

Daher dass $z_{4}$ einen **Rand** von $a$ hat, kann wieder in $z_{1}$ weitergesucht werden:
![[Musterautomat_2.png]]
Steck hinter dem Zeichen $!a$ das Zeichen $b$ kann direkt in den Zustand $z_{2}$ weitergegangen werde und das nächste Zeichen der Zeichenkette wird verglichen.

Steckt hinter $!a$ aber auch $!b$ stellte sich wieder die Frage des **Rands**. Da $z_{1}$ keinen Rand besitzt, geht es in $z_{0}$ weiter. 

Steckt hinter dem Zeichen $!b$ das Zeichen $a$ kann man in den nächsten Zustand $z_{1}$ eintreten und mit dem nächsten Zeichen der Zeichenkette weiterfahren.

Ist hinter $!b$ auch $!a$ muss man in $z_{0}$ bleiben und mit dem nächsten Zeichen der Zeichenkette weiterfahren.

### Feststellungen
- Das Begutachten eines Zeichens der Zeichenkette kann mehrere Zustandsübergänge beinhalten. Im Schlimmsten fall, ist man am Schluss in $z_{0}$.
- Mit dem Musterautomaten lässt sich eine Zeichenkette **rein sequenziell** durchsuchen.
- Jeder Zustand besitzt nur 2 Zustandsübergänge.

### Ränder aller Teilworte
Für die Konstruktion sind die [[Rand eines Wortes|Ränder]] aller Teilworte des zu suchenden Patterns wichtig.

Beispiel: Pattern $abcaab$

| Teilwort | Zustand | Rand        | Länge | Folgezustand |
| -------- | ------- | ----------- | ----- | ------------ |
| a        | $z_{1}$ | $\emptyset$ | 0     | $z_{0}$      |
| ab       | $z_{2}$ | $\emptyset$ |       | $z_{0}$      |
| abc      | $z_{3}$ | $\emptyset$ |       | $z_{0}$      |
| abca     | $z_{4}$ | a           | 1     | $z_{1}$      |
| abcaa    | $z_{5}$ | a           | 1     | $z_{1}$      |
![[Musterautomat_3.png]]

## Musterautomat vs. optimierter Suchautomat
- Beides sind [[Endliche Automaten|endliche Automaten]] zum Suchen eines Patterns in einer Zeichenkette.
**Optimierter Suchautomat**
- Manuell (aufwändig) konstruiert für spezifische Pattern.
- Pro Zustand mehrere "Ausgänge" möglich.

**Musterautomat**
- Konstruiert mittels [[Rand eines Wortes|Ränder]] der Teilwörter
- Pro Zustand nur zwei "Ausgänge".
- Spezielle Abarbeitung: Ggf. mehrere Zustandsübergänge pro Zeichen.

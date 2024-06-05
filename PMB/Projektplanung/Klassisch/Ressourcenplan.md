Bei der Erstellung des Ressourcenplans werden die geeigneten Ressourcen (Personen) einen [[Projektstrukturplan#Arbeitspaket|Arbeitspaket]] zugewiesen.

**Input:**
- Arbeitspakete mit [[Aufwandschätzung|Aufwänden]] und [[Ablaufplan]].
- Verfügbarkeit der Fähigkeiten der Mitarbeiter.

Das Ziel des Ressourcenplans ist:
- Die Zuteilung geeigneter Ressourcen.
- Bestimmen der Dauer der Arbeitspakete.
- Verteilung der Arbeitspakete auf der Zeitlinie.

**Output:**
- Projektdauer
- Projektkosten

## Vorgehen
1. Festlegung der für die Arbeit nötigen Profile und Zuordnung der Arbeitspakete.
	- Arbeitspakete benötigen einen speziellen Skill
2. Sichtung den verfügbaren Mitarbeitern und deren Profile und die Zuordnung von Mitarbeitern zu den Arbeitspakten.
	- Passend Mitarbeiter auswählen.
3. Durch Zuweisen der Mitarbeiter und deren Verfügbarkeit ergibt sich die Dauer eines Arbeitspaketes.
4. Verteilung der Aufwände pro Arbeitspaket und Mitarbeiter auf die Zeitachse unter der Beachtung der Auslastung

### Dauer eines Arbeitspakets
Im Normalfall kann die Dauer mittels folgender Formel ermittelt werden:
$$
\text{Dauer [Tage]} = \frac{\text{Aufwand [Personentage]}}{\text{Persnalverfügbarkeit [Stellenprozent]}}
$$
Steht für ein Arbeitspaket nur eine begrenzte Zeit zur Verfügung:
$$
\text{Personalbedarf [Stellenprozent]} = \frac{\text{Aufwand [Personentage]}}{\text{(Dauer [Tage])}}
$$

## Kritischer Pfad
Als kritischer Pfad bezeichnet man im Projektplan die längste Kette von Arbeitspaketen und Meilensteine bei denen es kein Puffer gibt.

- Der kritische Pfad bestimmt die Mindestprojektdauer.
- Arbeitspakete und Meilensteine auf dem Pfad sind logisch voneinander abhängig.
- Die Elemente auf dem Pfad haben keine Reserve und müssen rechtzeitig fertig sein.
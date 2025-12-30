Modelle in der [[Operations Research|Entscheidungsfindung]] allgemein:
- Variablen
	- Alternative: Menge von Variablen
	- Konsequenzen: Ergenbis der Alternative
		- Extremierung (min, max)
		- Satisfizierung ($\leq,\geq,\leq\dots\leq,=$)

Beim Einsatz eines [[Beschreibendes Modell|beschreibendes Modell]] geschieht folgendes ausserhalb des Modells:
- **Beurteilung einer Alternative**
- **Erzeugung einer Alternative**
- **Auswahl der besten Alternative**

Mit einem Optimierungsmodell werden genau die oben geannten Punkte übernommen. Dafür wird jedoch ein Lösungsverfahren / Algorithmus (**Solver**) benötigt.

## Formulierung
>[!Definition]
>maximiere/minimiere $f_{1}(x,p)$ unter den Bedingungen
>$f_{2}(x,p) \leq d_{2}$
>$f_{m}(x,p) \leq d_{m}$


## Vorgehen zum erstellen des Modells
1. [[Einflussdiagramm]] erstellen.
2. [[Beschreibendes Modell]] aufstellen
3. Auszeichnen einer Konsequenz als Zielfunktion, welche zu minimieren / maximieren ist.
4. Aufstellen der entsprechenden Ungleichungen und Gelichungen.

## Typen von Optimierungsmodellen
**Mathematische Programmierung**
- [[Lineare Optimierungsmodelle|Lineare Programmierung]] / [[Nicht-Lineare Optimierungsmodelle|nicht-linear Programmierung]]
- [[Ganzzahlig Lineare Optimierungsmodelle|Ganzzahlige]] / gemischt ganzzahlige lineare Programmierung
=> Solver typischerweise basierend auf algebraischen / arithmetischen Konzepten

**Kombinatorische Optimierung**
- „Standard“-Modelle, im allg. in Graphen (Wege, Zyklen (Bsp. Handelsreisendenproblem), Bäume, Flüsse, Matching, usw.)
- Anwendungsspezifische Modelle (sehr zahlreich) und Optimierungsalgorithmen (Solver)

**[[Constraint Programming Modelle|Constraint Programming]]**
- Generischere Modellierkonstrukte (z.B. global constraints) als in der mathematischen Programmierung
- Deshalb meist kompakte, leserliche Modelle
- Solver typischerweise basierend auf arithmetischen und logischen Konzepte

## Eigenschaften guter Modelle
- Einfach
	- Einfach zu verstehen
	- Nur modellieren, was notwendig ist
	- Fördert das Verständnis des Problems
	- Dem Bestreben viele Details einzubeziehen ist zu wiederstehen
- Robustheit
	- Das Modell sollte nie abstruse Resultate liefern (z.B. unzulässige Alternativen)
- Einfache Steuerung
	- Die Experten sollten wissen, was für Inputdaten benötigt werden, um die gewünschten Resultate zu erhalten
- Aktualisierbarkeit
	- Es sollte einfach sein, die Parameter und die Struktur des Modells zu aktualisieren, wenn neue Informationen vorhanden sind
- Vollständigkeit im Kernbereich
	- Alle wichtige Phänomene sind modelliert, auch wenn ihr Einfluss subjektiv eingeschätzt werden muss
- Einfache Kommunikation
	- Das Modell sollte "benutzerfreundlich" sein Z.B.: die Inputdaten sollten einfach abgeändert werden können, und der Output sollte einfach zu verstehen sein
- (Zusätzlich) Handhabbares Modell
	- Es sollten effiziente Algorithmen zur Lösung des Modells bestehe
Ein Sortieralgorithmus ist ein [[Algorithmus]] welcher Datenelemente anhand von einer bestimmten Reihenfolge sortiert.
Sortieralgorithmen werden unterteilt in:
- [[Vergleichsbasierte Sortieralgorithmen]]
- [[Radix Sortieralgorithmen]]

Unsortierte Daten haben:
- Eine [[AD/Algorithmen/Komplexität]] der Suche von $O(n)$
- eine mühsamen und langsamen Zugriff.

Sortierte Daten bieten:
- Einen Zugriff **schnellen** Zugriff.
- [[Binäre Suche]].

## Totale Ordnung
Um Datenelemente sortieren zu können, muss eine **totale Ordnung** vorliegen.
Eine **totale Ordnung** (bzw. lineare Ordnung) liegt vor, wenn für **zwei beliebige** Datenelemente $x$ und $y$ gilt:
- $x$ ist **kleiner** $y$ ODER
- $x$ und $y$ sind **gleich** ODER
- $x$ ist **grösser** $y$.
$\implies$ Daten müssen sich vergleichen lassen.

Daten werden meistens anhand von einem Schlüssel verglichen, dies kann ein oder mehrere Attribute eines Objekts sein.

In Java implementieren Klassen typisch das [[compareTo & Comparable#compareTo ( Interface Comparable)|Interface Comparable]] für die natürliche Ordnung oder [[compareTo & Comparable#Comparator|Interface Comparator]] für eine spezielle Ordnung.

## Stabilität
Die Stabilität eines Sortieralgorithmus sagt aus, wie gleiche Elemente sortiert werden. Behalten die Elemente die Reihenfolge ist der Algorithmus stabil, wenn nicht wird er als instabil bezeichnet

### Beispiel
Daten: \[D1, D5_1, D3, D5_2, D2, D4]

Stabil sortiert:
\[D1, D2, D3, D4, D5_1, D5_2]

Instabil sortiert:
\[D1, D2, D3, D4, D5_2, D5_1]


## Inter vs. Extern
Beim **internen** Sortieren:
- liegen die Daten im **Arbeitsspeicher** vor.
- **Direktes Vergleichen** der Daten möglich.
- Primär von Bedeutung

Beim **externen** Sortieren:
- Daten liegen auf externen Massenspeicher.
- **NUR** Lesen und Schreiben möglich, kein direktes Vergleichen.
- Intern Speicher ist für alle Daten zu klein.

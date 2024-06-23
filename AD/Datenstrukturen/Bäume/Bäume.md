---
aliases:
  - Baum
---


Ein Baum ist eine [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]] welche aus Knoten und Kanten besteht. Dabei ist der Wurzelkonten der zentrale Einstiegspunkt und von dort aus wird weiter navigiert.

**Beispiel Unix-Dateisystem**
![[FileTree.png]]
## Verwendung
1. Daten haben bereits eine inhärente hierarchische Struktur, welche man entsprechend abbilden will. Beispiele:
	- Dateisystem mit Verzeichnissen und Dateien
	- Stammbaum
	- Vererbungshierarchie in Java
2. Explizite Anordnung und Einordnung von Daten in eine Baumstruktur um gewisse Ziele zu erreichen:
	- Schnelle Suche in einem geordneten Baum


## Grundelemente
Ein Baum besteht aus Knoten und Kanten.
![[TreeElements.png]]
### Modellierung
- Ein Baum ist eine [[Rekursion|rekursive]] Datenstruktur, die Knoten weisen auf wiederum andere Knoten.
- Enthält keine geschlossenen Pfade, und bildet somit eine Monohierarchie. Jedem Knoten ist **genau ein einziger Vrogängerknoten** zugeordnet.
- Objektorientierte Modellierung eines Baumes, wobie die Kardinalität der **child**-Beziehung von der Ordnung des Baumes abhängt.
![[TreeUML.png]]
## Richtung der Bäume
Ein ungerichteter Baum ist eine reine Hierarchie.
- **Out**-Tree, Navigation von der Wurzel **nach unten** zu den Blättern. (Kanten (Pfeile) gehen von der Wurzel aus)
- **In**-Tree, Navigation von den Blättern nach oben zur Wurzel

## Kenngrössen
- [[Ordnung eines Baumes|Ordnung]]
- [[Grad eines Knoten|Grad der Knoten]]
- [[Pfad]]
- [[Baum Niveaus]]
- [[Höhe eines Baumes|Höhe]]
- [[Gewicht eines Baumes|Gewicht]]
-  [[Füllgrad eines Baumes|Füllgrad]]

## Spezialformen von Bäumen:
- **Binär**-Baum, einfach und häufig.
- **AVL**-Baum, höhlen-balancierter Binär-Baum.
- **B**-Baum balancierter Baum, **nicht** zwingend binär
- **B** * -Baum  restriktivere Form des B-Baums (ebenfalls balanciert)
- **Binomial**-Baum speziell strukturierter Baum
- etc.
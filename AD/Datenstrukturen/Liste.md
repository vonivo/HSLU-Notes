Eine Liste ist eine [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]] welche Elemente hintereinander speichert.

**Einfach verkette Liste:**
![[LinkedList.png]]
Jedes Element besitzt eine Referenz auf das vorherige Element, sprich jedes Element kennt seinen direkten Nachfolger.

**Doppelt verkette Liste:**
![[DoubleLinkedList.png]]Jedes Element besitzt eine Referenz auf das vorherige und das nachfolgende Element.


## Modellierung
Listen werden typischerweise mit zwei verschiedenen Klassen modelliert.
Die erste Klasse repräsentiert dabei die Liste selbst.
Sie enthält:
- Referenz auf das erste (und letzte) Element (**head und tail**).
- Hilfsattribute (z.B. size)
- Methoden für die verschiedenen Attribute,

Die zweite Klasse repräsentiert ein Element in der Liste und ist somit ein Behälter der einzelnen Datenpunkte. Meistens werden diese Klasse **Knoten** oder **Node** benannt.
Sie ist nicht öffentlich zugänglich und enthaltet:
- Eine/Zwei Referenzen zu Vorgänger und Nachfolger
- Enthält Attribut(e) für die effektiven Daten.

**Einfache Verkettung**
![[List_uml.png]]
**Doppelte Verkettung**
![[DoubleLinkedList_uml.png]]
## Eigenschaften
- **Dynamisch**: Grösse der Datenstruktur passt sich der Anzahl Elemente an.
- **Explizit**: Die Elemente habe explizite Beziehungen zueinander über Referenzen.
- **Indirekt:** Der Zugriff erfolgt indirekt über ein sequenzielles Vorgehen (Von vorne oder von Hinte).
- **Geordnet:** Die Reihenfolge der Elemente bleibt bestehen.



## Suchen
Da kein direkter Zugriff besteht, beträgt die [[Komplexität|Zeitkomplexität]] der Suche eines Elementes $O(n)$ da immer durch die Liste iteriert werden muss. Dies ist dabei **unabhängig,** ob die Liste **sortiert oder unsortiert** ist.

Durch ein Hilfskonstrukt der **Skiplist** kann jedoch auch eine Laufzeit von $O(\log n)$ erreicht werden.

## Ergänzen eines Elements
**Einfach verkette Liste**
Das Element wird immer an erster Stelle hinzugefügt.
Das neue Element wird neu den **Head** der Liste und wird mit dem **alten Head** verkettet:
![[LinkedListe_Add.png]]
**Komplexität:** $O(1)$

**Doppelt verkettet Liste**
Durch die doppelte Verkettung kann auch am Ende der Liste ein Element mit der Komplexität von $O(1)$ ein Element hinzugefügt werden.



## Einfügen eines Elements
Wenn ein Element an einer spezifischen Stelle eingefügt werden soll, muss zuerst die Stelle gesucht werden ($O(n)$) und dann dort eingefügt werden ($O(1)$). Das Verschieben der Daten (wie beim [[Array]]) fällt weg, da die Beziehung explizit ist.
![[LinkedList_insert.png]]**Komplexität:** $O(n) + O(1) \implies O(n)$

## Entfernen
Um das zu entfernende Element zu finden, muss dies mit $O(n)$ gesucht werden und dann mit $O(1)$ entfernt werden.
![[LinkedList_remove.png]]
**Komplexität:** $O(n) + O(1) \implies O(n)$

## Bilanz
**Vorteile**
- Dynamisch, können eine beliebige Anzahl von Elementen aufnehmen und belegen keinen festen Platz (Wachsen und Schrumpfen mit den Daten).
- Gut geeignet für sehr grosse, stark variierende Daten
- Aufwand für das Reine Einfüge ist konstant
- Sind bei Java als Objekte implementiert und unterstützen Generics.
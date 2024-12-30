Bei der vereinfachten MC-Notation werden, falls möglich Beziehungsmengen weggelassen. Diese werden durch eine **Beziehungsbezeichnung** und **Leserichtung** ersetzt.
![[Pasted image 20241230142014.png]]
Ebenfalls entfallen die Attribute der Entitäten.

## Regeln
- Kardinalität wird mit "1-m-c" angegeben.
- Die Beziehungstypen entfallen. An ihrere Stelle treten die Bezeichnung und die Leserichtung.
- Falls eine Beziehung selbst Attribute hat, muss dafür eine neue Entitätsmenge modeliert werden.
- Die Definition der Entitätsmengen und deren Attribute wird in einem spearaten Dokument erstellt. Bsp:
![[Pasted image 20241230142251.png]]

## Elemente
- Entitätsmenge:![[Pasted image 20241230142321.png]]
- Beziehung:![[Pasted image 20241230142330.png]]
- Bezeichnung für Beziehung (inkl. Leserichtung)![[Pasted image 20241230142347.png]]
- Kardinalität: ![[Pasted image 20241230142357.png]]


## Empfehlungen
- Entitätsmengen im Singular bennen.
- Beziehungen mit Verben bennnen.
- Die zweite Leserichtung kann weggelassen werden (Passivform der ersten Richtung).

## Generalisierung
**Spezialisierung**
Die Spezialisierung ist die klassische **IS-A**-Beziehung. Kennzeichnend ist die **Vererbung der Eigenschaften**.

-> Die Spezialisierung wird mit einem Rechteck in einem weiteren Rechteck visualisiert.
![[Pasted image 20241230142745.png]]

**Generalisierung**
Bei der Generalisierung wird in dem Sinne verallgemeinert, dass der Generalisierende-Entity-Typ durch die Vereinigungsmenge der Instanzen mehrere Entity-Typen gebildet wird.


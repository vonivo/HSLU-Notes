Use Cases (Anwendungsfälle), Use Case Diagramme und Use Case Beschreibungen:
- Schaffen eine Kommunikationsgrundalge für Kundenanfroderungen.
- Halten die funktionalen Dienstleistungen eiens Systems fest.
- Use Case Beschreibungen repräsentieren eine Sequenz von Transaktionen innerhalb eines Systems.
- Jeder Use Case für einen einzelnen Aktor einen identifizierbaren Nutzen.

## Elemente
### Aktor
- Aktoren interagieren mit dem System und nehmen dabei eine spezifische Rolle ein. (Benutzer oder Drittsystem)
- Aktoren werdend durch Assoziationen mit Use Cases verbunden.
- Jeder Aktor muss mindestens einem Anwendungsfall assoziiert sein.

![[Pasted image 20250101152316.png]]
#### Generalisierung
Eine Generalisierung der Aktoren liegt vor, wenn zwei verschiedene Aktoren A und B über gleiche Eigenschaften verfügen, also die gleiche Rolle C einnehmen können.

- gleiche Eigenschaften werden in einem Aktor C modelliert.
- Die Aktoren A und B können mindestens die Rollen des Aktor C übernehmen.

Häufig werden Recht von Aktoren über Generalisierung spezifiziert.
![[Pasted image 20250101152605.png]]

Gibt es von einem Aktor keine Instanz, kann dieser mit **{{abstract}}** markiert werden.

### Assoziation
Die Assoziation verbindet Use Cases und Aktore. Sie ist binär und kann Multiplizitäten enthalten.

Wenn zwei Aktoren über eine Assoziation mit einem Use Case verbunden sind, werden bei Akteure benötigt. (**UND**-Verknüpfung)

### System
System oder Systemgrenzen:
- Der Systemumfang wird im Use Case Diagramm mit einem Kasten umrahmt **und Beschriftet**
- Die Systemgrenzen im Use Case Diagramm ist identisch mit der Systemgrenze im [[Kontext-Diagramm]]
![[Pasted image 20250101152937.png]]

### Use Case
- Use Case repräsentieren eine **Funktion oder Aktion**, die von einem System ausgeführt werden kann.
- Beschreibt ein Ziel
- Der Name besteht mindesten aus eine **Substantiv** und einem **Verb**
![[Pasted image 20250101153100.png]]

#### Generalisierung
- B erbt das Verhalten von A und kann dieses überschreiben oder ergänzen.
- B erbt alle Beziehungen
- B benötigt A
- B entscheidet, was von A ausgeführt wird.
- Abstrakte Modellierung möglich **{abstract}**
![[Pasted image 20250101153228.png]]
#### Include
Ein Use Case kann einen anderen Use-Case aufrufen wie ein Funktionsaufruf.
![[Pasted image 20250101153308.png]]

#### Extend
- Zeigt an, dass das Verhalten eines Use Case a durch einen anderen Use Case B erweitert werden kann, aber nicht muss.
- Die Ausfürhung von UseCase B ist von einer Bedingung abhängig.
- Die Extensionpoints sowie die Bedinung muss modeliert werden.
![[Pasted image 20250101154512.png]]

## Use Case Beschreibung
![[Pasted image 20250101154614.png]]
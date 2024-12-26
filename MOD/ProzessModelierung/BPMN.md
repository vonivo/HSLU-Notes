BPMN Business-Process-Modeling-Notation ist die Notationsart um einen [[Prozess]] standardisiert zu visualisieren.

## Elementen
### Grundelemente
#### Prozess
Ein Prozess wird mittels eines Rechteckes dargestellt.
![[Pasted image 20241226134907.png]]
#### Ereignis
Ein Ereignis stell dar, das etwas passiert. In jedem BPMN gibt es ein **Start**- und mindestens ein **Endereignis**.
![[Pasted image 20241226135019.png]]
#### Sequenzfluss
Der Sequenzfluss beschreibt die zeitlich-logische Reihenfolge, in der die Flusselemente zueinander stehen.
![[Pasted image 20241226135129.png]]
### Gateways
Gateways stehen für Entscheidungen in einem Diagramm, es ist jedoch **keine Aufgabe**.
Es gibt meistens **ein Öffnendes Gateway** und **ein Schliessendes Gateway**.
#### Exklusives Gateway
Das exklusive Gateway beschreibt eine Verzweigung, bei der nur ein Pfad weiter verfolgt wird.
Jeder Sequenzfluss wird dabei beschriftet.
![[Pasted image 20241226135623.png]]
Müssen die verschiedenen Flüsse wieder zusammengeführt werden benutzt man das schliessende Gateway.
![[Pasted image 20241226135726.png]]
Es kann entweder mit oder ohne **X** gezeichnet werden.
![[Pasted image 20241226135756.png]]
#### Paralleles Gateway
Das Parallele Gateway zeigt an, das zwei Sequenzflüsse parallel abgearbeitet werden. Wenn diese beiden Flüsse wieder zusammengeführt werden, muss auch wieder ein paralleles Gateway benutzt werden.
**Das schliessende Gateway synchronisiert den Sequenzfluss**, dass heisst es geht erst weiter, wenn alle Token aller Sequenzflüsse bei diesem Gateway sind.
![[Pasted image 20241226140106.png]]
#### OR-Gateway
Mit dem OR-Gateway kann eine Und-Oder-Situtation beschrieben werden. Bei der entweder **ein**, **mehrere** oder **alle** Sequenzflüsse durchlaufen werden.
Auch hier ist das schliessende Gateway (falls existent) synchronisierend.
![[Pasted image 20241226140401.png]]
#### Standardfluss
Der Standardfluss kann mittels eines Strichs durch den Sequenzpfeil gekennzeichnet werden. Er wird ausgeführt, wenn kein anderer Pfad zutrifft.
![[Pasted image 20241226140519.png]]
### Pools und Lanes
#### Lane
Eine Lane gibt an, **wer** für die Aufgaben innerhalb dieser Lane verantwortlich ist.
Dabei sollte **keine Zuordnung zu Personen** gemacht werden, sondern zu Teams/Abteilung/System/....

Ein Flussobjekt darf **immer nur in einer Lane sein**.
![[Pasted image 20241226140811.png]]
#### Pool
Mehrere Lanes werden nach Verantwortlichkeit in Pools zusammengefasst.
Dabei steht ein Pool für die **übergeordnete Instanz** mehrerer Lanes.
![[Pasted image 20241226140931.png]]
### Daten
Daten repräsentieren alle möglichen Informationen.

**Datenobjekte** werden über **Assoziation mit Flussobjekten** in Verbindung gebracht.
-> Dabei ist die Assoziationsrichtung entscheiden.

Zeigt die Assoziation von einem Prozess-Schritt zum Datenobjekt, heisst das, dass die Daten durch diesen Schritt erstellt wurden.
![[Pasted image 20241226141513.png]]
Umgekehrt bedeutet das, dass der Schritt die Daten benötigt.

Wird der Assoziationlinie (**ohne Pfeil**) dem Sequenzfluss angehängt, heisst das, dass die Daten vom ersten Prozess-Schritt erstellt werden und von nächsten direkt wieder verwendet werden.
![[Pasted image 20241226141706.png]]

### Teil- und Hauptprozesse
#### Teilprozesse 
Teilprozesse beschreiben einen detaillierten Ablauf (sind selbst ein BPMN) und werden im Oberprozess als einzelne Aufgabe dargestellt.
Jeder Teilprozess ist ein Gültiges BPMN

Der Teilprozess (wie Funktionsaufruf) wird durch ein **Kästchen mit einem Plus** dargestellt:

In Teilprozessdiagramm wird ein Kästchen mit einem Minus verwendet um zu Signalisieren, dass es sich um einen Teilprozess handelt.
![[Pasted image 20241226141921.png]]
#### Hauptprozess
Wird in einem BPMN ein Hauptprozess angestossen, welcher nicht selbst zum Prozess gehört wird, dies wie ein Teilprozess dargestellt, nur die **Aufgabenbeschreibung** wird in **Grossbuchstaben** geschrieben.
![[Pasted image 20241226142108.png]]
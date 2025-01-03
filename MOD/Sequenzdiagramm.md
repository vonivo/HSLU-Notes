Sequenzdiagramme dienen zur Beschreibung der Laufzeitsicht eines Systems.
![[Pasted image 20250103133323.png]]

## Elemente
### Diagrammrahmen
Der Rahmen wird als Rechteck um das Diagramm gezeichnet. Die Beschriftung wird in der oberen linken Ecke vorgenommen.
![[Pasted image 20250103133531.png]]

### Akteur
Der Akteur ist der Auslöser einer Sequenz und wird als Strichmännchen modelliert.
Der Akteur besitzt eine Lebenslinie, welche senkrecht als gestrichelte Line modelliert wird.
![[Pasted image 20250103133652.png]]

### Objekt
Wie im [[Objektdiagram]] wird hier das Objekt mit "Bezeichner:Klasse" modelliert. 
Auch Objekte besitzen eine Lebenslinie.
![[Pasted image 20250103133849.png]]
**Aktives Objekt**
Ein aktives Objekt ist ein Objekt mit eigenem Kontrollfluss. Das heisst das Objekt ist z.B. ein Thread in einem nebenläufigen Kontrollfluss:
![[Pasted image 20250103133857.png]]
### Nachrichten
#### Nachricht
Der Sender wartet bis zur Beendigung der Interktion.
Die Nachricht ist ein Methoden-Aufruf, welcher auf dem Pfeil modeliert wird.
Die **Pfeilspitze** ist **ausgefüllt**.

Die Antwort wird als gestrichelter Pfeil modelliert und ist optional.
Auf dem Antowortpfeil wird der Retunrwert der Nachricht in einer Variabel zugewiesen.

![[Pasted image 20250103134044.png]]

#### Asynchrone Kommunikation
Die Nachricht wird als Signal betrachtet.
Der Sender wartet nicht auf das Ende der Interaktion.
![[Pasted image 20250103134215.png]]
### Ausführungsspezifikation
Die Ausführungsspezifikation oder Aktivierung zeigt an, welches Objekt gerade aktiv eine Methode ausführt. Sie wird mittels eines Balkens über der Lebenslinie modelliert.
![[Pasted image 20250103134330.png]]
Ein Selbstaufruf wird durch eine Nachricht und einen überlappenden Aktivierungsbalken dargestellt:
![[Pasted image 20250103134402.png]]

### Objekte erstellen
Objekte können auch während einer Sequenz erstellt werden dafür sind zwei Schritte notwendig:
1. "Create-Pfeil" -> Ein gestrichelter Pfeil, welcher das Objekt erstellt.
2. Nachricht für den Konstruktoraufruf des Objekts.
![[Pasted image 20250103134539.png]]

### Löschsymbol
Ein Objekt kann auch durch eine "destroy"-Nachricht und ein "X" auf der Lebenslinie gelöscht werden:
![[Pasted image 20250103134701.png]]

### Kombinierte Fragmente
Kombinierte Fragmente dienen zur Modellierung von komplexen Strukturen:
![[Pasted image 20250103134741.png]]
#### Option
Optionaler Ablauf, welcher nur ausgeführt wird, wenn die Bedingung erfüllt ist:
![[Pasted image 20250103134821.png]]

#### Alternativer Ablauf
Ein Ablauf welcher eine Entweder-Oder-Verzweigung modelliert.
- Darstellung von mind. 2 Alternativen.
- XOR
- Auswahl anhand der Bedingung
![[Pasted image 20250103134939.png]]
#### Schleife
Ein sich wiederholdender Ablauf welcher eine Schleife modelliert.
- Ausführungswahrscheinlichkeit wird durch Zähler mit **Min**- und **Max** dargestellt.
- Überwachungsbedingung optional. Nur wenn die **Mindestdurchlaufzahl** **überschritten** ist und die Überwachungsbedingung **true** ist, wird der Loop fortgesetzt. 
![[Pasted image 20250103135506.png]]

#### Break
Ein Break wird verwendet, um einen Ausnahmezustand zu handeln. Wenn ein Break ausgefürht wird, wird die Sequenz **immer** beendent.

- Wenn Überwachungsbedingung **true** ist, wird der Break ausgeführt.
![[Pasted image 20250103135731.png]]
>[!info]
>Ein Automat oder Statemachine ist eine Menge an **Zuständen**, welche mittels **Übergängen** in Verbindung stehen und durch **Ein**-/**Ausgaben** getriggerd werden.

In der Informatik werden Automaten an vielen Ort verwendet:
- Compilerbau
- Such nach Pattern in einem String
- Kommunikationsprotokolle
- etc.

## Grundlagen
### Zustände
Ein Automat besitzt eine Menge an **Zuständen Z**. Dabei muss der **Startzustand explizit gekennzeichnet** werden.

### Eingaben
Ein Automat besitzt Eingaben, welche dann die spezifischen Zustandsübergänge auslösen.
Eingaben kann eine Folge von Zeichen, Symbolen, Ereignissen, etc. sein.

### Ausgaben
Ein Automat kann auch Ausgaben hervorrufen, dies sind in der Regel Zeichen oder Symbole.

## Typen von Automaten
### Allgemeiner Automat
(Z, E) -> Z
Der Automat bewirkt keine Ausgaben.

### Mealy-Automat
(Z,E) -> Z, (Z,E) -> A
Beim Mealy-Automat bewirkt ein Zustandsübergang immer auch eine Ausgabe.

### Moore-Automat
(Z,E) -> Z, Z -> A
Beim Moore-Automat bewirkt ein Zustand direkt eine Ausgabe.



## Darstellung
Ein Automat kann mit verschiedenen Mitteln dargestellt werden:
- als [[AD/Algorithmen/Graphen/Graph]],
![[Statemachine_Graph.png]]
- als Tabelle.
![[Statemachine_table.png]]


## Umsetzung
Ein Automat kann in Java mit verschiedenen Ansätzen umgesetzt werden.
Mit Software kann das sein:
- strukturiert (mittels Switches)
- objektorientiert (State-Patern)

In Hardware:
- Flipflops
- Speicherelemente
- programmierbare Logikbausteine


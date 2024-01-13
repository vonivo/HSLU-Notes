- Operatoren (+, -, * , /, =) haben je nach [[Datentyp]] eine andere Funktion (polymorph)
	-  Beispiel mit **+** werden Zahlen addiert aber Zeichenketten konkateniert

- = wird für die Zuweisung verwendet
- Um auf Gleichheit zu prüfen nutzt man ==

# Logische Operatoren
Logische Operatoren werden oft bei Bedingungen zu [[Selektion|Selektionen]] verwendet.

| Zeichen | Bedeutung |
| ---- | ---- |
| < | kleiner als |
| <= | kleiner oder gleich asl |
| == | gleich (identisch) |
| != | ungleich |
| >  | grösser als |
| >= | grösser oder gleich als |
**== sollte nur elementare Datentype verwendet werden bei Objekten verwendet man die [[Equals & Hashcode|equals]] [[Methode]]** 
## Verknüpfungen
Bedingungen können verknüpft werden mit folgenden Operatoren
- Java ist soweit optimiert das die Bedingungen nicht weiter ausgewertet werden wenn nach der ersten Bedingung das Ergebnis schon klar ist
	- Beispiel: wenn `a = 1`  und die Bedingung ist `(a == 2 && a == 1)` wird breits nach der ersten Bedingung abgebrochen, da die gesamte Bedingung nie wahr sein kann.

| Op | Funktion | Kurzbeschreibung |
| ---- | ---- | ---- |
| && | UND (AND) | Beide Argumente müssen *true* sein |
| \|\| | ODER (OR) | Mindestens eines der Argumente muss *true* sein |
| ^ | Exklusiv-ODER (XOR) | Nur genau eines der Argumente darf *true* sein  |
| ! | Negation (NOT) | Negiert das Argument |
### AND
| 1. Argument (a) | 2. Argument (b) | Resultat (a && b) |
| ---- | ---- | ---- |
| $\color{red}false$ | $\color{red}false$ | $\color{red}false$ |
| $\color{red}false$ | $\color{green}true$ | $\color{red}false$ |
| $\color{green}true$ | $\color{red}false$ | $\color{red}false$ |
| $\color{green}true$ | $\color{green}true$ | $\color{green}true$ |
- Der Operator ist **optimiert**: Wenn das erste Argument **false** ist, wird das **zweite** nicht mehr ausgewertet.

### OR
| 1. Argument (a) | 2. Argument (b) | Resultat (a \|\| b) |
| ---- | ---- | ---- |
| $\color{red}false$ | $\color{red}false$ | $\color{red}false$ |
| $\color{red}false$ | $\color{green}true$ | $\color{green}true$ |
| $\color{green}true$ | $\color{red}false$ | $\color{green}true$ |
| $\color{green}true$ | $\color{green}true$ | $\color{green}true$ |
- Der Operator ist **optimiert**: Wenn das erste Argument **true** ist, wird das **zweite** nicht mehr ausgewertet.

### Exclusiv OR
| 1. Argument (a) | 2. Argument (b) | Resultat (a \|\| b) |
| ---- | ---- | ---- |
| $\color{red}false$ | $\color{red}false$ | $\color{red}false$ |
| $\color{red}false$ | $\color{green}true$ | $\color{green}true$ |
| $\color{green}true$ | $\color{red}false$ | $\color{green}true$ |
| $\color{green}true$ | $\color{green}true$ | $\color{red}false$ |
### NOT
| 1. Argument (a) | Resultat (!a) |
| ---- | ---- |
| $\color{red}flase$ | $\color{green}true$ |
| $\color{green}true$ | $\color{red}false$ |


### Gesetz von De Morgan
Das Gesetz von De Morgan besagt folgendes:

> Eine AND-Operation lässt sich durch eine OR-Operation (und umgekehrt!) ersetzen, wenn man  gleichzeitig sowohl die einzelnen Argumente als auch das Resultat negiert

#### Beispiel:
`!(a && b) == !a || !b `
`!(a || b) == !a && !b `
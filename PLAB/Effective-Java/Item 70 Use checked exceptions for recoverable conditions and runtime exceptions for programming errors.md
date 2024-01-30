
## Checked Exceptions
Werden verwendet bei, Ausnahmezuständen wo der Client sich erholen kann.
Dies wird mittels des [[Exceptionhandling]] gemacht.

Dank den [[Exceptionhandling#Arten von Fehlern|Checked Exceptions]] muss sich der Programmierer um den Fehler kümmern.

## Unchecked Exceptions
[[Exceptionhandling#Arten von Fehlern|Unchecked Exceptions]] sollten bei Programmierfehlern verwendet werden. Ein Grossteil dieser Fehler entstehen, wenn gewisse Voraussetzungen nicht erfüllt werden. Zum Beispiel, wenn der `index` eines `arrays` nicht zwischen `0` und `array.size()` ist.

Teilweise kann ist es nicht genau klar, ob der Client sich erholen kann oder nicht, da muss der Programmierer entscheiden, welche [[Exceptionhandling#Arten von Fehlern|Exception]] er wirft.

Eine [[Exceptionhandling#Arten von Fehlern|Unchecked Exceptions]] stoppt den aktiven Thread und der Stacktrace wird ausgegeben.

## Errors
Errors sollten nur von der JVM selbst geworfen werden und daher nie von spezialisiert werden.
Sie repräsentieren eine Resourcendefizit.
>[!Definition]
>**Code-Coverage** ist eine Metrik die angibt, welche Code-Zeile zur Laufzeit ausgeführt wurde.
>
>Code-Coverage-Messungen werden typischerweise während der Ausführung von Testsfällen ausgeführt ([[Unit Tests]], [[Integrationtests mit JUnit|Integrationtests]], etc.).

Mithilfe von Code-Coverage zeigt, wie umfassend der Code tatsächlich getestet, genutzt wurde.

>[!warning]
>Eine hohe Coverage ist **kein** Beweis für gute Testfälle oder Fehlerfreiheit des Codes.


## Arten
- **Statement Coverage**(Line Coverage):
	- Misst ob (und wie oft) eine Code-Zeile durchlaufen wurde.
	- Bei logischem Vergleich/Ausdruck nicht repräsentativ.
- **Branch Coverage**
	- Prüft, welche Zweige einer bedingten Anweisung ausgeführt wurde.
- **Deciscion Coverage**
	- Bei Fallunterscheidung (`if`, `while`, etc.) wird geprüft, dass alle Teilausdrücke in der Bedingung auf `true` und `false` aufgelöst wurde.
- **Function Coverage**
	- Misst auf Basis der Funktionen, ob sie aufgerufen wurde.
- **Race Coverage**
	- Konzentriert sich auf Codestellen die parallel ablaufen.
- **Path Coverage**
	- Wird gemessen, ob alle möglichen Kombinationen von Programmablaufpfäden durchlaufen wurde.
	- Exponentieller Anstieg der Möglichkeiten -> in der Praxis nicht durchführbar.


## Technische Umsetzung
Gemessen wird die Abdeckung bei der Ausführung des Codes durch den modifizierten Code selbst. Messdaten werden typisch in eine spezifische Datei persistiert.

Die Code-Coverage-Messung ist ein [[Build-Werkzeug]] und der [[Buildserver]] visualisiert / wertet die Cover-Messung nur aus.

**Beispiele**
- JaCoCo
### Instrumtierung des Quellcodes
Der Quellcode wird durch einen Preporcessor vor dem Compilieren mit Statements für die Coverage-Messung ergänzt.

**Nachteil**
Modifizierter Quellcode (nicht reproduzierbar)

### Instrumentiereung des Bytecodes
Der Bytecode wird bei/nach Kompilierung mit Bytecode zur Coverage-Messung ergänzt.

**Nachteil**
Verschiedene `.class`-Dateien. Müssen separat verwaltet und gemanaged werden.


### Instrumentierung zur Laufzeit
Der Bytecode wird zur Laufzeit durch den JIT Instrumentiert.

**Vorteil**
Nur ein Binary, unabhängig von Compiler, jederzeit und überall ad-hoc aktivierbar.

**Nachteil**
Teilweise Concurrent bei Bytecodemanipulation
Die VM-Sprache unterscheidt in zwei Verzweigungsbefehle:
- **Unbedingte Verzweigung**: mit dem `goto symbol`-Befehl -> Springe zum Befehl nach dem `label symbol`
- **Bedingte Verzweigungen**: `if-goto symbol` Befehl -> Hole den obersten Stackwert, wenn dieser nicht false ist, springe zur Ausfürhugn des Befehls nach `symbol label`.

**Beispeil**
`if (n < 100) goto LOOP`
-> `push n, push 100, lt, if-goto LOOP`

**while-Beispiel**
```java
int mult(int x, int y) {
	int sum = 0;
	int i = 0;
	while ( i < y) {
		sum += x;
		i++;
	}
	return sum;
}
```
wird zu:
 ```
 function mult(x,y)
 push 0
 pop sum
 push 0
 pop i
 label WHILE_LOOP
	 push i
	 push y
	 lt
	 not
	 if-goto WHILE_END
	 push sum
	 push x
	 add
	 pop sum
	 push i
	 push 1
	 add
	 pop i
	 goto WHILE_LOOP
 label WHILE_END
 push sum
 return
 ```

### Befehle
- `label labelName`: Beschriftet die aktuelle Stelle im Code der Funktion. 
	- Nur markierte Stellen können angesprungen werden. 
	- Geltungsbereich ist die Funktion in welcher es definiert ist.
	- Zeichenfolge aus Buchstaben, Ziffer, Unterstrichich, Punkte und Doppelpunkt. 
	- Beginnt mit einer Ziffer
- `goto labelName`: Bewirkt einen unbedingten Sprung. Die Ausführung wird an der durch das Label markierte Stelle weitergeführt.
	- `goto`-Befehl und das Label müssen im selben Scope sein.
- `if-goto labelName`: Bewirkt einen bedingten Sprung
	- Oberste Wert des Stacks wird gepoppt; wenn der Wert nicht 0 ist, wird die Ausfürhung an der durch das Label markierte Stelle weitergeführt.
	- `if-goto`-Befehl und das Label müssen im selben Scope sein.

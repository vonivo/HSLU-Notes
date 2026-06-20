
**Bootstrapping**
Der Prozess des Ladens der Basissoftware in den Speicher des Computers nach dem Einschalten oder Zurücksetzen.

**HW-Vertrag**
Wenn der Computer zurückgesetzt wird, beginnt die Ausführung mit dem Befehl `ROM[0]`

**VM-Vertrag**
Der folgende Code sollte am Anfang des ROMs, beginnend in `ROM[0]`, platziert werden:
```
sp=256
call Sys.init
```

**Jack-Vertrag**
Die Programmausführung beginnt mit der Funktion `Main.main()`

**OS-Vertrag**
`Sys.init` soll das Betriebssystem initialisieren und dann `Main.main` aufrufen.

**API**
```java
function void init();
function void halt();
function void wait(int duration); // in ms
function void error(int errorCode)  // Print error to screen and halts
```

## Implementation
```java
class Sys {
	function void init() {
		do Math.init();
		do Memory.init();
		do Screen.init();
		...
		do Main.main();
	}
}
```

- Für `halt` eine Endlosschleife verwenden.
- Für `wait` eine HW-spezifische Schleife verwenden
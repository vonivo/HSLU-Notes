Eine Race Condition ist ein Verhalten wenn zwei [[Thread|Threads]] gegenseitig um eine Resource konkurrieren.

## Beispiel
Es existiert eine Counter-Klasse:
```java
class SimpleCounter {
	private int count = 0;

	public int increment() {
		count++;
		return count;
	}
}
```

Nun startet der Main-Thread zwei Threads `T1`und `T2`.
Annahme `T1` und `T2` laufen auf einem Prozessorkern.

![[RaceCondition.png]]
Wie man sieht, ist die Ausgabe nicht wie erwartete 1,2,3,4,5,6...

Die Methode `increment` ist ein kritischer Abschnitt.
Wenn sich mehere Threads gleichzeitig in diesem Abschnitt befinden, wird der Zählerstand `count` gegenseitig überschrieben und es entsteht eine Inkonsistenz.

Das exakte Verhalte des Schedulers ist nicht deterministisch vorhersagbar und somit ist das Endresultat des Counters immer zufällig.

Die Lösung dafür ist der [[Gegenseitiger Ausschluss|gegenseitige Ausschluss]].


### Mit gegenseitigem Auschluss
![[FixedRaceCondition.png]]
- `T1` und `T2` können immer noch durch Taskwechsel unterbrochen werden.
- Im kritischen Abschnitt befindet sich aber **nur ein Thread**.
[[Exceptionhandling#Arten von Fehlern|Checked Exceptions]] zwingen den Programmierer sich um einen Fehler zu kümmern, was an sich die Zuverlässigkeit des Programmes erhöht.
Wenn aber [[Exceptionhandling#Arten von Fehlern|Checked Exceptions]] **überstrapaziert** werden, macht es die **API weniger benutzerfreundlich.** (Auch weil seit Java 8 solche [[Methode|Methoden]] nicht direkt in [[Streams]] aufgerufen werden können.)


Um herauszufinden, ob es eine [[Exceptionhandling#Arten von Fehlern|Checked Exceptions]] benötigt, sollte sich der Programmierer immer fragen, wie würde ich die [[Exceptionhandling|Exception handeln]].

Falls eine [[Methode]] nur **genau eine [[Exceptionhandling#Arten von Fehlern|Checked Exceptions]]** wirft, sollte man sich fragen, ob man diese umgehen kann. Denn "nur" dank dieser [[Methode]] muss ein [[Exceptionhandling]] gemacht werden und die [[Methode]] kann nicht in [[Streams]] verwendet werden.

## Arten um Checked Exceptions zu umgehen
1. Es kann ein `Optional<T>` verwendet werden
	Hat jedoch den Nachteil, dass keine zusätzlichen Informationen weitergegeben werden können
2. Aufteilen in eine [[Methode]] welche ein `boolean` zurück gibt (Zeigt an ob es eine Exception gegeben hätte) und in eine [[Methode]] welche eine `RuntimeException` wirft.
```java
if (obj.actionPermitted(args)) {
    obj.action(args);
} else {
    ... // Handle exceptional condition
}
```
Achtung bei Multithreading (Zustand kann sich zwischen `if` und `action` ändern.)
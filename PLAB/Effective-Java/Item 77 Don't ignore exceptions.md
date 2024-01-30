Wenn schon eine [[Exceptionhandling#Arten von Fehlern|checked Excpetion]] geworfen wird, versucht diese dem Programmierer auch etwas zu sagen. Daher sollte diese **nicht ignoriert** werden.

Wenn eine Exception wie folgt ignoriert wird:
```java
try {
    ...
} catch (SomeException e) {
}
```
Ist dies ähnlich wie den Feueralarm zu ignorieren und auszuschalten, sodass niemand anders davon etwas mitbekommt.

Wenn Exceptions ignoriert werden, kann es sein, dass irgendwo im Programm als Folge davon ein Fehler auftritt. Diesen dann zu suchen, ist extrem schwierig.

Manchmal ist es sinnvoll eine Exception zu ignorieren, dann **muss im catch-Block jedoch ein Kommentar stehen, welcher das erklärt.**

Auch macht es dann meistens Sinn, die Exception zu loggen und die Fehlervariable sollte `ignored` genannt werden.
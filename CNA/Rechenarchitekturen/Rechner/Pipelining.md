Eine Prozessor-Pipeline ist eine Art der Parallelisierung, welchen den Prozessor schneller machen.

Dafür braucht es eine Pipeline. Jeder Stufe der Pipeline wird in einem Taktzyklus erledigt:
![[Piepline.png]]
Hält sich der Prozessor an diese Pipeline ist nach allen 5-Zyklen eine Operation erledigt.
Wenn sich der Prozessor in der Stufe S2 befindet, sind alle anderen 4 Stufen jedoch im Leerlauf.

Beim Pipelining wird der Computer beim Ausführen von S2 auch schon die nächste Instruktion abfragen (S1) und so weiter:
![[Pipelining.png]]
Dadurch ist nach den ersten 5 Zyklen mit jedem Zyklus eine weitere Instruktion fertig.


## Erweiterte Eigenschaften
- **Abhängigkeiten** und **Konflikte** zwischen Instruktion können dazu führen dass die Pipeline warten muss. (**Pipeline stall**)
- **Branch-Prediction**: Ist in einer Instruktion ein bedingter Sprung, entscheidet sich der Prozessor für einen Weg (Branch) und rechnet damit auf "gut Glück" weiter.
	- Einfachste Form: Sprung wird nie ausgeführt
	- Dynamic Branch Prediction: Wurde der Sprung zuletz ausgeführt?
- **Flush**: Die ganze Pipeline wird gelehrt und es wird von neuem begonnen
	- Z. B. Bei einer falschen Branch-Prediction
- **Specaulative execution**: Der Prozessor verwendet unbenutzte Ressourcen um im Voraus zu berechnen.

>[!info]
>Zwei order mehrere Aktivitäti heissen nebeläufig, wenn sie zeitgleich bearbeitet werden können.
>- Egal, welche Aktivität zuerst gestartet und ausgeführt wird.
>- Egal, ob die Aktivitäten in umgekehrter Reihenfolge ausgeführt werden
>- Egal, ob die Aktivität gleichzeitig erledigt werden.

Besitzt ein Rechner mehr als eine CPU oder Rechenkerne, kann die Nebenläufigkeit parallel auf Hardwareebene realisiert werden.
- Beschleunigung des Programms, sofern der Kontrollfluss nebenläufige Aktivitäten beinhaltet

Das Abstraktionskonzept in Java für Nebenläufigkeit ist der [[Thread]].


## Vorteile
- Steigerung der Performance.
- Zur Verfügung stehende Rechenleistung kann voll ausgenutzt werden.
- Durch Auslagern blockierter Code-Abschnitte können Anwendungen reaktiv gehalten werden.

## Nachteile
- Erschwerter Debugging (CPU Zuteilung ist nicht deterministisch)
- Prallel ablaufende Threads müssen koordiniert werden.
- Programmcode mit Multithreading-Konzepten kann schwieriger zu verstehen sein und benötigt höheren Wartungsaufwand.


## Anmerkungen
- Zahlreiche Aufgaben, die nebenläufig ausgeführt werden, treten nicht regelmässig auf und sind meist von kurzer Dauer.
- Für jede Aufgabe einen [[Thread]] zu erezeugen belastet das [[Betriebssystem]] unnötig.
- Eine grosse Anzahl an konventionellen [[Thread|Threads]] wirkt sich negativ auf die Leistung des Systems aus. -> Daher werden oft [[Threadpool|Threadpools]] verwendet.
- Jede nebenläufige Aufgabe ([[Task]]) benötigt einen [[Thread]]. Der [[Task]] wird dem [[Thread]] über den [[Konstruktor]] vermittelt.
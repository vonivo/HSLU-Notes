Das [[Betriebssysteme| Betriebssystem]] ist zuständig für die Programmabarbeitung. 

Das OS lädt ein Programm in den [[Speicher|Arbeitsspeicher]]
Das OS kontrolliert und steuert welche Programme wann und für wie lange von der [[Prozessor|CPU]] ausgeführt werden 
Dabei hat jedes laufende Programm einen festgelegten Datenbereich.
Wird das Programm suspendiert wird der gesamte Kontext auf den [[Stack (Rechnerarchitektur)|Stack]] geschrieben
Bei der Wiederaufnahme wird das Programm und sein Kontext aus dem [[Stack (Rechnerarchitektur)|Stack]] geladen
Als Programm und Kontext versteht man die **Registerinhalte + die Zeiger auf den Datenbereich des Programmes. 

Für die Prozessabarbeitung ist  [[Memory Allocation]] sehr wichtig weil es beschreibt wie die Daten gespeichert werden. 


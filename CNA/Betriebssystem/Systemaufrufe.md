Über Systemaufrufe können Anwendungen [[Betriebssysteme|Betriebssystem]]funktionen aufrufen.

Systemaufrufe sind meist in Bibliotheksfunktionen “eingebettet”. Parameter werden über den [[Stack (Rechnerarchitektur)|Stack]] übergeben.
- Dadurch muss man nicht den assembly code für jede Maschine kennen (diese können sich gravierend unterscheiden)

Dabei geht die Kontrolle vom Anwendungsprogramm auf das [[Betriebssysteme|OS]] über und nach der Ausführung wieder zurück.
- Das heisst vom [[User Mode]] in den [[Kernel Mode]] und umgekehrt

Das untenstehende Bild beschreibt einen Systemaufruf über ein C Library, welcher etwas ausliest:
`count = read(fd,buffer,nbytes)`

`fd` beschreibt hier das File (als Value) das ausgelesen werden soll, `buffer` beschreibt den Zwischenspeicher (als Adresse) und `nbytes` bezeichnet die Anzahl Bytes die gelesene werden soll von dem File. Das Resultat `count` beschreibt die Anzahl Bytes die gelesen wurden.

- In den Schritten 1-3 werden die drei Parameter auf den [[Stack (Rechnerarchitektur)|Stack]] gelegt. 
- In Schritt 4 wird der eigentlich Systemaufruf read ausgeführt.
- In Schritt 5 schreibt die Bibliotheksfunktion `read` (in Assembly geschrieben) den korrespondierenden Code für die Read Operation in ein Register
- In Schritt 6 wird die der TRAP Aufruf gemacht um vom [[User Mode]] in den [[Kernel Mode]] zu wechseln
- In Schritt 7 Ordnet der Kernel dem Code für die Read Operation den dazugehörigen System Call Handler zu
- Bei Schritt 8 läuft der System Call Handler
- Ist der System Call Handler fertig wird bei Schritt 9 vom Kernel Mode wieder in den User Mode gewechselt (per TRAP)
- Schritt 10 und Schritt 11 gehen wieder zurück zu dem Aufruf und räumen den [[Stack (Rechnerarchitektur)|Stack]] auf

![[Systemaufrufe.png]]

Siehe Tanebaum S. 50
#flashcards/Rechenarchitekturen 
>[!info]
>Eine **F**ield **P**rogrammable **G**ate **A**rray ist ein Mechanisimus, welcher es Erlaubt beliebige Hardwareschaltungen in einen Chip einzuprogrammieren.

Der FPGA Programmierer kann dabei über **Lookuptabels** spezifizieren, welche physischen Logikgatter wie diese miteinander verschaltet sind und so **extrem schnelle** Rechner bauen.

# Kontrollfragen
**Was ist ein Hauptunterschied der Harvard-Architektur im Vergleich mit der Von-Neumann-Architektur?**
?
Von-Neumann: gemeinsamer Daten- und Programmspeicher. Harvard: Daten- und Programmspeicher getrennt + gleichzeitiger Zugriff möglich.

**Was versteht man bei Rechnerarchitekturen unter einer Pipeline?**
?
Befehle in mehreren Stufen ausführen

**Es kommt vor, dass mit dem aktuellen Inhalt der Pipeline nicht weiter gearbeitet werden kann und der Inhalt der Pipeline muss gelöscht werden = Pipeline Flush. Wann ist dies der Fall?**
?
Wenn die Reihenfolge der Befehlsabarbeitung anders ist als angenommen: z.B. bedingter Sprung wird anders ausgeführt als angenommen oder bei einem Interrupt

**Skizzieren Sie eine superskalare Rechnerarchitektur.**
?
![[Pipeline_with_Multiple_ALUS.png]]
<!--SR:!2024-05-23,4,270-->
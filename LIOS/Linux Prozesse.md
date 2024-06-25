Unter Linux besteht ein [[Prozess]] aus:
- laufendem Computerprogramm im Arbeitsspeicher.
- Sicherheitseigenschaften (Eigentümerinformationen und -berechtigungen).
- Verwaltungsinformationen (Prozessstatus)

Die Umgebung eines Prozesses beinhaltete:
- Lokale und globale Variablen.
- Einen aktuellen Umgebungskontext (z.B Interpreter, Parent-Prozess).
- Zugewiesen Systemressourcen wie [[Programmoutputumleitung|Dateideskriptoren]] und Netzwerkports.

>[!error] Achtung
>Ein Prozess wird immer von einem anderen Prozess (Parent-Prozess) ausgelöst und erbt von diesem die Rechte und Umgebung.

[[Systemd]] ist in Rocky-Linux der erste Prozess mit der PID=1 und wird beim Boot gestartet. Jeder andere Prozess erbt von diesem.

# Starten eines Prozesses
1. Übergeordneter Prozess ruft `fork()` auf und erstellt damit eine neue Prozessstruktur von sich selbst. (Duplizieren den aktuellen Prozess). => **Sicherheitseigenschaften und Umgebung vererben.**
2. Der neue Prozess erhält eine eigene PID und als PPID wird die ID des Parent gesetzt.
3. Der neue Prozess ersetzt nun den Programmcode mit dem Aufruf von `exec()`. Dadurch wird der gesamte Prozess durch ein neues Programm ersetzt.

# Lebenszyklus
![[ProzessLebenszyklus.png]]Im Normalfall wartet der Parent-Prozess mittels `wait()` auf die Beendigung des Child, um danach weiterzuarbeiten.

# Prozessstatus
In linux existieren folgende Prozessstatus:

| Name     | Flag | Statusname und Beschreibung                                                                                                                               |
| -------- | ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Running  | R    | Der Prozess verarbeitet im Moment Daten.                                                                                                                  |
| Sleeping | S    | Der Prozess wartet auf eine Bedingung wie eine Hardwareanforderung, den Zugang zu Systemressourcen oder ein Signal                                        |
|          | D    | Der Prozess befindet sich in einem ununterbrechbaren Schlaf                                                                                               |
|          | K    | Der Status entspricht dem nicht unterbrechbaren Schlaf **D**. Eine wartende Aufgabe kann hier jedoch auf das Signal zu vollständigen Beendigung reagieren |
|          | I    | Eine Untermenge des Status **D**. Wird für Kernel-Threads verwendet.                                                                                      |
| Stopped  | T    | Der Prozess wurde angehalten.                                                                                                                             |
| Zombie   | Z    | Der Prozess ist eigentlich beendet, die Abfrage nach der PID wurde durch den Parent noch nicht gemacht.                                                   |
|          | x    | Prozess wird endgültig freigegeben.                                                                                                                       |

![[Prozessstatus.png]]

- Ist ein Prozess beendet, kann der Parent vom Betriebssystem erfragen, wie er beendet wurde (erfolgreich, abgestürzt, abgebrochen => Exit-Code).
- Daher bleibt der Prozesseintrag in der Prozesstabelle stehen, bis der Parent die Abfrage durchgeführt hat. => Prozess ist ein **Zombie**, sprich er verbraucht keine Ressourcen mehr ausser der Eintrag in der Prozesstabelle.
- Wenn der Parent-Prozess beendet, verwaisen die Kinder (Orphaned) und werden vom Prozess PID=1 adoptiert.

## Auflisten aktueller Prozesse
`top` Zeigt alle laufende Prozesse und Ressourcen an.
`ps aux` Zeigt alle Prozesse an.


# Prozesssignale
Ein Signal ist ein [[CNA/Rechenarchitekturen/Interrupt|Interrupt]] eines Prozesses.
Jedes Signal besitzt eine *Standardaktion*. Für gewühlich ist eine der folgenden:
- Ende -> Programm beendet sich **sofort**.
- Core -> Erstellt ein Speicherabbild bevor das Programm beendet wird.
- Anhalten -> Unterbricht Programm (suspend) und wartete auf Fortsetzung (resume).

Durch Handler-Routinen kann das Standardverhalten implementiert werden.

| Name    | Nr. | Aktion       | Standard | Bedeutung                                                    |
| ------- | --- | ------------ | -------- | ------------------------------------------------------------ |
| SIGSTOP | 19  | Anhalten     | POSIX    | Der Prozess wurde angehalten                                 |
| SIGSTP  | 20  | Anhalten     | POSIX    | Der Prozess wurde manuell durch Benutzer angehalten (STRG-Z) |
| SIGCONT | 18  | Weiterlaufen | POSIX    | Ein angehaltener Prozess soll weiterlaufen                   |
| SIGINT  | 2   | Ende         | POSIX    | Interrupt durch das Termianl oder den Benutzer STRG-C        |
| SIGQUIT | 3   | Ende & Core  | POSIX    | Das Signal `quit` vom Terminal                               |
| SIGTERM | 15  | Ende         | POSIX    | Beedndigung des Programms anfordern. => Softshutdwon         |
| SIGKILL | 9   | Ende         | POSIX    | Sofortiges Beenden                                           |
| SIGHUP  | 1   | Ende         | POSIX    | Das Termianl wurde geschlossen oder beendet.                 |
## Signale Senden
Signale können durch Tastatureingaben gesendet werden:
- Aussetzen/Anhalten -> STRG-z
- Beenden -> STRG-c
- Speicherauszug -> STRG-\\

Alle Signale können mit dem Programm `kill` gesenkt werden. Dies funktioniert über die PID des Prozesses.
- `kill -l` -> Listet alle Signale auf
- `kill -9 5194` -> SIGKILL and Prozess mit PID= 5194

Mit `pkill` kann ein Signal an einen oder mehrere Prozesse gesendet werden die den Auswahlkriterien entsprechen.
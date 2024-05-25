Das Rechenwerk (siehe [[Von-Neuman-Architektur]], [[Harvard Architektur]]) steuert den Programmablauf.
![[Steuerwerk.png]]
Es enthält:
- Programcounter
- Instruction-Register
- Adressregister
- [[CNA/Rechenarchitekturen/Stack|Stackpointer]] (Stapelzeiger)

Das Steuerwerk kann auf zwei Arten realisiert werden

**Festverdrahtet**
- Realisierung mit [[Flip-Flop|Flip-Flops]] welche den aktuellen Zustand speicher. (Finite-State-Machine)
- Enthält einen einfachen Befehlssatz (RISC Reduced Instruction Set Computer)
- Hohe Taktrate

**Mikroprogrammierbar**
- Mikroprogramm von Chipentwickler festgelegt (Firmware)
- Komplexerer Befehlssatz (CISC Complex Instruction Set Computer)

Die heutigen Prozessoren benutzen beide Techniken.
- Ein Steuerwerk enthält ein Mikroprogramm. Darin ist für jeden Maschinenbefehl eine Sequenz an Mikrobefehlen definiert, welche den Maschinenbefehl Schritt für Schritt ausführen.
- Mikroprogramm legt die Werte der Steuersignale fest.

# Kontrollfragen
#flashcards/Rechenarchitekturen 

**Wohin zeigt der Programm Counter?**
?
Auf die Adresse, an welcher der nächste Befehl oder Befehlsteil gefunden wird.

**Zu welchem Befehlstyp gehört der Maschinenbefehl MOV r2, adr ?**
?
Zweiadressbefehl man könnte auch antworten: Datentransferbefehl

**Welcher Wert steht nach Ausführung des Programmabschnitts im Akkumulator A**

|        |                                              |
| ------ | -------------------------------------------- |
| Beginn | LADE Akkumulator A mit #$7F                  |
|        | BRANCH IF PLUS nach LABEL ;Plus falls Bit7=0 |
|        | INCREMENT A                                  |
| Label  | DECREMENT A                                  |
|        | DECREMENT A                                  |
?
$7D (#$7f = 0111 1111 = positiv, also wird der Sprungbefehl ausgeführt)

**Was bedeutet LADE Akkumulator A mit $7F?**
?
Akku <- Inhalt der Speicherzelle $7F

>[!info]
>Ein Interrupt ist eine Unterbrechung des aktuellen Programms für eine **dringende** Aufgabe durch ein **externes Signal**

Ein Interrupt verhält sich ähnlich wie eine Subroutine([[Unterprogramm]]) jedoch sind Interrupt **nicht eingeplant** wie Unterprogramme, sondern werden durch ein **externes Signal** ausgelöst.

Ein Rechner kann mehrere Interrupt-Eingänge haben. Diese werden durch den sogenannten Interrupt-Controller verwaltet.
Den Interrupt-Eingängen werden Prioritäten zugewiesen, zusätzlich können sie aus- und eingeschaltet werden.

Wie bei einem Unterprogramm können sich Interrupts verschachteln, dabei wird immer der Interrupt mit der höchsten Priorität ausgeführt.


## Interrupt-Controller (IRC)
Ein Interrupt verläuft wie folgt:
1. Interrupt Request (IRQ) von einem Gerät
2. Interrupt Controller bearbeitet die Aufforderung und erzeugt ein Interrupt-Signal zur CPU
3. CPU unterbricht
	1. Rette Kontext auf den [[CNA/Rechenarchitekturen/Stack]]
	2. Zeigt Annahme des Interrupt (INTA -> Interrupt Acknowledgement)
	3. List vom IRC die Interrupt-Nummer und verzweigt mit Hilfe der Vektortabelle in die entsprechende Interrupt-Service-Routine
	4. Interrupt-Service-Routine liest Geräteregister aus und startet entsprechende Aktionen
	5. Return von Interrupt (RTI)

## Verschachtelte Interrupts
![[Nested_Interrupt.png]]
# Kontrollfragen
#flashcards/Rechenarchitekturen 

**Benennen Sie einige Aufgaben, die oft mit Stack gelöst werden?**
?
Abspeichern der Rücksprungadresse bei Unterprogrammen, Parameterübergabe, Resultatrückgabe, Zwischenspeicher bei Interrupt: Rücksprungadresse + Registerzustände (= Context)

**Warum wird bei einem Unterprogrammaufruf die Rücksprungadresse auf den Stack gelegt?**
?
(Frage ist etwas trivial)Weil dann von den verschiedenen Stellen des Programms das Unterprogramm aufgerufen werden kann und dann immer die richtige Rücksprungadresse immer am gleichen Ort (Top of Stack) bereitsteht.

**Was ist der Unterschied zwischen einem Unterprogrammaufruf und einem Interrupt?**
?
UP: Wird immer an der gleichen Stelle im Programmablauf aufgerufen, Context wird nicht automatisch gerettet IR: Wird von einem externen Ereignis getriggert, Context wird automatisch gerettet

**Kann bei einem mit 5 Werten belegten Stack auch direkt auf den 2. Wert zugegriffen werden?**
?
Nein, erst muss der 5. dann der 4. dann der 3. dann der 2. Wert gelesen werden.
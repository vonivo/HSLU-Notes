Insgesamt gibt es drei Grobunterteilungen von Befehlen welcher ein [[Rechner|Prozessor]] ausführen kann.
1. Datentransfer
2. Arithmetisches und logische Operationen
3. Programmablaufsteuerung
Mit diesen 3 Gruppen sind alle Anforderungen an einen [[Rechner]] abgedeckt.

## Aufbau eines Befehls
Ein Befehl enthält folgende Informationen
- Durchzuführende **Operation**
- Falls **Operanden** benötigt werden: Typ, Länge [[Adressierungsart]] und Adressangabe
	- Für den ersten Operanden
	- Für den zweiten Operanden
	- Für das Resultat
- **Adresse** des **nächsten Befehls**
	- Kann implizit durch Befehlslänge und aktueller Befehlsadresse sein
	- Explizit durch ein Sprungziel mit absolutem oder relativen Wert

Nicht bei jedem Befehl sind alle Informationen benötigt.

## Codierung des Befehls
- Ein Befehl wird meistens codiert. Ein verbreitetes Format dafür ist der **Mnemoic** (z.B. ADD #1234, adr1, adr2). Hier ist der Mnemonic "ADD".
- Der Typ, Länge und Adressierungsart und Adresse sind implizit im Befehl gegeben.


## Dreiadressbefehl
Ein Dreiadressbefehl setzt sich aus der Operation, der 1. Quelladresse, 2. Quelladresse und der Zieladresse zusammen.
![[ThreeAddressInstruction.png]]![[ThreeAddressInstruction_ALU.png]]
### Beispiele
- ADD $800, $8001, $8002

## Zweiadressbefehl
In einem Zweiadressbefehl sind die Operation, 1. Quelladresse und 2. Quelleadresse vorhanden. Das Resultat wird dann je nach Definition wieder in eine Quelladresse geschrieben.
![[TwoAddressInstruction.png]]
![[TowAddressInstructionALU.png]]
### Beispiel
- ADD $800, $8001


## Einadressbefehl
Der Einadressbefehl enthält nur die Adresse des ersten Operanden, der zweite Operand und die Zieladresse verstecken sich im Befehl implizit oder kommen aus dem Akkumulator.
![[OneAddressInstruction.png]]![[OneAddressInstructionALU.png]]


# Kontrollfragen
#flashcards/Rechenarchitekturen 
**Was sind die Vor- und Nachteile der Einadressbefehle gegenüber Zwei- oder Dreiadressbefehlen?**
?
- + Scheneller
- + Weniger Speicherzugriffe
- + Befehl ist kürzer
- - Akkumulator wird immer überschrieben
- - Weniger flexibel
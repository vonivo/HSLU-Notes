#flashcards/Rechenarchitekturen 
Der Arbeitsspeicher ist über zwei Leitungen (**Busse**) angeschlossen.
Der **Datenbus** überträgt die Daten, welche im Speicher sind und der **Adressbus** zeigt auf, auf welche Speicherzelle zugegriffen wird.

![[Skizze_speicher.png]]
Innerhalb der CPU befinden sich Register, welche auch eine einzelne Speicherzelle sind.

Die Breite des Adressbusses (Anzahl Bits) ergibt die Anzahl an Speicherzellen $2^{Breite\space Adressbus}$. Beispiel. Ein Adressbus mit einer Breite von $16$ Bit kann insgesamt $2^{16}=65'536$ Speicherzellen adressieren.

Die Speicher Grösse ergibt sich aus der Anzahl der Speicherzellen mal der **Breite des Datenbusses**.

Beispiel:
**Breite Adressbus:** 16
**Breite Datenbus:** 8
**Speichergrösse**: $2^{16}*8 = 512Kb$

Der Speicher hat an sich noch 3 Steuersignale:
![[Speicherbaustein.png]]

| Name | Beschreibung<br><br>                                                                          |
| ---- | --------------------------------------------------------------------------------------------- |
| CS   | Chip-Select -> Zeigt an, welcher Chip aktiv ist (eigentlich eine Erweiterung des Datenbusses) |
| WE   | Write-Enabled -> Zeigt an ob der Speicher beschrieben wird                                    |
| OE   | Output-Enabled -> Zeigt an ob der Speicher gerade gelesen wird.                               |

# Kontrollfragen
**An einem Speicher sind 12 Adressleitungen angeschlossen. Wie viele Speicherplätze hat der Speicher? Wie gross ist seine Kapazität, wenn er eine Breite von 8 Bit hat?**
?
Kapazität $2^{12} * 8$, Speicherplätze: $2^{12}$

Der Hack-Computer ist eine [[Von-Neuman-Architektur|von Neumann Plattform]].
Die Maschine ist eine 16-Bit-Maschine, bestehend aus einer CPU, zwei separaten Speichermodulen, die als Befehls- und Datenspeicher dienen und zwei speicher belegte I/O-Geräten: Bildschirm und Tastatur.
![[Pasted image 20260618095449.png]]

- Der Ausgang des PC ist mit dem Eingang des ROM verbunden. Somit Ist der Ausgang des ROM immer `ROM[PC]`, daher den Inhalt der Befehlspeichersatz auf den PC zeigt.

**Taktbetrieb**
- **Execute**: Die Decodierte Anweisung wird gleichzeitig an verschiedene HW-Elemente weitergeleitet. 
	- Handelt es sich um einen [[A-Befehl]] (`MSB=0`), wird das `A`-Register auf die im Befehl eingegebenen 15-Bit Adresse geladen.
	- Handelt es sich um einen [[C-Befehl]] (`MSB=1`)  werden die zugrunde liegenden Segmenten (`a`, `c`, `d` und `j`) als Steuerbits behandelt, die die [[ALU]] und die Register veranlassen den Befehl auszuführen.
- **Fetch**: Welcher Befehl als nächsten ausgeführt wird, hängt von den Sprungbits `j` des aktuellen Befehls und von der ALU-Ausgabe ab. Zusammen bestimmen diese ob ein Sprung ausgeführt werden soll. Wenn ja, wird der [[Programm-Counter]] auf den Wert des `A`-Registers gesetzt. Andernfalls wird der PC um eins erhöht und im nächsten Takt den Befehl aus dem ROM geholt.



**Komponenten**
- [[CPU]]
- 

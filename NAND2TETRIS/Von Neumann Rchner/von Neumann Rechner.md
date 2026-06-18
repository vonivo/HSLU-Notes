![[Pasted image 20260618094026.png]]
### Komponenten:
- **Arithmetische logische Einheit (ALU)**: Die [[ALU]] ist für die Ausführung aller arithmetischer und logischen Operationen auf tiefer Ebene zuständig.
- **Register:** Damit die CPU Zwischenresultate lokal speicher kann, gibt es Hochgeschwindigkeitsregister, welche jeweils ein Wortspeichern können.
	- Datenregister
	- Adressregister
- **Steuereinheit:** Ein Computerbefehl ist in der Regel ein Binärwort aus $16$, $32$ oder $64$ Bit. Bevor ein solcher Befehl ausgeführt werden kann, muss er dekodiert werden. Die dekodierten Informationen werden dann genutzt, um den anderen HW-Komponenten zu signalisieren, wie die Befehle auszuführen sind. Diese Dekodierung wird durch die Steuereinheit gemacht.
	- Ein weiteres Element der Steuereinheit ist der [[Programm-Counter]] welcher herausfindet, welcher Befehl als nächstes ausgeführt werden soll.
		- Wird kein Sprung gemacht, wird die Adresse um eins erhöht.
		- Wird ein Sprung gemacht, lädt er die Adresse des Ziels.
- **I/O:** Damit viele Geräte mit wenig Aufwand angesteuert werden können existiert das Konzept der **Speicherabbildung**.
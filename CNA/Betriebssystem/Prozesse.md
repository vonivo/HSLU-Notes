---
aliases:
  - Prozess
---
Ein Prosses ist ein laufendes Programm inklusive seiner Umgebung. 

- Das Wechseln zwischen zwei Prozessen wird als **Context Switching** bezeichnet. ^48789b
	- das braucht Zeit → [[Multithreading]]
- Ein [[CNA/Betriebssystem/Scheduling]] [[Algorithmus]] bestimmt welcher Prozess wann bearbeitet wird 

# Prozessaufbau
Ein Prozess kann man auf verschiedene Weise betrachten:

![[Pasted image 20240523203048.png|inlR|200]]
Physikalisch gibt es immer noch nur ein Programm Counter. Dieser wechselt zwischen den Prozessen und zeigt immer das Value für den jeweiligen Prozess an. 

![[Pasted image 20240523203434.png|200]]
Logisch sind es aber vier Werte welche separat voneinander hoch gezählt werden. 
![[Pasted image 20240523203544.png]]
Zeitlich sieht es dann so aus, so kann immer ein Stückchen von einem Prozess nach dem anderen ausgeführt werden. 

# Prozesszustände
## Entstehung
Prozesse entstehen in den folgenden Szenarios:
- Systeminitialisierung
- explizit durch den Benutzer initiiert
- als Batch-Jobs zu bestimmten Zeiten (cronjob)
- ein anderer laufender Prozess erzeugt einen neuen Prozess

Prozesse entstehen durch [[Systemaufrufe]]
Window:
- `createProcess` mit 10 [[Parameter]] um die Umgebung zu bestimmen
Unix: 
- `fork` erzeugt eine Kopie des laufenden Prozess
- `execv` ladet das neue Programm in den Prozess

## Beendigung
- Normale Beendigung (freiwillig)
- Beendigung aufgrund eines Fehlers (freiwillig)
	- [[Prozessor]] entdeck einen Error (Usereingabe)
- Beendigung aufgrund einer Fehlers (unfreiwillig)
	- Error wird durch Prozess verursacht (Bug)
- Beendigung durch einen anderen Prozess (unfreiwillig)

## Zustände
Prozesse können die folgenden Zustände haben:
- rechnend (running): [[Prozessor|CPU]] führt aus
- rechenbereit (ready): temporär suspendiert
- blockiert (blocked): wartet auf ein externes Ergebnis

### Zustandsübergänge
1. Running → Blocked: Prozess blockiert weil er auf Input wartet
2. Running → Ready: Prozess wird suspendiert. *Sein Kontext (Prozesskontrollblock) wird gespeichert*
3. Ready → Running: Prozess wird wieder aufgeweckt. *Sein Kontext (Prozesskontrollblock) wird wieder geladen*
4. Blocked → Ready: Blockierungsgrund beendet
![[Pasted image 20240523204801.png]]

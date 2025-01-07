---
aliases:
  - Interrupt
---
Interrupts sind eine Unterbrechungsanforderung für **dringende** Aufgaben

Interrupts werden gehandelt mit eine Interrupt Service Routine (ISR)
- diese funktioniert ähnlich wie ein [[Unterprogramme|Unterprogramm]] → einfach durch externes Ereignis ausgelöst

Ein [[Rechner]] kann mehrere Interrupteingänge haben, oder ein [[Interruptcontroller]]verwenden
- Interrupt Eingänge haben Prioritäten (einzeln freigeben und sperren möglich)
- es können mehrere Interrupts gleichzeitig aktiv sein, aber nur ein ISR

Sonderfall des Interrupts ist die Trap → Interrup per Software
- Verwendet beim Kontextwechsel vom [[Betriebssysteme|Betriebssystem]]

# [[Gerätemanagement|I/O Management]]
Interrupts sind eine Methode des [[Gerätemanagement|I/O Management]]

Bei Interrups läuft der Anfang der I/O Operation ähnlich ab wie beim Busy Waiting:
Die Anwendung sendet ein System Call an das OS. 
Das OS gibt den Call weiter mit einem Prozeduraufruf an den Treiber. 
Der Treiber initiiert die I/O Operation und möchte Daten liefern/empfangen

Nun programmiert der [[Gerätetreiber]] den [[Gerätetreiber]] aber so das dieser einen Interrupt auslöst sobald er ready ist. 
Der Treiber gibt danach bereits schon zurück an die Anwendung
Die Anwendung wird vom OS blockiert (blocked), da sie ja auf das I/O Gerät wartet. 
Im Unterschied zum Busy Waiting **können in dieser Zeit aber andere [[CNA/Betriebssystem/Prozesse]] ausgeführt werden**

Ist das Gerät nun ready, sendet es einen Interrupt an die [[Prozessor|CPU]]. Die [[Prozessor|CPU]] suspendiert die momentane Aktion und ruft den Interrupthandler im [[Gerätetreiber]] auf. Dieser bestimmt dann die weiteren Aktionen. 


Auf dem linksuntenstehenden Bild ist der Ablauf nochmals zu sehen:
1. Treiber gibt Gerätecontroller an was er tun soll wenn das Gerät bereit ist
2. Sobald das Gerät bereit ist verständigt der Gerätecontroller den [[Interruptcontroller]]. Dieser entscheidet wie der Interrupt zu priorisieren ist
3. Sobald der [[Interruptcontroller]] den Interrupt ausführen möchte verständigt er die [[Prozessor|CPU]]
4. Der [[Interruptcontroller]] gibt der [[Prozessor|CPU]] die nötigen Informationen zu dem Gerät damit sie mit den Information herausfinden kann wo der Interrupthandler sich im Memory befindet. 

Auf der Grafik rechts unten sieht man den Aufruf des Interrupthandlers (Tanenbaum S. 32)
![[Interrupts.png]]
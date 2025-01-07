Das [[Betriebssysteme|Betriebssystem]] greift mithilfe von [[Gerätetreiber|Gerätetreibern]] auf Geräte zu. Die [[Gerätetreiber]] wiederum verwenden [[Gerätetreiber#Gerätecontroller|Gerätecontroller]] mit eigenen Registern als Schnittstelle zu den eigentlichen Geräten. 

![[Gerätemanagement.png]]

# Interaktion mit I/O Geräten
Bei der Interaktion mit I/O Geräten gibt es drei verschiedene Herangehensweisen:
[[Polling (Busy Waiting)]]
[[CNA/Betriebssystem/Interrupts]]
[[Direct Memory Access (DMA)]]

Für den Umgang mit angeschlossenen Geräten benötigt das [[Betriebssysteme|OS]] Informationen über [[CNA/Betriebssystem/Interrupts|Interrupt]]-Nummern, Interruptlevel (Priorität) und I/O-Adressen
- Früher wurde das statisch am Gerätecontroller festgelegt
- Heute erledigt das der PCIe-Bus, welcher die Informationen dynamische während der Laufzeit zuweist

# Addressierung von I/O Geräten
Siehe [[IO Mapping]]
Polling eine Methode des [[Gerätemanagement|I/O Management]]

Beim Busy Waiting sendet eine Anwendung ein System Call an das OS. 
Das OS gibt den Call weiter mit einem Prozeduraufruf an den Treiber. 
Der Treiber initiiert die I/O Operation und möchte Daten liefern/empfangen.

Dafür muss er auf eine Rückemeldung des Gerätes warten. 
Dazu frägt er fortlaufend das Ready Register des Gerätecontrollers ab, bis das Ready Register anzeigt dass das Gerät ready ist. 
Danach kann den Gerätetreiber fortfahren und anschliessend an die Anwendung zurückmelden. 
**Während dieser ganzen Zeit ist die [[Prozessor|CPU]] belegt. Deshalb ist diese Herangehensweise zu vermeiden**

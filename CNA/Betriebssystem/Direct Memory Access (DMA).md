Direct Memory Access ist eine Methode des [[Gerätemanagement|I/O Management]]

Dabei wird spezielle Hardware verwendet: Ein Direct Memory Access Controller. Dieser Kontrolliert den Bitfluss zwischen Memory und gewissen Geräte ohne Intervention der [[Prozessor|CPU]].

Dadurch kann die [[Prozessor|CPU]] ihre Ressource anderweitig einsetzen. 

Vor der Nutzung teilt die [[Prozessor|CPU]] dem DMA-Controller mit wie viele Bits von welcher Quelle zu welchem Ziel befördert werden müssen. 

Ist der DMA Controller fertig sendet er einen [[Interrupts|Interrupt]] zu der [[Prozessor|CPU]]. 

Der DMA Controller ist im Memory Controller integriert. 

![[DMA.png]]
# Halbaddierer
Der Halbaddierer kann die Operation durchführen und zwei Bits miteinander Addieren. Dabei verfügt er noch über ein Carry-Bit:
Die Warhheitstabelle sieht wie folgt aus:
![[Halbaddierer.png]]
Ü -> Carry-Bit
S -> Bit selbst

Das S kann über ein [[Logische Verknüpfungen|XOR-Gater]] realisiert werden, das **Ü** wird über ein [[Logische Verknüpfungen|AND]] gemacht
![[Halbaddierer_Gater.png]]

## Volladdierer
Der Volladdierer Verfügt über 3 Eingänge: Das Bit **A**, das Bit **B** und über ein Carry-Bit **$Ü_{e}$**. Somit kann der vollständig Addieren. Dabei verfügt er über die Ausgänge des Bit und des Carry.
![[Volladdierer_tabelle.png]]
Um diese Tabelle zu bilden, müssen zwei Halbaddierer genutzt werden und mittels einem [[Logische Verknüpfungen#OR|OR]] verknüpft werden.

![[Volladdierer.png]]

Um einen 3-Bit Addierer zu machen, werden nun 3 Volladdierer in Serie geschaltet.
Es existieren verschieden Adressierungsarten um Daten anzusprechen.

## Absolute oder direkte Adressierung
Die direkte **A**dressierung ist ein Adressierung auf eine **absolute Adresse**

Beispiel: LDA $0800

Hier wird der Wert hinter der [[Zahlensysteme|Hexadezimalen]]-Adresse 0800 geladen.

## Registeradressierung
Bei der Registeradressierung wird nicht der Speicher über eine Adresse angesprochen, sonder es wird der Wert eines Registers geladen.

Bsp: LDA R1

In diesem Beispiel wird das Register mit dem Namen **R1** geladen

## Unmittelbare Adressierung
Die unmittelbare Adressierung sagt, dass der unmittelbar nachfolgende Wert nicht als Adresse interpretiert werden soll, sondern als Wert geladen wird.

Bsp: LDA #$F3

Das Zeichen **#** zeigt, dass der hexadezimale Wert 'F3' geladen werden soll.

## Indirekte Adressierung
Bei der indirekten Adressierung wird der Wert hinter einer Adresse als weitere Adresse interpretiert und dann dieser Wert benutzt. Verhält sich sehr ähnlich wie ein Pointer in C.

Beispiel: LDA ($6E3F)

Hier wird zuerst auf den Wert hinter '6E3F' zugegriffen. Dieser Wert ist dann die endgültige Adresse:
![[IndirectAddresses.png]]

## Indizierte Adresse
Bei der indizierten Adressierung wird anhand von einer Startadresse und einem Versatz die Adresse berechnet. So funktionieren Arrays.

Beispiel: LDA $0700, X

Hier wird die Startadresse 0700 plus den Wert von X gerechnet und dann auf diese Adresse zugegriffen.



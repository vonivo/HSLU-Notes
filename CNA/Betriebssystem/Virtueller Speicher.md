Virtueller [[Speicher]] ist eine Möglichkeit den [[Speicher|Arbeitsspeicher]] mittels [[Memory Management]] zu erweitern. 

Dabei wird der [[Speicher]] in Pages eingeteilt. Diese virtuellen Pages werden dann den physischen Pages mittels Page-Table zugeordnet. Die Page-Table liegt in der MMU.

Das sieht dann folgendermassen aus:

![[Pasted image 20240526154444.png]]

![[Pasted image 20240526154510.png]]


# Swapping
Alle Seiten welche sich zur Zeit nicht im Memory befinden werden auf die Festplatte geswapped mithilfe einer Auslagerungsdatei. –> Swapping.
- Werden die Pages wiedergebraucht werden sie in den [[Speicher|Arbeitsspeicher]] geladen. 
 
![[Pasted image 20240526154741.png]]

Eine anderer Anwendungsfall für Swapping ist der Hibernation Modus eines Computer, da wird der gesamte [[Speicher|Arbeitsspeicher]] in ein Swapfile geschrieben. 
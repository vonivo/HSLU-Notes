>[!Definition]
>Bei einer offenen Schichtenarchitektur können Schichten offen oder geschlossen sein.

**Offene Schicht**
Eine offene [[Software-Schichten|Schicht]] kann von **einer direkt darüberliegenden** Schicht übersprungen werden:
- vermeidet horizontale Abhägigkeiten.
- Performancegewinn, falls nur ein Methode-Warpping besteht.
![[Offene_Schichtenarchitektur.png]]

>[!Info]
>Alternativ können Schichten rekursiv verschachtelt werden.


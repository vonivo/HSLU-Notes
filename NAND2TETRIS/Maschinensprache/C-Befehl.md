>[!Definition]
>Der **C-Befehl** stellen die Command-Befehle der Hack-Plattformd dar, mit dem fast alles erledigt wird. Der Befehl beinhaltet die Antworten auf folgende Frage:
>- Was soll berechnet werden?
>- Wo soll der berechnete Wert gespeichert werden?
>- Was soll als nächstes geschehen?
>  
> symbolisch: `dest = comp; jump`
>  - Entweder Feld `dest` oder `jump` kann weggelassen werden.
>  - Wenn `dest` leer ist, wird `=` weggelassen
>  - Wenn `jump` leer ist, wird `;` weggelassen.
>    
> binär: `1 11 a cccccc ddd jjj`

**A-Teil**
Über das `a` Bit kann gesteuert werden, ob der eine Operand von Memory `M` oder vom Register `A` gelesenw erden soll. Wenn `a=1` wird `M` verwendet, sonst `A`.

**C-Teil**
Der C-Teil repräsentiert die **6** Steuerbits der [[ALU|Hack-ALU]].
![[Pasted image 20260616193903.png]]

**D-Teil**
Der `d`-Teil spezifiziert die Destination der Berechnung:
![[Pasted image 20260616194255.png]]

**J-Teil**
Wenn kein `j`-Teil spezifiziert ist, spring der Computer zu der nächsten Adressen, ansonsten kann ein Sprung ausgeführt werden:
![[Pasted image 20260616194411.png]]

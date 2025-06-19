>[!Definition]
>Sequential Consistency beschreibt:
>- Lese- und Schreiboperationen aller beteiligten Systeme können in eine globale sequentielle Abfolge geordnet werden.
>- Die Operationen pro System sind in der globalen Abfolge in der selben Ordnung wie sie auf dem Teilsystem vorkamen.
>- Zeit spielt dabei keine Rolle.

Eine verteilte Eingabe- und Verarbeitungs-Applikation verlang oft Sequential Consistency.

**Vorteil**
Unabhängige Teiloperationen blockieren das Gesamtsystem nicht.

>[!Info]
>Man nehmen einen Stack pro Teilsystem, welches die Abfolge der Schritte im Teilsystem enthält.
>Um eine sequenzielle Konsistenz zu erhalten, dürfen wir nun beliebig Operationen von des Stack nehmen und anfügen. Die Reihenfolge innerhalb des Stacks muss gleichbleiben.


## Beispiel
Die folgende Applikation schreibt in ein Konto:
$K\implies B$ lese von Konto $K$ und erhalte den Betrag $B$
$B\implies K$ schreibe den Betrag $B$ in Konto $K$.

System welches sequenzielle Konsistenz erfüllt:
![[sequnetialConsistency.png]]
Mögliche Abfolge:
$$
\begin{align}
X\implies10|20\implies Y|Y \implies20|X \implies 10|15\implies X|Y\implies20 \\
15 \implies Y|20\implies Z
\end{align}
$$

System welches sequenzielle **nicht** Konsistenz erfüllt:
![[sequentialConsistency2.png]]

Abfolge kann nicht global zusammengestellt werden, **ohne** die Reihenfolge innerhalb des Systems $B$ oder $A$ zu ändern.

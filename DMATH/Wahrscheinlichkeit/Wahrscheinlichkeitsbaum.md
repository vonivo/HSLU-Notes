[[Wahrscheinlichkeit|Wahrscheinlichkeiten]] können auch mittels einem [[Bäume|Baum]] berechnet werden.

Wird nehmen dazu folgendes Spiel an:
- Es wird ein Preis hinter $3$ Türchen versteckt.
1. Der Spieler wählt eines der 3 Türchen aus.
2. Der Showmaster öffnet eines der zwei verbleibenden Türchen hinter welchen sich der Preis nicht versteckt.
3. Der Spieler erhält die Möglichkeit seine Wahl nochmals zu ändern.

Wird die Wahrscheinlichkeit erhöht, wenn der Spieler seine Wahl noch ändert?

Wenn der Spieler die Wahl nicht änder, hat er nach der [[Laplaceverteilung]] ein $\frac{1}{3}$ Wahrscheinlichkeit zu gewinnen:
$$
p(\text{Gewinn}) = \frac{\text{Anzahl g. Fälle}}{\text{Anzahl m. Fälle}} = \frac{1}{3}
$$
Ändert der Spieler seine Wahl, können wir das mit folgendem Spielbaum abbilden![[Pasted image 20241226164052.png]]
Alle Enden, welche schwarz sind (Spieler gewinnt nicht) haben eine Wahrscheinlichkeit von $\frac{1}{18}$.

Wahrscheinlichkeit nicht zu gewinnen: $\frac{6*1}{18} =\frac{3}{9}=\frac{1}{3}$

Wenn der Spieler seine Wahl ändert, kann er seine Gewinnchance somit auf $1-\frac{1}{3} = \frac{2}{3}$ steigern.


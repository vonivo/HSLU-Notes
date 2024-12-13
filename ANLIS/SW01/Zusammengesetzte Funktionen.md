Zusammengesetzte Funktionen sind [[ANLIS/SW01/Funktionen/Funktion]] die von einer oder meheren zweiten Funktion abhängen.

## Beispiel 
Ein kreisförmiger Ölteppich dehne Sich mit der Zeit $t$ aus. Ausgehend vom (zeitabhängigen)  Radius $r=g(t) = 1 +t$ ergibt sich die Fläche A:  
$A = f(r)=\pi r^2$ wobei $r=g(t)=1+t)$
Also ist A eine aus f und g zusammengesetzte Funktion 
$$
A = f(g(t))= (f\circ g)(t) = \pi(1+t)^2
$$

Hier ist $f$ die **äussere Funktion** (welche zuletzt angewendet wird) und $g$ die **innere Funktion** (welche zuerst angewendet wird).   

Oft schreibt man $A = A(r)$ und $r= r(t)$, d. h. $A=A(r(t))$. Damit deutet man an, dass $A$ eine Funktion von $r$ ist (nämlich die Funktion $A(r)$) und $r$ ist wiederum eine Funktion von $t$ (nämlich die Funktion $r(t)$).  

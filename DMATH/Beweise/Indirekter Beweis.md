Falls ein [[Direkter Beweis|direkter Beweis]] schwierig ist, kann man versuchen einen indirekten Beweis zu führen.

## Beweis durch Kontraposition
Statt zu zeigen, dass $p\to q$ gilt, zeigen wir, dass $\neg q\to \neg p$ gilt. Da diese beiden [[Proposition|Propositionen]] logisch äquivalent sind kann so indirekt bewiesen werden, dass $p\to q$ gilt.

### Beispiel
**Behauptung:** Sei das Quadrat $n^{2}$ eine natürliche Zahl gerade. Dann ist auch $n$ gerade.
$$
n\in\mathbb{N} n^{2} \text{ gerade} \to n \text{ gerade}
$$
**Beweis**
Falls $n$ ungerade ist, gilt $n=2k+1|k\in\mathbb{Z}$
$$
\begin{align}
n^{2} \text{ gerade} \to n \text{ gerade} &= n \text{ ungerade} \to n^{2} \text{ ungerade} \\
n^{2}&=(2k+1)^{2} \\
&=4k^{2}+4k+1 \\
&=2(2k^{2}+2k)+1
\end{align}
$$
## Beweis durch Kontradiktion
Um die Aussage $p$ zu beweisen nimmt man an $\neg p$ sei wahr und führt diese Aussage durch [[logisches Schliessen]] auf den Widerspruch $q(q=F)$, d.h. $\neg p \to p$ also $\neg p\to F$ somit muss $\neg p$ falsch sein und dadurch $p$ wahr.

### Beispiel
**Behauptung**: Schwere Objekte fallen nicht schneller als leichtere.
**Beweis**:
Angenommen, schwere Objekte fallen schneller als leichtere.
1. Wir nehmen ein schweres und ein leichtes Objekt und kleben beide Zusammen.
- Einerseits müsste die Fallgeschwindigkeit dieses neuen Objektes zwischen den Geschwindigkeiten der Ausgangsobjekte liege, denn das leichte (langsam fallende) Teilobjekt wird den Fall des schwereren (schnell fallende) Teilobjekt abbremsen.
- Andererseits ist das neue Objekt sicher schwerer als jedes einzelne Teilobjekt und müsste somit auch schneller fallen als beide.
=> Beide logischen Überlegungen wiedersprechen sich, unsere Annahme muss also falsch sein.
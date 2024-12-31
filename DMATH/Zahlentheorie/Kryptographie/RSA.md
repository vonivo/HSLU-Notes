Im Jahr 1977 wurde RSA, von Ronald Lynn Rivest (amerikanischer Mathematiker und Kryptologe), Adi Shamir (israelischer Kryptographieexperte) und Leonard Max Adlemann (US-amerikanischer Professor für Informatik und Molekularbiologie) erfunden. Da Adlemann seinen Anteil als gering einschätzte, wollte er zuerst nicht als Autor genannt werden. So kam es zur nicht-alphabetischen Reihenfolge der
Autoren in der Abkürzung RSA.

=> RSA basiert darauf, dass die Primfaktorenzerlegung einer gorssen Zahl rechnerisch fast unmöglich ist. (siehe. Theorem [[Modulare Quadratwurzel]])
## Ablauf
### Schlüsselerzeugung
1. Wähle zwei grosse (mind. $300-600$ stellige) Primzahlen $p$ und $q$.
2. Berechne $n=p\cdot q$ ($n$ sollte ungefährt 4096-Stellen lang sein)
3. Berechne $\phi(n)=(p-1)(q-1)$ ([[Eulersche Phi-Funktion]])
4. Wähle eine zu $\phi(n)$ [[ggT und kgV|teilerfremde]] Zahl $e$ (meist $2^{16}+1 = 65'537$).
5. Bestimme ein [[Multiplikative Inverse|modulares Inverses]] modulo $\phi(n)$ zu $e$, d.h. eine Zahl $d$ mit
$$
e\cdot d=1+k\phi(n)\text{   bzw.   }e\cdot d\equiv 1\text{ mod }\phi(n)
$$
	für eine ganze Zahl $k \in\mathbb{Z}$ ([[Erweiterter Euklidischer Algorithmus]]).
6. **Privater** Schlüssel: $d$ (auch $p,q$ und $\phi(n)$ müssen geheim bleiben).
7. **Öffentlicher** Schlüssel: $(n,e)$

### Verschlüsselung
$$
f_{e}(m)=m^{e}\text{ mod n} =c
$$
### Entschlüsselung
$$
f_{d}(c)=c^{d}\text{ mod }n =m
$$

## Korrektheit
Daüfr wird auch der [[Satz von Euler]] verwendet.
$$
\begin{align}
f_{d}(c) &= c^{d}\text{ mod }n &\text{Definition der Entschlüssenlungsfunktion} \\
&=(m^{e})^{d}\text{ mod n} &\text{Wir wisse:}c=m^{e}\text{ mod }n\\
&=m^{ed}\text{ mod }n &\text{Potzenzgesetz}\\
&=m^{1+k\phi(n)}\text{ mod n} &\text{Konstruktion von d: }ed=1+k\phi(n)\\
&=(m^{\phi(n)})^{k}\cdot m \text{ mod }n &\text{Potzenzgesetz} \\
&=(m^{\phi(n)}\text{ mod }n)^{k}\cdot(m\text{ mod }n)&\text{Modulo rechnen immer erlaubt} \\
&=1^{k}\cdot m\text{ mod }n &\text{Satz von Euler} \\
&= m&\text{m<n}
\end{align}
$$


## Beispiel
Wir wählen die Primzahlen $p = 29$ und $q = 53$, den Exponenten des öffentlichen Schlüssels $e = 47$ und verschlüsseln die Meldung $m = 131$. Führen Sie die drei Schritte (Schlüsselerzeugung, Ver- und Entschlüsseln) durch.
**Schlüsselerzeugung**
1. $n=29\cdot53=1537$
2. $\phi(n)=28\cdot52=1456$
3. Inverse finden:

| $1456$ | -    | $1$  | $0$   |
| ------ | ---- | ---- | ----- |
| $47$   | $30$ | $0$  | $1$   |
| $46$   | 1    | $1$  | $-30$ |
| 1      |      | $-1$ | $31$  |
$d=31$
$(1537,47)$

**Verschlüsseln**
$$
131^{46}\text{ mod }1537 = 570
$$
**Entschlüsseln**
$$
570^{31}\text{ mod }1537=131
$$

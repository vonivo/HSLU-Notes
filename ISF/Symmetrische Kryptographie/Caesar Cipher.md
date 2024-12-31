- Einfach zu Bruteforce
- Frequenzanalyse → Häufigkeit der Buchstaben Analysieren

**Beispiel**
$M=K=C=\mathbb{Z}_{26}=\{ 0,1,2,\dots,25 \}=\{ a,b,c,\dots,z \}$.
Statt Buchstaben verwenden wir die Zahlen $\{ 0,1,2,\dots25 \}$. Dafür muss die Nachricht zuerst kodiert werden.

Verschlüsseln:
$$
c=f(k,m)=m+k \text{ mod }26
$$
Entschlüsseln:
$$
m=f^{*}(k,c)=c-k\text{ mod }26
$$

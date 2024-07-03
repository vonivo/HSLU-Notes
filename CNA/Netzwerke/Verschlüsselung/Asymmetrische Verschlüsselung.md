Bei der asymetrischen Verschlüsselung besitzt jeder Kommunikationsteilnehmer ein Schlüsselpaar:
- öffentlicher Schlüssel und
- privater Schlüssel

Eine Verschlüsselte Nachricht wird mit einem öffentlichen Schlüssel verschlüsselt und kann dann nur mit dem dazugehörigen Schlüssel entschlüsselt werden.

![[AsymmetrischeVerschlüsselung.png]]

# RSA Beispiel
## Alice
1. Wähle Primzahl $p=11$ und $q=17$
2. Bestimme $n$ und $(n)$:
$$
\begin{align}
n &=  p \times q \\
&=11\times17 \\
&= 187 \\
(n) &=(p-1)\times(q-1) \\
&=10\times 16 = 160
\end{align}
$$
3. Wähle $e$ möglichst klein, sodass:
$$
\text{ggt}(e,(n)) = \text{ggt}(7, 160) =1
$$
4. Suche $d$ mit $(e \times d) \% (n) = 1$ => $d = 23$
5. Publiziere $n$ und $e$ => Public Key

## Verschlüssel
$$
c = p^{e}\%n
$$
## Entschlüsseln
$$
p = c^{d}\%n
$$

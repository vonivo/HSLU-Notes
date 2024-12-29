>[!Definition]
>Eine **Rekursionsbeziehung** der [[Reelle Zahlenfolgen|Folge]] $\{ a_{n} \}$ ist eine Beziehung der Form
>$$
>a_{n}=f(a_{n-1}, a_{n-2},\dots a_{2}, a_{1}), \forall n\geq n_{0},n_{0}\in\mathbb{N}^{+}
>$$
>Eine **Lösung dieser Rekursionsbeziehung** ist eine [[Reelle Zahlenfolgen|Folge]], die diese Relation erfüllt.

## Beispiel
### Beispiel 1
Gegeben sei die Rekursionsbeziehung $a_{n}=2a_{n-1}-a_{n-2}$ für alle $n=2,3,4,\dots$.
Sind nachfolgende Zahlenfolgen Lösungen dieser Rekursion?
1. $a_{n}=3n$
$$
\begin{align}
a_{n-1}&=2(3(n-1)) \\
a_{n-2}&=3(n-2) \\
 \\
2a_{n-1}-a_{n-2}&\stackrel{?}{=}3n \\
2(3(n-1))-3(n-2)&\stackrel{?}{=}3n \\
6n-6-3n+6&\stackrel{?}{=}3n \\
3n &= 3n
\end{align}
$$
=> $3n$ ist eine Lösung.
2. $a_{n} = 2^{n}$
$$
\begin{align}
a_{n-1}&=2^{n-1} \\
a_{n-2}&=2^{n-2} \\
 \\
2^{n}&\stackrel{?}{=}2(2^{n-1})-2^{n-2} \\
&\stackrel{?}{=}2^{n}-2^{n-2} \\
&\stackrel{?}{=}n^{n-2}(2^{2}-1) \\
&\stackrel{?}{=}n^{n-2}(3)
\end{align}
$$
=> $2^{n}$ is keine Lösung.
3. $a_{n}=5$
$$
\begin{align}
a_{n-1}&=4 \\
a_{n-2}&=3 \\
 \\
5&\stackrel{?}{=}2\cdot4-3 \\
&=5
\end{align}
$$
=> $5$ ist eine Lösung.

### Beispiel 2
Ein Computersystem betrachtet eine Folge von Dezimalziffern als ein gültiges Passwort, wenn es eine **gerade Anzahl von Nullen** enthält (z.B. 1230329830 ist gültig und 1203040556 ist ungültig). Sei an die Anzahl gültiger Passwörter der Länge n. Gesucht: Rekursionsbeziehung für an.

Um diese Rekursionsbeziehung zu beschreiben, beginnen wir mit einem PW der der Länge $n$:
1. Da ein gültiges PW eine gerade anzahl "Nullen" enthalten muss unterscheiden wir die 2 Fälle: 
	1. Letze Zahl ist keine Null
		Wir Zeichnen dass ein. Da die Letzte Zahl keine $0$ ist, muss daher das Passwort vorherschon eine gerade Anzahl Nullen enthalten und ist somit gültig. => Also sprich die Anzahl dieser Passwörter bei der die Stelle $n$ eine $0$ ist, ist $9a_{n-1}$
	2. Letze Zahl ist eine Null.
		Ist die Lezte Zahl eine Null, muss das Passwort ohne die Letzte Zahl also eine ungerade Anzahl Nullen enthalten um insgesamt gültig zu sein. 
		Die Anzahl aller ungültigen PW der Länge $a_{n-1}$ erhalten wir, indem wir alle  gültigen PW der Länge $n-1$ allen möglichen PW der Länge $n-1$ abziehen. (#Alle PW: $10^{n-1}$, # GültigePWs $a_{n-1}$)
		=> $10^{n-1}-a_{n-1}$


![[Pasted image 20241229083431.png]]
=> Nun können wir diese Fälle addieren und enrhalten die Rekursionsbeziehung:
$a_{n}=9a_{n-1}+10^{n-1}-a_{n-1}=8a_{n-1}+10^{n-1}$

>[!Theorem]
>Falls man $k+1$ Objekte auf $k$-Schubfächer verteilen muss, dann gibt es mindestens ein Schubafch mit mehr als einem Objekt.

**Beispiel 1**
In einem Raum mit $367$ Personen gibt es mindestens zwei mit demselben Geburtstag; weil es ja nur 366 Mögliche Geburtstage gibt.

**Beispiel 2**
Zeige, dass es für jede natürliche Zahl $n$ ein Vielfaches $(n*k, k\in\mathbb{N})$ gibt welches in der Dezimalschreibweise lediglich Einsen und Nullen enthält.

$n=3$
$$
\begin{align}
1*1 &=1 \\
2*5 &= 10 \\
3*37 &= 111
\end{align}
$$
Sei $n$ beliebig:
$$
\begin{align}
1&=a_{1} &a_{1} \text{ mod } n = r_{1} \\
11&=a_{2} &a_{2}\text{ mod } n =r_{2} \\
111&=a_{3} &a_{3}\text{ mod } n =r_{3} \\
1111&=a_{4} &a_{4}\text{ mod } n =r_{4} \\
1111\dots&=a_{n+1} &a_{n+1}\text{ mod } n =r_{n+1}
\end{align}
$$

# Erweitertes Schubfachprinzip
>[!Theorem]
>Falls man $N$ Objekte auf $k$ Schubfächer aufteilt, dann gibt es mindestens ein Schubfach mit $\left\lceil  \frac{N}{k}  \right\rceil$ Objekte.

## Beispiel
Wie gross ist die Mindestzahl $N$ von Studierenden in DMATH, damit mit absoluter Sicherheit mindestens 5 Studienende dieselbe Note ($A, B, C, D, E ,F$) erhalten?
$$
\begin{align}
5 &= \left\lceil  \frac{N}{6}  \right\rceil  \\
4&< \frac{N}{6} \\
4*6 &< N \\
N&=25
\end{align}
$$

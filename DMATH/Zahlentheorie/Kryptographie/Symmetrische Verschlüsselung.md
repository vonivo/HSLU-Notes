>[!Definition]
>Ein symmetrischer Verschlüsselungsalgorithmus besteht aus.
>1. Einer (Verschlüsselungs-) Funktion $f$ mit zwei Variablen.
>2. Dem **Schlüssel** $k$ (mit $k\in K$ der [[Menge]] aller Schlüssel).
>3. Dem **Klartext** $m$ (mit $m\in M$ der Menge aller möglichen Klartexte).
>4. Dem Geheimtext $c$ (mit $c\in C$ der Menge aller möglichen Geheimtexte), der sich wie folgt ergibt:
>$$
>c=f(k,m)
>$$
>Die (Verschlüsselungs-) Funktion $f$ **muss umkehrbar sein**, d.h. es eine (Entschlüsselungs-Funktion) $f^{*}$ geben, die die Wirkung von $f$ neutralisiert.
>Es gilt:
>$$
>m=f^{*}(k,c)=f^{*}(k,f(k,m))
>$$

Dass heisst:
1. Für jeden (fest gewählten) Schlüssel $k$ müssen die Funktionen
$$
m\mapsto c=f(k,m), \text{ und } c\mapsto m=f^{*}(k,c)
$$
	[[Injektive Funktionen|injektiv]] sein.
2. Zuerst verschlüsseln und danach wider entschlüsseln ergibt wieder den Klartext:
$$
f^{*}(k,f(k,m))=m
$$



**Beispiele**
- [[Skytale]]
- [[Caesar Cipher]]
- [[Schlüsselwortchiffre]]
- [[Vignenère Cipher]]

Nach dem [[Fundamentalsatz der Differential- und Integralrechnung]] folgt aus der [[Produktregel]] der Differenzialrechnung
$$
\frac{d}{dx}[u(x)*v(x)] = u'(x)v(x)+u(x)v'(x)
$$
durch Integration beider Seiten
$$
u(x)\cdot v(x)=\int u'(x)\cdot v(x) \, dx + \int u(x)\cdot v'(x) \, dx 
$$
man hat also
$$
\int u'(x)\cdot v(x) \, dx = u(x) \cdot v(x)-\int u(x)\cdot v'(x) \, dx 
$$
Ziel: Das Integral auf der rechten Seite ist einfach als das auf der linken Seite.

>[!info]
>Es gilt:
>$$
>\int u'(x)\cdot v(x)=u(x)\cdot v(x) - \int u(x)\cdot v'(x) \, dx  \, dx 
>$$
>Vorgehen:
>1. Zerlege den Integranden in ein Produkt von zwei Faktoren
>2. Ein Faktor ist $u'(x)$, der andere ist $v(x)$
>3. Der erste Faktor $u'(x)$ kommt auf der rechten Seite überall in integrierter Form, d. h. als $u(x)$ vor.
>4. Der zweite Faktor $v'(x)$ kommt auf der rechten Seite nur unter dem Integral in abgeleiteter From, d. h. als $v'(x)$ vor.

## Vorgehen für [[Unbestimmtes Integral|unbestimmte Integrale]]
![[Partielle_Integration 1.png]]
1. Faktoren Festlegen
$$
\begin{align}
u(x)&=x \\
v'(x) &= e^{ x }
\end{align}
$$
2. Ableiten/Integrieren und in Tabelle schreiben:

| $u(x)$=x | $v(x)=e^{ x }$ |
| --- | --- |
| $u'(x)=1$ | $v'(x)=e^{ x }$ |
3. Anhand obiger Grafik das integral zusammenstellen
$$
\begin{align}
\int xe^{ x } \, dx &= xe^{ x }-\int 1\cdot e^{ x } \, dx   \\
&=xe^x-e^x +C \\
&=e^{ x }(x-1) +C
\end{align}
$$

## Vorgehen für [[Bestimmtes Integral|bestimmte Integrale]]
>[!info]
>Es gilt:
>$$
>\int _{a}^{b}u'(x)\cdot v'(x) \, dx = [u'(x) \cdot v(x)]_{a}^{b}-\int _{a}^{b}u(x) \cdot v'(x) \, dx  
>$$
>Das Vorgehen ist ähnlich wie bei unbestimmten Integralen, zusätzlich kommt bei bestimmten Integralen die obere und untere Integrationsgrenze mit ins Spiel.

Berechne $I = \int _{0}^{R}xe^{ -x } \, dx$

| $u(x) =x$ | $v(x)=-e^{ -x }$ |
| ---- | ---- |
| $u'(x)=1$ | $v'(x)=e^{ -x }$ |
$$
\begin{align}
\int _{0}^{R}xe^{ -x } \, dx &= \left[-x e^{ -x }\right]_{0}^{R}-\int_{0}^{R} 1 \cdot -e^{ -x } \, dx  \\
&= -Re^{ -R }-0e^{ -x }-[(e^{ -x })]_{0}^{R} \\
&= -Re^{ -R }-0e^{ -x }-[e^{ -xR }-e^{ -0 }] \\
&= -Re^{ -R }-e^{ -x R }+1
\end{align}
$$
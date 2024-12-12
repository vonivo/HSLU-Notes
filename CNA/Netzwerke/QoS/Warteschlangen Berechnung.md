Mit dem KEWarteschlangenmodell können die Netzwerk-Kanalkapazität als Entscheidungsgrundlage genutzt werden um ein Modell zu berechnen.

Damit lässt sich die erwartete Verarbeitungszeit des Servers/Routers berechnen.

- Mittlere Ankunfts-/Anfragerate: $\pi\frac{Pakete}{s}$
- Mittlere Verarbeitungsrate: $\mu\frac{\text{Pakete}}{s}$

$$
\begin{align}
\text{Zeit}&=\frac{1}{\mu}\times \frac{1}{1- \frac{\pi}{\mu}} \\
&= \frac{1}{\mu} \times \frac{1}{1-\rho}
\end{align}
$$
=> $\rho = \frac{\pi}{\mu}$

Wenn:
- $\pi<\mu$ ist der Normalfall, $T = \text{realistisch}$.
- $\pi=\mu$ dann $T = \infty \implies$ Überlauf
- $\pi>\mu$ dann $T = \text{negativ} \implies$ Überlauf

Können zwei Personen A und B ein Geheimnis (z.B. einen Schlüssel) vereinbaren, obwohl jemand ihre Kommunikation vollständig überwacht? Falls es Einwegfunktionen gibt, geht das!
**Diffie-Hellman Schlüsselvereinbarung**

1. Wähle zwei (allg. bekannte) natürliche Zahlen $p$ ([[Primzahl]]) und $g<p$ ([[Primitive Elemente|erzeugende]] von $\mathbb{Z}_{p}^{*}$)
2. A wählt eine (nur ihr bekannte) Zufallszahl $a <p$, berechnet $\alpha=g^{a}\text{ mod }p$ und sendet diese an B
	B wählt eine (nur ihr bekannte) Zufallszahl $b <p$, berechnet $\beta=g^{b}\text{ mod }p$ und sendet diese an A.
3. A berechnet $\beta^{a}\text{ mod }p$ ($=g^{a\cdot b}\text{ mod }p$) und B berechnet $\alpha^{b}\text{ mod p}$ ($g^{b\cdot a}\text{ mod }p$).
4. Beide haben den gemeinsamen Schlüssel $\beta^{a} \text{ mod } p = α^{b} \text{ mod } p$ und ein Angreifer kann aus der Kenntnis von $\alpha$ und $\beta$ (sowie natürlich $p$ und $g$) den Schlüssel $K$ praktisch (wegen des [[Diskrether Logarithmus|diskreten Logarithmusproblem]]) nicht rekonstruieren.
![[Pasted image 20241230133541.png]]
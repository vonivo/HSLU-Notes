Basieren auf [[Graph]] $G =(V,E)$ und Flüssen auf den Bogen des Graphen.

## Beispiel Transshipment
- 2 Fabriken (1 und 2) haben eine Produktionskapazität von 50 t und 60 t pro Woche einer spezifischen Ware
- 2 Kunden (3 und 4) haben einen Bedarf von 40 t und 70 t (pro Woche)
- Das Transportnetz mit 2 Transitpunkte (5 und 6)
![[Transshipment.png]]
**Problem**
Bestimme einen Transportplan, so dass die Transportkosten minimal sind.

**Graph**
- $V=\{ 1,2,\dots,6 \}$
- $E=\{ (1,3),(1,6),(2,4),(2,5),(3,4),(3,6),(5,1),(5,3),(6,2),(6,4) \}$
- Ein Transportplan: $x_{i,j}$, $(i,j)\in E$

Jedes Zulässige Modell muss folgende Bedingungen erfüllen:
- **Produktions-Standort**: $\text{heraus}-\text{herein}\leq \text{Angebot}$
- **Verbraucher**: $\text{herein}-\text{heraus} \geq \text{Verbrauch}$
- **Transit:** $\text{heraus}-\text{herein}=0$

## Modell
Minimiere $\sum_{(i,j)\in E}k_{i,j}x_{i,t}$ unter den Bedingungen
$$
\begin{align}
x_{1,3} + x_{1,6}-x_{1,5} & \leq 50 \\
x_{2,4}+x_{2,5}-x_{2,6} & \leq 60 \\
x_{1,3} + x_{5,3} - x_{3,4}-x_{3,6}  & \geq 40 \\
x_{2,4}+x_{3,4}+x_{6,4}  &\geq 70 \\
x_{5,1}+x_{5,3} - x_{2,5} &= 0 \\
x_{6,2} + x_{6,4} - x_{1,6} - x_{3,6} &= 0
\end{align}
$$

## Eigenschaften
- Lineare Optimierungsmodelle mit sehr spezieller Struktur
- Folgen:
	- "Natürliche Ganzzahligkeitseigenschaft" . Falls Daten ganzzahlig, (extremale) Optimallösung ganzzahlig
	- Hocheffiziente Lösungsmethoden (z.B. speziell zugeschnittener [[Simplex]]-Algorithmus)
- Unterschiedliche Anwendungen, insb. in Entwurf und Betrieb von logistischen oder technischen Netzen

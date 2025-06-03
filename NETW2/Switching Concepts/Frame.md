
![[EthernetFrame.png]]
**Preamble**
- Muster auf das synchronisiert wird.
- Beginnt mit `1010`
- Endet mit `11`

**Type**
Das Type Fled kann je nach Protokoll den Type des Protokolls oder die Framelänge darstellen.,

Bei dem **Ethernet II** Protokoll ist das Feld die **Length**.
Und beim **CMSA/CD Eth 802.3** ist das Feld den **Type**.

**Entscheidungsregel**:
$$
\begin{align}
\text{Wert} \leq 1500 \implies \text{Länge } \to \text{IEE 802.3}\\
\text{Wert} \geq 1536 \implies \text{Type } \to \text{Ethernet II}
\end{align}
$$

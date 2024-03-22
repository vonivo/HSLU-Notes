# Exzesscode
Ein Exzesscode ist eine Zahl mit einem Versatz/Offset.
Dabei wird der Zahl immer der Versatz addiert. Ein typischer Versatz wäre $2^{m-1}$ oder $2^{m-1}-1$.

Bei [[Gleitkommazahlen#IEEE 754|IEE 754]]: m=8, $2^{8-1}-1 = 127$.

Bei einer 8-bit Zahl mit einem Versatz von 127 kann ein Zahlenbereich von **-127** bis **128** dargestellt werden.
![[Exzesscode.png]]
### Beispiel
Die Zahl -32 würde im Exzesscode so geschrieben werden:
$$
-32 + 127 = 95
$$
**95** in Binär ist: 0101 1111

# Vorzeichen
Bei dieser Variante ist immer das höchstwertige Bit das Vorzeichen. Dabei entspricht eine 1 einem Minus und eine 0 einem Plus.
Dadurch entstehen aber zwei Zahlen für Null: 1000'0000 und 0000'0000
### Beispiel
$$
\begin{align}
9 &= 0000'1001 \\
-9&=1000'1001
\end{align}
$$
# Einerkomplement
Beim Einerkomplement wir die Positive Zahl logisch negiert und das ergibt dann die Negative-Zahl. Auch hier wird eine Negative Zahl durch ein "führende" 1 gekennzeichnet.

Dadurch entstehen aber zwei Zahlen für Null: 1111'1111 und 0000'0000

### Beispiel
$$
\begin{align}
8 &= 0000'1000 \\
-8&= 1111'0111
\end{align}
$$
# Zweierkomplement
Das Zweierkomplement funktioniert gleich wie das Einerkomplement, nur wird die Zahl invertiert und dann um eins erhöht.

Dadurch existiert nur noch eine Zahl für 0: 0000'0000
$$
\begin{align}
8 &= 0000'1000 \\
\text{Invertieren:} \\
&= 1111'0111 \\
\text{Um eins erhöhen} \\
&=1111'1000
\end{align}
$$

# Vor- und Nachteile
## 1er-Komplement
### Nachteile
- Übertrag muss in zusätzlichem Schritt addiert werden
- 2 Darstellungen für Null
### Vorteile
- Schneller bei Division und Multiplikation mit doppelt langem Ergebnis
- Einfachere Bildung

## 2er-Komplement
### Nachteile
- Bildung etwas komplexer
### Vorteile
- Nur eine Darstellung für Null -> Wertebereich um 1 grösser
- Addition des Übertrags entfällt
Angenommen, wir testen drei verschiedene Schlagzeilen A, B und C und führen sie jeweils mit 1.000 Besuchern durch. Die Ergebnisse sind in folgender Tabelle dargestellt.

$$
\begin{array}{c|ccc}
& \textbf{Schlagzeile A} & \textbf{Schlagzeile B} & \textbf{Schlagzeile C} \\ \hline
\textbf{Klick} & 14 & 8 & 12\\
\textbf{kein Klick} & 986 & 992 & 988\\ 
\end{array}
$$
**Chi-Quadrat-Test** prüft, ob **beobachtete Daten** einer **erwarteten Verteilung** entsprechen.

**Ablauf**:
1. Erwartete Verteilung berechnen
$$
\begin{align}
\text{Klick}&=\frac{14+18+12}{1000+1000+1000}&=\frac{34}{3000} \\
\text{kein Klick}&= 1-\frac{14+18+12}{1000+1000+1000}&=\frac{2966}{3000}
\end{align}
$$

2. **Quadratische Pearson-Residuum** berechnen:
$$
R^{2} = \frac{(\text{beobachtete Häufigkeit} - \text{erwartete Häufigkeit})^{2}}{\text{erwartete Häufigkeit}}
$$
3. **Chi-Quadrat-Metrik $\chi^{2}$** berechnen:
$$
\pmb{\chi^2} = 
\pmb{R}_{\text{\small A,Klick}}^2 + \pmb{R}_{\text{\small A,kein Klick}}^2 + \pmb{R}_{\text{\small B,Klick}}^2 + \pmb{R}_{\text{\small B,kein Klick}}^2 + \pmb{R}_{\text{\small C,Klick}}^2 + \pmb{R}_{\text{\small C,kein Klick}}^2
$$

4. Wiederhole 1000 Mal die Schritte 2 und 3
5. Wie oft ist die **Summe der quadrierten Pearson-Residuen** grösser als die beobachtete? Das ist der [[ASTAT/Testverfahren/p-Wert]]

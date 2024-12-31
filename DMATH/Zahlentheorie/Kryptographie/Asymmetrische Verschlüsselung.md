- Jedem Teilnehmer $T$ wird ein privater Schlüssel $d=d_{T}$ (geheim) zum Entschlüsseln und ein öffentlicher Schlüssel $e=e_{T}$ zum Verschlüssel zugeordnet.
- Der Verschlüsselungsalgorithmus $f_{e}$ zum öffentlichen Schlüsse $e$ ordnet jedem Klartext $m$ den Geheimtext $c=f_{e}(m)$ zu. Jeder kann also verschlössen.
- Umgekehrt ordnet $f_{d}$ jedem Geheimtext $c$ den Klartext $m$ zu. Nur wer den zugehörigen privaten Schlüssel hat, kann also entschlüsseln.

**Bedingung:**
1. Korrekte Entschlüsselung: $m'=f_{d}(c)=f_{d}(f_{e}(m))=m$.
2. Public-Key-Eigenschaft: Es ist **praktisch unmöglich** aus der Kenntnis von $e$ auf $d$ zu schliessen.

## Ablauf
1. Ermitteln des öffentlichen Schlüssels $e=e_{T}$ von $T$.
2. Die Funktion $f_{e}$ auf die Klartextnachricht $m$ angwenden
3. $c$ wird an $T$ gesendent.
4. Nur $T$ kann nun $c$ mittels $d$ und $f_{d}$ entschlüsseln: $f_{d}(c)=m$

NTP wurde 1982 unter der Leitung von David Mills entwickelt und befindet sich seit 1994 in der Version 4.

**Eingenschaften**
- NTP-Daemon auf fast allen Rechnerplattformen verfügbar. (PC bis Crays).
- Erreichbare Genauigkeit von ca 10ms in WANs und $>1$ ms in LANs.
- Fehlertolerant


**Struktur**
- *Stratum 1:* primärer Zeitgeber, über Funk oder Standleitungen an amtliche Zeitstandards angebunden
- *Stratum > 1:* synchronisiert mit Zeitgeber des Stratums $N -1$ 
- Stratum kann dynamisch wechseln

![[NTP.png]]
**Struktur**
![[NTP2.png]]

## Ablauf
+ Client sendet NPT-Message an Server.
+ Server verarbeitet Paket
+ Server sendet Paket zurück
+ Client hat nun vier Timestamps ($t_1 - t_4$) und leitet davon Offset unt Delay ab:

| Client        | Connection | Server        |
| ------------- | ---------- | ------------- |
| Zeitstempel 1 | ---->      | Zeitstempel 2 |
| Zeitstempel 3 | <--------  | Zeitstempel 4 |
$$
\begin{align}
\text{Offset} &= \frac{(t_2 - t_1) + (t_3 - t_4)}{2} \\
\text{Delay} &= (t_4 - t_1) - (t_2 - t_3)
\end{align}
$$
**Offset:** Zeitdifferenz der Rechenuhren (gemittelt) -> Ändern um diesen Wert
**Delay:** Zeit während der das Paket unterwegs war -> Paket mit geringstem Delay nutzen
**Zeitserver**: Maschine mit Zeitzeichenempfänger[^1], synchronisiert alle anderen Maschinen.
**UTC**: Universal Coordinated Time: Zeitmessung in Beziehung mit dem Sonnenstand mit Schaltsekunden

**Ablauf**
+ Client `P` erfragt Zeit von Server `S` zum Zeitpunkt $t_0$
+ Die Anfrage wird von `S` bearbeitet innerhalb der Zeitspanne $I$
+ Die Antwort $C_\text{UTC} (t_0)$ wird von `P` zum Zeitpunkt $t_1$ empfangen
+ `P` wird auf die Zeit $C_\text{UTC} (t_0) + \frac{\text{RTT}}{2}$ gesetzt, d.h. die vom Server
  gemeldete Zeit plus die Rücklaufzeit des Pakets.
  - die Round Trip Time (RTT) wird dabei berechnet durch $\text{RTT}=t_1 - t_0$.
  - ist die Zeitspanne $I$ bekannt, kann die Berechnung verbessert werden:
    $\text{RTT} = t_1 - t_0 - I$
+ Für genauere Werte wird die Laufzeit öfters gemessen, Messungen ausserhalb
  eines Bereiches werden verworfen und eine Mitteilung der restlichen Werte
  durchgeführt.
![[AlgorithmusVonCirstian.png]]


**Probleme**
- Zeit vom Zeitserver liegt in der Vergangenheit der lokalen Zeit 
	-> Zeit kann nicht zurückgedreht werden, da inkonsistente Zustände\
	=> Lösung: Verlangsamung der lokalen Zeit, bis Zeitdifferenz ausgeglichen
- Laufzeit der Anfrage kann nicht genau bestimmt werden, abhängig von Netzwerklast
	=> Kompensation durch mehrfache Messungen der Dauer der Anfrage und Adaption des vom Zeitserver gelieferten Werts



[^1]: z.B. Langwellensender DCF77 https://de.wikipedia.org/wiki/DCF77

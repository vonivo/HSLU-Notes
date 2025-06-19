Wie erfolgt automatischer Wechsel auf ein [[VSK/Konsitenz und Replikation/Replikation|Replikat]], sobald Primary ausfällt?

**Teilfragen:**
- Wie erkenne [[VSK/Konsitenz und Replikation/Replikation|Replikate]] zuverlässig, dass der Primary ausgefallen ist?
	- [[Heartbeat-Protokolle]]
- Wie ernenne die [[VSK/Konsitenz und Replikation/Replikation|Replikate]] einen neuen Priamry, falls mehrere Repliakte existieren?
	- [[Leader-Election-Protokolle]]
- Wie wissen Clients auf wwelches System sie verbinden müssen?
	- Namesdienste / IP-Routing

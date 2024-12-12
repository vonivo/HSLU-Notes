Als Interprocess Communication (IPC) bezeichnet man die Kommunikation zwischen Prozessen.

Das Ziel ist ein strukturierter und konfliktfreier Ablauf von Prozessen. Das wird durch **Prozesssynchronisation** bewerkstelligt. 

- Wie kommunizieren [[Prozesse]]?
	- [[Message Passing]]
- Wie verhindert man [[Deadlocks]] oder Konflikte zwischen Prozessen?
	- Es werden kritische Regionen definiert, nur ein Prozess darf sich zur gleichen Zeit in einer kritischen Region befinden.
	- Es dürfen keine Annahmen über Geschwindigkeit und [[Prozessor|CPU]] Anzahl gemacht werden
		- Wenn die nötige Hardware nicht gegeben währe welche man annimmt, geht man ein grosses Konfliktrisiko ein
	- Ausserhalb einer kritische Region darf ein Prozess einen anderen Prozess nicht blockieren
	- Kein Prozess soll ewig warten müssen bis er Zugriff auf einen Kritischen Bereich hat
	- Verhindern kann man es mit Kontrollelementen:
		- [[Semaphor]]
		- [[Mutex]]
		- [[Monitor]]
-  Wie kann man [[Prozesse]] abarbeiten unter Berücksichtigung ihrer Abhängigkeiten?

> Kritische Regionen sind Abschnitte in denen auf gemeinsame Ressourcen (Datenbanken, [[Speicher]]) zugegriffen wird


# IPC Probleme
[[Produzenten-Konsumenten-Propblem(PCP)]]
[[Dining Philosophers]]
[[Readers and Writers]]
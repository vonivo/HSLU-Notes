Um mit I/O Geräte arbeiten zu können braucht die [[Prozessor|CPU]] verschiedene Register in die sie Daten schreiben und lesen kann. Wie diese Register integriert werden nennt man I/O Mapping. 

Dabei gibt es drei Herangehensweisen: 
![[Pasted image 20240526155551.png]]

- a) Seperater I/O und Memory Space
	- Memory und I/O werden vollständig getrennt, nur das [[Betriebssysteme|Betriebssystem]] (keine User Programme) hat Zugriff auf  auf den I/O Port Space
- b) Memory-mapped I/O
	- Die I/O Adressen werden vollständig in das Memory integriert
- c) Hybrid
	- Es gibt sowohl I/O Mapped Control Register als auch Memory Mapped I/O
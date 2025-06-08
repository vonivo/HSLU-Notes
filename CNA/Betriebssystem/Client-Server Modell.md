Ein Client Server Modell ist ein [[Verteilte Systeme| verteiltes System]] bestehen aus folgenden [[Rechner|Rechnern]]:
- Client → Nimmt Dienste in Anspruch
- Server → bietet Dienstleistung an

# Zwei Stufenarchitektur
Das nennt man auch ein zwei Stufensystem:
![[Pasted image 20240530113449.png]]

Dabei kann die Aufteilung ziemlich beliebig sein. Der Client kann sowohl die Benutzeroberfläche, Teile der Applikation und der Datenbank betreiben, während der Server nur noch einen anderen Datenbankteil übernimmt. Ebenso kann der Server ein Teil der Benutzeroberfläche, die Applikation und die Datenbank betrieben, während der Client nur noch als Benutzeroberfläche dient. 
![[Pasted image 20240530113533.png]]

# Drei Stufen Architektur
Bei der drei Stufen Architektur wird das System in drei [[Rechner]] aufgeteilt
Dabei übernimmt der Client die Benutzeroberfläche, ein Applikationsserver die Applikation und ein Datenbankserver die Datenbank.
![[Pasted image 20240530113855.png]]

## Beispiel
![[Pasted image 20240530114002.png]]

# Kommunikation
Die Kommunikation kann dabei über [[Socket|Sockets]] und [[CNA/Netzwerke/RPC]] erfolgen
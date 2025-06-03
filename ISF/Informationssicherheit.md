>[!Info]
>Die Informationssicherheit umfasst den **Schutz der Informationen** als solche unabhängig vom Medium. (Elektronische Datenträger, Papier, Wissen in den Köpfen der Mitarbeiter)

Bei der Informationssicherheit wird der Schutz von [[Daten, Informationen und Wissen#Informationen|Informationen]] ohen IKT-Mittel sichergestellt.

Die Informationssicherheit befasst sich mit dem Schutz **aller** [[Daten, Informationen und Wissen|Daten]] und [[Daten, Informationen und Wissen|Informationen]].
Ziel der Informationssicherheit ist es, mögliche [[Bedrohungen]] und [[Schwachstellen]] zu identifizieren, um aus der Bewertung durch entsprechende Massnahmen die Auswirkung und die Eintrittswahrscheinlichkeit zu minimieren.
![[Pasted image 20241124151432.png]]

## Grundschutzziele
Die Grundschutzziele werden mit **C-I-A** beschrieben:
- Confidentiality -> Vertraulichkeit
	[[Daten, Informationen und Wissen|Informationen]] können nicht von unautorisierten Personen, Instanzen oder Prozessen eingesehen werden.
	**Bell-LaPadula Prinzip**
	![[Pasted image 20250123100831.png]]
	-> no-read-up
	-> no write down
- Integrity -> Integrität
	[[Daten, Informationen und Wissen|Daten]] oder Systeme können nicht unautorisiert oder zufällig manipuliert oder verändert werden.
	**Technische Massnahmen**
	- HMC: AES
	- Digitale Signaturen
	- Biba-Prinzip
	![[Pasted image 20250123101022.png]]
	-> No-Write-UP
	-> No-Read-Down
![[Pasted image 20250123101237.png]]
	**Organisatorische Massnahmen**
	- PKI
	- Blockchain
- Availability -> Verfügbarkeit
	Der Benutzer kann jederzeit auf Dienste oder [[Daten, Informationen und Wissen|Informationen]] zugreiffen.
	![[Pasted image 20250123101253.png]]

Alle Sicherheitsbetrachtungen müssen sich **mindestens** auf diese 3 Schutzziele beziehen


## Weitere Schutzziele
- Privacy
- Anonymity
- Pesudonynimty
- Resilience
- Authority
- Authenticity
- Verbindlichkeit
- Kopierschutz
- Zutrittskontrolle -> Schutz des physischen Systems
- Zugangskontrolle -> Schutz des logischen Systems
- Zugriffskontrolle Schutzer der Operationen

## Schritte der Informationssicherheit
1. Sichern (Backups)
2. Schützen (DMZ, Firewall, Paketfilter, etc.)
3. Überwachen (Virenscanner, IDS, IPS, WAF)
4. Vorbeugen (Softwareupdates)
	1. Forensic Readyness
		1. Stragety
		2. Policy and Procedures
		3. Technology
		4. Digital Forensic Response
		5. Compliance and Monitoring
5. Aufpassen (Persönliches Verhalten)

## Weitere Sicherheitsziele
- Authentizität
- Autorisierung
- Zugriffskontrolle
- Zugreifbarkeit
- Zuverlässigkeit
- Verbindlichkeit
- Unbeobachtbarkeit
- Wirksamkeit, Effektivität
- Kopierschutz
Die einfachste Weise um auf ein Cisco Gerät zuzugreiffen ist via SSH.
Bei SSH werden die Credentials standardmässig lokal auf dem Gerät gespeichert, was mehr Konfigurationsaufwand generiert.

### AAA-Konzept
AAA steht für Authentication, Authorization und Account und das geläufige Tool umd Access-Control für ein Netzwerkgerät einzrichten.

Mit AAA kann kontrolliert werden wer Zugang zum Netzwerk bekommt, wass diese dort machen können und audit-actions durchführen.

## Authentication
Es gibt zwei Methoden Authentication zu implementiere, lokal oder server-basiert.

**Lokal**
- Speicher von Zugangsdaten direkt auf dem Gerät.
- User authentisiert sich gegen die lokale Datenbank
- Ideal für kleine Netzwerke

**Server-Based**
- Das Netzwerkgerät greift auf einen zentralen AAA-Server zu.
- AAA-Server beinhaltet Login-Datenbank.
- Router verwendet RADIUS (Remote Authentication Dial-In User Service) oder TACACS+ (Termianl Access Controller Access Control System) um sich mit dem Server zu verbinden.
- für grosse Netzwerke.

## Authorization
Eine AAA-Authroization geschieht automatisch nach dem Login und der Benutzer muss nichts zusätzliches mehr machen.

Mit Authorisation wird konfiguriert, was ein Benutzer auf dem Netzwerk alles darf, indem es ein Set von Attributen benutzt, welche den Zugang des Benutzers zum Netzwerk beschreiben. Diese Attribute nutzt der AAA-Server um die Berechtigungen zu bestimmen.

## Accounting
- AAA Server speichert detailiertes Log (alle EXEC und Configuration Commands werden gespeichert)
- Log enthält username, datum und zeit + command

## 802.1X
Der 802.1X IEEE-Standard beschreibt die port-basierte Access Controll und Authentication-Protokoll.

Das Protokoll verhindert, dass unautorisierte Endgeräte sich mit einem LAN über öffentliche Switchports verbinden.

Jedes Endgerät wird über einen AAA-Server authentifiziert, bevor es Zugang zum Netzwerk erhält.

Rollen:
- Client (Supplicant)
- Switch (Authenticator), verbindet Client und Server 
	- leitet Authentifizierungsinformationen weiter
	- blockiert access für nicht authentifizierte Geräte
- Authentication Server
	- Validiert Client Credentials und leitet Ergebnis an Switch weiter
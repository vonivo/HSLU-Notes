**Authentisieren:**
Eine Partei `P` weist sich gegenüber einen System `S` mittels eines Geheimnisses aus:
- I.d.R mittels Kenntnis einer Information, einem Zugang, oder einem Besitz, welche nur Parte `P` hat (Passwort, Token, Smartcard, etc.)

**Authentifizieren:**
System `S` prüft, ob Partei `P` diejenige ist, welche sie vorgibt zu sein, indem das Geheimnis überprüft wird.

**Autorisierung**
Überprüfen, ob eine authentifizierte Partei berechtigt ist, auf eine Ressource zuzugreifen.

Authentifiziert wird in der Regel eine [[Session]] welche für eine Partei `P` steht.
Ist die Authentifizierung erfolgreich, wird die Session meist mit einem Benutzer verknüpft.
```java
void login(Message message) {
	String account = message.getAccount();
	String password = message.getPassword();
	PasswordRecord record = PasswordManager.getAccount(account);

	if (record.matches(password)) {
		session.setAccount(account);
	}
```


## Autorisierung
Nach der Verknüpfung mit Konto ist eine Session autorisiert auf bestimmte Ressourcen oder Funktionalitäten zuzugreifen.

```java
if (session.hasRole("logger")) {
	while (true) {
		LogMessage msg = receiveLogMsg();
	}
}
```

**Role based Access Control**
Definition von Rollen und prüfen ob Benutzersession für die benötigte Aktion die Rolle hat.

**Row Level Security**
Funktionalität von Datebanken.
Definition pro Ressource (oft in Table-Row gespeichert), wer daraf zugrefien kann.
(siehe [[Access Control Lists]]).
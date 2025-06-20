>[!Definition]
>Zeitlich beschränkte Zweiwege-Kommunikation (Anmelden bis Abmelden).
>Typischerweise zwischen Client und Server [[Request-Reply]].

## Session-Secret
Ein Session-Secret ist ein grossen zufälliges Geheins zwischen dem Server und dem Client.

Das Secret wird bei der Anmeldung von Server generiert und dem Client mitgeteilt. Der Client sendet dann dieses Secret bei jedem Request mit.

### Varianten
- **Zufällig**
	- Zufallsgenerator muss kryptografisch sicher sein.
	- Typische Grösse $16$ bytes.
	- Server speichert Informationen, welche zur Session gehören.
	- Bsp. Session-Cookie
```java
private byte[] generateSessionKey() {
	SecureRandom secureRandom = new SecureRandom();
	byte[] sessionKey = new byte[16];
	secureRandom.nextBytes(sessionKey); // may block
	return sessionKey;
}
```

- Verschlüsselte statische Informationen (Access-Token)
	- Public/Private-key Verfahren.
		- [[Digitale Signatur]]
	- Beispiel:
		- JWT. Dient als AccessToken (enthält, z.B. Verknüpfung zu Benutzerkonto), Besteht aus Header/Payload/Signatur



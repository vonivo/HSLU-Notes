Passwörter werden als Hash gespeichert.
- Klartext-Passwörter sind eine Gefahr für andere Systeme.
- Kryptografisch sicherer Hash verwenden.
- Teurer Hash verwenden

Hashalgorithmen:
- Scrypt
- Bcrypt
- PBKDF2

## Beispiel Hash

![[hash.png]]
- **Cost:** Anpassen der Kosten der Hashwertberechnung an aktuelle HW.
	- Kosten für ein Login sollten ca $100ms$ sein.
- **Salt:** Verhindert Rainbow-Tables mit Pre-Computed-hashes. (Gleich Passwörter bekommen unterschiedlichen Hash)
	- Zufällige Zahl welche mit dem Passwort-Hash gespeichert werden kann.
- **Pepper:**
	- Zusätzulich alle Passwörter mit weiteren (für alle PWs identisch) Zahl Z hashen. Diese Zahl Z wird abseits der PW-DB gespeichert.

## Implementierung
```java
private byte[] generateSalt() {
	SecureRandom random = new SecureRandom();
	byte[] salt = new byte[16];
	random.nextBytes(salt);
	return salt;
}

private static final int ITERATION_COUNT = 65536;
private static final int KEY_LENGTH = 512;
private static final String CRYPTO = "PBKDF2WithHmacSHA512";

public byte[] generateHash(String password, byte[] salt) {
	KeySpec spec = new PBEKeySpec(
	password.toCharArray(), salt, ITERATION_COUNT, KEY_LENGTH);
	SecretKeyFactory factory = SecretKeyFactory.getInstance(CYRPTO);
	return factory.generateSecret(spec).getEncoded();
}

public static class PasswordRecord {
	private final byte[] hash;
	private final byte[] salt;
	
	public PasswordRecord(byte[] hash, byte[] salt) {
		this.hash = hash;
		this.salt = salt;
	}

	public PasswordRecord create(String password) {
		byte[] salt = generateSalt();
		byte[] hash = generateHash(password, salt);
		return new PasswordRecord(hash, salt);
	}

	public boolean compare(String password, PasswordRecord record) {
		byte[] newPasswordHash = generateHash(password, record.salt);
		return Arrays.equals(newPasswordHash, record.hash);
	}
}
```


##### Direct Trust

- Persönliche Überprüfung vom Public Key
- Benötigt authentischen Kanal zum etablieren vom Trust
    - Vorsinstalliert auf Webseite installiert

##### Web of Trust

Alice vertraut indirekt Charlie weil Bob Charlie vertraut und Alice Bob vertraut Alice → Bob → Charlie

##### Hierarchical Trust (PKI)

PKI → Public Key Infrastructure System das digitale Zertifikate ausstellen, verteilen und prüfen kann

Certificate Authority: Zertifizierungsstelle

- Intermediate CA signiert Zertifikate (Public Key) von Endbenutzern
- Root CA signiert Zertifikat von Intermediate CA
- Root CA ist self-signed

Aufbau X.509 Zertifikat:
![[Pasted image 20241124161714.png]]
Verwendungszweck von Zertifikaten:

- Verschlüsselung
    - SSL/TLS-Verbindung
    - Email
- Signaturen
    - Email
    - Dokumente
    - Code
    - Zertifikate
- Authentisierung
    - SSL/TLS Verbindung
    - Identitätsnachweis
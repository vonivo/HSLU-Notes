>[!Definition]
>TLS bietet transparente Verschlüsselung der Anwendungskommunikation. Vom Konzept ist das Konzept auf der Transportschicht, implementiert ist es jedoch auf der Anwendungsschicht.


## Verbindungsaufbau
![[TLS.png]]
## X.509 Zertifikat
Mit TLS wird ebenfalls die Identität (**Authentifizierung**) der Gegenstelle ausgeführt.
Dies wird mittels `X.509`- Zertifikaten gemacht. (Verhindert [[MITM]]).

Ein `X.509`-Zertifikat:
- Bindet eine Identität mittels [[Digitale Signatur]] zu einem öffentlichen Schlüssel.
- Sind zertifiziert durch Zertifizierungsstelle oder selbstzertifiziert.
- bedingen Vertrauen in Zertifizierungsstelle.
- Sind unterteilt ind:
	- **Zertifizierungsstelle (CA)**: Kann weiter Zertifikate erteilen. Hierarchisch aufgebaut. Vertrauen in oberste CA benötigt.
	- **Endstelle**: Identifiziert eine Entität.

### Chain of Trust
Root-CAs stellen aus Sicherheitsgründen keine **Endstellen**-Zertifikate aus. Mehrere Schichten zwischen Root-CA und Endstelle erhöhen Sicherheit.

Wenn eine CA kompromittiert wird, werden alle von dieser CA ausgestellten Zertifikate ungültig.

Ein Server liefert immer sein eigenes Zertifikat inklusive der ganzen Zertifikats-Chain aus.

Der Client muss das Root-CA bei sich selbst gespeichert haben, wenn diese Matchen, vertraut er auch dem Server.

## Zertifiakt erstellen
1. Certificate Sign Request erstellen
	1. Erstellen eines Private-Key für den Server
		- Artefakte: `server.key`
	2. Konfiguration des CSR (Certificate Sign Request):
		- Artefakt: `csr.conf`
	3. Erstellung CSR:
		- Artefakt: `server.csr`
2. Zertifikat austellen:
	1. Senden von `server.csr` und weiteren Informationen an die Zertifizierungsstelle.
	2. Prüfen der Identität durch Zertifizierungsstelle
		- Artefakt: `server.crt`


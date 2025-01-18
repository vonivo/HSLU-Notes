Angreifer stehlen Schlüssel, Passwörter, Geschäftsgeheimnisse, Personendaten oder andere sensitive Daten vom Server, bei der Übertragung oder vom Client.

Viel passiert dabei auf der SSL/TLS Ebene des  [[OSI Referenzmodell|TCP-IP-Stack]].

Ein Beispiel dazu ist FTP. Bei FTP wird das Passwort im Klartext übertragen und jeder der mithört kennt danach das Passwort.

## Schutz
- Keine Daten speichern oder übertragen, welche nicht benötigt werden.
- Daten nach ihrer Sensitivität klassifizieren und entsprechend behandenl.
- Sensitive Daten nur verschlüsselt ablegen.
- Passwörter mit Salt und Pepper und einer starken Hashfunktion gehast ablegen.
- Daten verschlüsselt übertragen (FTP->SFTP, HTTP->HTTPS) Zertifikate prüfen
- Sichertellen, dass sichere Ciphers verwendent werden
- Keine sensitiven Daten auf der Clientseite cachen.
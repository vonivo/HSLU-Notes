Dadurch, dass Quantencomputer gewisse Probleme schneller lösen können hat das einen Einfluss auf Kryptologie.

## Immer noch sicher
- Verschlüsselung mit [[One Time Pad]] -> sicher. (Da [[Perfekte Sicherheit]])
## Geschwächt
- [[Secret Key Verschlüsselung]] (AES, DES, 3DES)
- "Message authentication" mit Hashfunktion: SHA, (MD5)
- Challenge-Response-Authentisierung mit Hashfunktionen.

## Gebrochen
- Verschlüsselung (Schlüsselaustausch) mit asymmetrischen Algorithmen ([[RSA]], [[Diffie-Hellman]], ECDH)
- Eletronische Signaturen: RSA, DSA
- Challenge-Response-Authentication mit Signaturen: RSA, DSA

# Post-Quanten-Kryptologie
Post-Quanten-Kryptologie beschreibt den Zweig der Kryptologie, welcher Sicherheit mit anderen mathematischen Problemen garantiert, welche von einem [[Quantencomputer]] nicht schneller gelöst werden können.

Das NIST hat dazu einen Wettberwerb ausgerufen, wer solche Kryptologie bezüglich Verschlüsselung/Schlüsselaustausch und Signaturen entwickelt.


# Quantenkryptographie
Die Quantenkryptographie selbst beschreibt Verschlüsselungsverfahren, welche sich selbst Eigenschaften von Quanten zunutze machen.

Dazu werden Polarisationsfilter verwendet. Immer wenn ein Teilchen mit einem Filter "gemessen wird" wird der Zustand davon verändert.

### Quantenschlüsselverteilung
![[Pasted image 20250118165137.png]]
1. Alice schickt Photonen mit zufälliger Polarisationsrichtung (-45, 0, 45, 90)
2. Bob misst mit einem Filter, zufällig entweder 0 oder 45 gedreht.
3. Über einen klassischen Authentischen Kananl
	1. Werte bei denen die Richtung nicht übereinstimmt werden gelöscht.
	2. Von einem Datensampel wird geprüft, ob ein Angreifer präsent war -> abort
	3. Von den restlichen Werten wird ein Schlüssel erzeugt.
![[Pasted image 20250118165410.png]]

Was braucht Quantenkryptografie?
- Direkter Kommunikationskanal (Glasfaser)
- Laser
- Beamsplitter
- Photondetektor für einzelne Photonen

Was ist nicht notwendig?
- Quantencomputer
- Quantenmemory
- Komplizierte Interaktionen zwischen Teilchen

Voraussetzungen:
- Authentisierung -> initialer kurzer Schlüssel oder klassisches Authentisierungsprotokoll
- Lokale Zufallszahlen -> Quantenzufallsgenerator
- Information leakage -> sichere Integration
- Präzise Geräte -> Post-processing
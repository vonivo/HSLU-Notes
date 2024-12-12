Basiert auf Funktionen die einfach zu berechnen sind, aber die Umkehrfunktion schwierig ist

Beispiele:

- RSA (Faktorisieren grosser Zahlen)
- Diffie-Hellman (Diskrete Logarithmen)
- Elliptic Curve DH (Diskrete Logarithmen)
- ElGamal Verschlüsselung (Diskrete Logarithmen)

P vs NP:

- Einfach zu prüfen aber schwierig herauszufinden

Schwachstelle: Verwendung schwacher kryptographischer Funktionen

- Verwendung von Funktionen welche gebrochen oder nicht sicher sind
    - Beispiel: kurzer Schlüssel, unsichere Zufallszahlen
    - Verhinden: Sichere Funktionen einsetzen (nicht selbst implementieren)

#### Signaturen

Eigenschaften:

1. Fälschungssicherheit
2. Authentizität
3. Unleugbarkeit
4. Willenserklären

Verwenden oft die gleichen Algorithmen Public Key Verschlüsselung

Beispiele:

- RSA
- Digital Signature Algorithm
- Elliptic DSA
- ElGamal Signature

Signatur von Dokumenten (Hash-then-sign):

- Zuerst Hashen und dann Hashwert signieren weil schneller
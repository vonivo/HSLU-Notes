Die Symmetrische Verschlüsselung beschreibt die Verschlüsselung von einem Text, bei dem der Text mit demselben Schlüssel entschlüsselt wird, wie er verschlüsselt wurde.

![[SymmetrischeVerschlüsselung.png]]

# Verschlüsselungsverfahren
- Data Encryption Standard (DES)
	- Von IBM entwickelt.
	- Durchläuft 16 Transpositions- und Substitutions-Zyklen.
	- Schlüssellänge 56 Bit, 199 innerhalb 24h gebrochen.
- Triple DES
	- Dreifacher DES
- RC5 ( Rivest Cipher) von RSA
	- Symmetrische Blockchiffre von 1994.
	- Variable Blockgrösse und Schlüssellänge.
- AES (Advanced Encryption Standard)
	- Im Jahr 200 erfunden von NIST (National Institute of Standars and Technology)
	- 128-Bit Schlüssellänge und **Rindeal**-Algorithmus (Rijmen und Daemen)
- GMS (Mobilephone)
	- A5/2, A5/3, A5/4


| Chiffre  | Autor                    | Schlüssellänge | Kommentar                 |
| -------- | ------------------------ | -------------- | ------------------------- |
| Blowfish | Bruce Schneider          | 1-448 Bit      | Alt und langsam           |
| DES      | IBM                      | 56 Bit         | Heutzutage Schwach        |
| IDEA     | Massey und Xuejia        | 128 Bit        | Gut aber patentiert       |
| RC4      | Ronald Rivest            | 1-2048 Bit     | Gewisse Schlüssel schwach |
| RC5      | Ronald Rivest            | 125-256 Bit    | Gut aber patentiert       |
| Rijndael | Daemen und Rijmen        | 128-256 Bit    | Beste Lösung              |
| Serpent  | Anderson, Biham, Knudsen | 128-256 Bit    | Sehr stark                |
| Triple   | IBM                      | 168 Bit        | Zweitbeste Lösung         |
| Twofish  | Bruce Schneider          | 128-256 Bit    | Stark, weitverbreitet.    |



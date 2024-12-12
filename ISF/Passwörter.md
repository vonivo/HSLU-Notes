Passwörter sind einer der schwächsten Teile der Online-Authentifizierung.

Je komplexer ein Passwort, sprich je mehr Zeichen verwendet werden können und werden, desto schwieriger kann es durch Bruteforce geknackt werden.

Passwörter sind schwach:

- Menschen sind schlecht darin, Zufälligkeit zu erzeugen
- Gute Passwörter sind schlecht merbar
- Gemeinsames Nutzen von Passwörtern für verschieden Dienste
- Sobald ein Angreifer Zugriff auf das Postfach hat

Regeln für sicheres Passwort:

- > 12 Zeichen
    
- Ziffern, Gross- Kleinbuchstaben sowie Sonderzeichen
- Keine Tastaturfolgen
- Kein Word einer bekannten Sprache
- Nicht überall dasselbe Passwort, 1 pro Anwendung
- Passwort nicht unverschlüsselt abspeichern
- Sofortiges Ändern beim Verdacht auf Kompromittierung
- Passwortsafe verwendenden

Gegenmassnahmen zu schwachen Passwörtern → MFA

## Speicherung
Password Based Key Derivation Function

- Ressourcenintensive kryptographische Hashfunktionen
    - mehrmals verknüpfte Hashes
    - Geschwindigkeit bestimmt durch Anzahl runden
    - erschwert Angriffe
    - Beispiele: PBKDF2, bcrypt, scrypt, Argon2

Best Practice:

- Nur Hashwert speichern
    
- Resource-intensive Hashfunktion verwenden
    
- Mit Salt gemeinsam hashen (unique)
    
    - So kann nicht erkannt werden ob zwei Nutzer das gleiche Passwort haben
- Online Passwort guessing
    
    - Normaler Login Prozess wird verwendet um das Passwort zu erraten
    - Anzahl Versuche limitieren
- Offline Passwort guessing
    
    - Angreifer hat Zugang zu der DB und versucht Passwörter zu erraten
    - Passwörter richtig abspeichern
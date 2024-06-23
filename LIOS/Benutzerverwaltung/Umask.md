Die Umask ist ein Werkzeug, dass die [[Permission|Brechtigungen]] beim Erstellen kontrolliert.
Die Umask ist ein Wert, der bei der Erstellung einer Datei den Berechtigungen abgezogen wird.


**Initiale Dateiberechtigungen:**
Dateien -> 0666 `-rw-rw-rw-`
Verzeichnis -> 0777 `drwxrwxrwx`

**Standard Umas**
Standard-Benutzer: `0002`
Root-Benutzer: `0022`

Wenn nun ein Standardbenutzer ein neues File erstellt erhält dies die Berechtigung: `0664` (`0(6-0)(6-0)(6-2)`.
Analog beim Root-User `0644`

Bei Verzeichnissen
Standard-Benutzer: `0775`
Root-Benutzer: `0755`

SELinux (Security-Enhaced [[Linux]]) bietet eine wichtige Sicherheitsfunktion von LInux. Es erweitert den Link-Kernel und ist der erste Versuch, das FLASK-Konzept (OS-Sicherheitsarchitektur) einzusetzen.

Mit SELinux wird der Zugriff auf Dateien und andere Ressource auf granularer Ebene gesteuert.

SELinux bietet dabei nur eine Zutrittskontrolle, jedoch keine Inhaltskontrolle.
Dies wird über Zielrichtilinen erreicht.

Diese Richtlinien werden geschrieben, um Aktivitäten einer einzelnen Anwendung abzudecken. Sie deklarieren vordefinierte Labels für einzelnen
- Programme,
- Dateien und 
- Netzwerkports.
![[SELinux.png]]

SELinux arbeitet **präventiv** (nicht alle Sicherheitsfragen können im Voraus abgedeckt werden)
- Erzwingtt eine Reihe von Zugriffsrechten
- Zusätzliche Sicherheitsschicht und Komplexitätsschicht
- Vorbeugung von unbekannten Schwachstellen -> Konzept des Whitelisting.
- Eine Schwäche in einem Teil des Systems kann sich nicht ausbreiten.

SELinux kennt drei Modi:
1. Enforcing -> Zugriffssteuerungsregeln werden erzwungen (Standard)
2. Permissive -> SELinux ist aktiv, aber Zugriffssteuerung wird nur geloggt. (Für Debugging)
3. Disabled -> Deaktiviert.

Der Modus kann wie folgt verändert werden
**Auslesen**
`[user@host ~]$ getenforce`

**Ändern**
`[user@host ~]$ setenfore 0 # 0=permissive, 1=enforcing`

Alternativ kann auch ein Parameter dem Kernel beim Bootvorgang übergeben werden.

Dauerhaft kann die SELinux-Konfiguration im File `/etc/selinux/config` angepasst werden.


# Übersicht
![[SELinuxOverview.png]]
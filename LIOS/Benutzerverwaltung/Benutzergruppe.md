In Linux existieren verschiedene Benutzergruppen, dabei wird zwischen:
- Primärgruppe
- Zusatzgruppe
unterschieden.

=> Jeder Benutzer gehört genau **einer Primärgruppe** an. Diese wird beim Erstellen eines Nutzers erstellt und heisst meistens wie der Nutzer selbst.

=> Benutzer können 0 bis $\infty$ Zusatzgruppen angehören.

Technisch existiert kein Unterschied der beiden Gruppen, sondern die Zuweisung ist entscheidenden. In [[Nutzerverwaltung#`/etc/passwd`|/etc/passwd]] kann ein Benutzer eine Gruppe zugeordnet werden. Diese Gruppe entspricht der **Primärgruppe**.
Alle Zusatzgruppen werden über `/etc/groups/` zugeteilt.


# `/etc/group`
Alle Benutzergruppen werden im File `/etc/group` festgehalten. Jede Zeile reräsentiert eine Gruppe.

Beispiel:
```bash
root:x:0:root
sys:x:3:bin,vonivo
vonivo:x:1000:
```
Die verschiedene Spalten werden mittels `:` getielt und sind von links nach rechts:
- Gruppenname
- Gruppenpasswort -> immer 'x' da veraltet
- GID
- Zugehörigkeitsliste von [[Nutzerverwaltung|Benutzer]] -> mit `,` getrennt.

Im obigen Beispiel ist der Benutzer `vonivo` Mitglied der Zusatzgruppe `sys` gleichzeitig ist seine Primärgruppe (siehe `/etc/passwd`) `vonivo`.

>[!error] Achtung
> Eine Gruppe kann nicht mitglied einer weiteren Gruppe sein.



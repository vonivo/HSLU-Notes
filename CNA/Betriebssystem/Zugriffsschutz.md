Der Zugriffsschutz stellt sicher das nur autorisierte Benutzer bestimmte [[Prozesse]] und Dateien sehen und mit ihnen interagieren darf. 
- Ein Supreuser (Root/Admin) darf dabei mehr/alles

[[Prozesse]] und Dateien haben in [[Multiuser]]systemen immer einen Besitzer:
- Diesem ist es erlaubt die Rechte für Erstellen, Terminieren und auch die Sichtbarkeit zu bestimmen

In [[Konkrete Betriebssysteme#UNIX|UNIX]] werden die Rechte mit 3 Bits representiert: rwx = Read/Write/Execute
- Diese Rechte können auf User/Gruppen/Other gesetzt werden

Moderne OS arbeiten mit ACL (Access Control List) –> Dies erlauben eine beliebige Rechtedefinition
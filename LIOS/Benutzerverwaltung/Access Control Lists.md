Die [[Permission|Standard-Berechtigungen]] sind ausreichend, wenn Dateien nur von einem Benutzer und einer festgelegten Gruppe bearbeitet werden.
Ist dies nicht der Fall, reichen sie nicht aus.

Für genau solche Fälle wurde die **Access Control List (ACL)** eingeführt.
ACLs können mehrere [[Nutzerverwaltung|Benutzer]] und [[Benutzergruppe]] durch Namen oder ID (UID oder GID) identifiziert berechtigen.

Dabei bleiben werden die regulären Berechtigungen `rwx` verwendet. Die zusätzlichen Benutzer und Gruppen werden als **Name User/Group** bezeichnet.

Die ACL einer Datei oder eines Verzeichnisses kann durch den Eigentümer gesetzt werden oder von Administratoren, welche die Fähigkeit `CAP_FOWNER` hat.

>[!info]
>Dateien und Verzeichnisse erben automatisch die ACL-Eigenschaft der Default-ACL des übergeordneten Verzeichnisses.


# Anzeigen von ACL
Mit dem [[Prompt|Befehl]] `ls -l` werden nur minimale Inforamtione zu ACL angzeigt:
```bash
[user@host ~]$ ls -l /shared-data/
-rw-rw-r--+ 1 labstudent labstundetn .............
```
=> Das Plus-Zeichen zeigt an, dass eine ACL-Struktur für die Datei existiert.
- user-Berechtigung -> Zeigt Benutzer-ACL
- group-Berechtigung -> Zeigt ACL-Maske
- other-Berechtigung -> Zeigt other Berechtigung
>[!error] Achtung
>Durch die Veränderung der group-Berechtigung wird nicht die Gruppen-ACL-Berechtigung geänder sonder die ACL-Maske


Mit dem Befehl `getfacl` können die ACL ausgelesen werden:
```bash
[user@host ~]$ getfacl shared-data.txt
# file: shared-data.txt
# owner: labstudent
# group: labstudent
user::rw-
user:labadmin:rw-
group::rwx
mask::rw-
other::r--
default:user::rwx
default:group::r--
default:other::---
```

- Die ersten 3 Zeilen sind Kommentare zum File (Für [[Permission#Special Bits|Special-Bits]] würde eine 4. Zeile hinzukommen)
- Die erste Spalte zeigt an, was berechtigt werden will. (`user`, `group`,`other` oder `mask`)
- In der zweiten Spalte wird der Benutzer/Gruppe benannt. Ist das Feld leer, wird bei `user` und `group` die Eigentümer benutzt.
- Die dritte Spalte zegit dann die entsprechenden Berechtigungen

=> Es können auch default Berechtigungen definiert werden.

# Setzen von ACL
Um ACLs zu setzen wird der Befehl `setfacl` verwendet. Die Berechtigungen sind abei auc `r,w,x,-`. Wenn ACL rekursiv gesetzt werden kann `X` verwendet werden um die Execute-Berechtigungen auf Verzeichnissen aber nicht auf Datei zu sezten.

## Beispiele
### Hinzufügen
```bash
[user@host ~]$ setfacl -m u:name:rwx file # Hinzufügen von User ACL
[user@host ~]$ setfacl -m g:name:rwx file # Hinzufügen von Grp ACL
[user@host ~]$ setfacl -m o::-       file # Hinzufügen von Other ACL
[user@host ~]$ setfacl -m m::r--     file # Setzen der Maske
[user@host ~]$ setfacl -m d:u::rw-   file # Setzen von Default
[user@host ~]$ setfacl -mR u::rw-  dir  # Rekursiv Setzen von ACL
```

## Löschen
```bash
[user@host ~]$ setfacl -x u:name file # Löschen
[user@host ~]$ setfacl -b file        # Löscht alle ACLs
```

# ACL-Maske
Die ACL-Maske legt die maximale Anzahl an Berechtigungen fest, die:
- benannten Benutzern,
- Gruppeneigentümer,
- benannte Gruppen,
erhalten können.

Der Eigentümer sowie sonstige Benutzer werden von der Maske nicht beinflusst.


# Berechtigungsreihenfolgen
1. Dateieigentümer -> Benutzer-ACL.
2. Benutzer welcher in einer ACL aufgeführt ist -> ACL-Benutzer-Eintrag.
3. Gruppe die dem Eigentümer oder einer benannten Gruppe entspricht -> Entsprechende ACL-Gruppe
4. Sonstige-ACL
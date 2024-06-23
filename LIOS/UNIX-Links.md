---
aliases:
  - symbolischer Link
  - hard Link
---
In [[Linux]] Betriebssystemen existieren zwei verschiedene Arten von Datei-Links.

# Hardlink
Ein Hardlink ist eine zusätzlicher/zweiter Verweis im Dateisystem auf die Originaldaten. Sprich eine zweiter Eintrag im Dateisystem welcher auf die Selbe Inode welche auf den Daten im Dateisystem zeigt.
![[Hardlink.png]]
## Eigenschaften
- Kann Dateisystem nicht überschreiten.
- Kann keine Verzeichnisse verknüpfen.
- Hat dieselbe Inode-Nummer und Berechtigungen wie die Originaldatei.
- Berechtigungen werden aktualisier, wenn sich die Berechtigungen der Originaldatei ändern.
- Entählt tatsächlich den Inhalt der Originaldatei -> Wenn Datei verschoben wurde funktioniert der Link immer noch.

```bash
[labstudent@lios-01 ~] ls -l
-rw-rw-r--. 2 labstudent labstudent 0 Mar 11 02:30 rezept
```
Die Nummer zwei nach den [[Berechtigungen]] zeigt an, dass es zwei Dateien mit derselben Inode-Nummer gibt.

# Softlink
Ein Softlink / symbolischer Link ist eine zweite Datei, welche eine Referenz auf die Originaldatei enthält.
![[Softlink.png]]
## Eigenschaften
- Kann dateisystemübergreifend sein.
- Ermöglicht zwischen Verzeichnisen zu verlinke.
- Hat eine andere Inode-Nummer und Dateiberechtigungen als die Originaldatei.
```bash
[labstudent@lios-01 ~] ls -l
-rw-rw-r--. 1 labstudent labstudent 0 Mar 11 02:30 rezept -> /var/rezept
```
Der `->` zeigt dass es sich bei der Datei rezept um einen Softlink handelt welcher auf `/var/rezept` verlinkt handelt.
- Ein Linux-Container LXC ist eine Gruppe von Prozessen die auf einem Server ausgeführt werden.
- Sie sind komplett isoliert von anderen Prozessen.
- Container sorgen für Isolation, sodass dieselbe Betriebssysteminstanz verwendet werden kann.

Container verwenden keine [[Hypervisor]] und daher auch kein Trap and Emulate. So können viele Prozessorzyklen eingespart werden.


**Funktion**
- Stellt feingranulare Kontrolle der individuellen Prozesse und Applikation zur Verfügung.
- Erlaubt die Isolation von Applikation
- Transparente Migrationen von Applikationen möglich (kein OS verschieben)
- **kein fremdes OS**

Damit die LXC Virtualisierung funktioniert muss:
- Container auf demselben Patchlevel laufen.
- Ressourcenmanagement eingeschaltet sein.

Welche drei Funktionen müssen vorhanden sien um Containerisierung zu betreiben?
- Filesystemgrenzen für Prozessor: **[[chroot]]**
- Ressourcen-Sharing zwischen Prozesse Gruppen: **[[cgroups]]**
- Namespaces: **ns** oder **[[namespaces]]**

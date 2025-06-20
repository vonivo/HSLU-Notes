>[!Definition]
>Ziel von Continious Integration (CI) ist, immer ein lauffähiges Produkt (Buildresultat) verfügbar zu haben.

Durch CI:
- Ist immer ein lauffähiges Produkt verfügbar.
	- Erlaubt Continious Testing.
- Bei Fehler jeder Art soll möglichst schnell Feedback erteilt werden.
	- Primär durch [[Unit Tests]] und [[Integrationtests mit JUnit|Integrationtests]]
	- Aber auch durch Compiler, Classpath, statische Codeanalyse, etc.
- Im Team parallel entwickelt werden können.
	- Behalten von Überblick.
	- Integrationsaufwand minimiren (small steps)
	- Aktuellen Zustand auf dem laufenden beliben.


## Praktiken
1. Zentrales [[Versionskontrollsysteme]].
2. Automatisierter [[Buildprozess]].
3. Automatisierte Testfälle.
4. Arbeiten auf dem Master-Branch.
5. Jede Änderung triggert einen Build.
6. Schneller [[Buildprozess]].
7. Auf/mit Kopien der produktiven Umgebung testen.
8. Einfacher Zugriff auf aktuelle Buildartefakte.
9. Offensive Information über den aktuellen Zustand.
10. Automatisches Deployment

### 1. Zentrales [[Versionskontrollsysteme]]
Sämtliche Quell-Artefakte welche für den [[Buildprozess]] benötigt werden unterliegen der Versionskontrolle.
-> Alles was für den Build gebraucht wird, aber nichts was wieder gebaut werden kann.

**Empfehlungen**
- Sinvolle Commit-Kommentare
- Tagging für Releaseversionen.
- Branches für parallele Entwicklung

### 2. Automatisierter [[Buildprozess]]
Der [[Buildprozess]] soll reproduzierbar, auf einer sauberen Maschine [[Buildserver]] durchgeführt werden.

Der Build darf ausschliesslich auf Basis der aktuellen Quelle aus dem [[Versionskontrollsysteme|VCS]] gebaut werden.

Im [[Buildprozess]] enthalten sind:
- Testfälle (Unit- und Integration)
- Code-Qualität

### 3. Automatisierte Testfälle
Die Abdeckung durch automatisierte Testfälle sollte möglichst gross sein.

Primär werden [[Unit Tests]] ausgeführt. Sekundär [[Integrationtests mit JUnit|Integrationtests]] da dieses eventuell nicht überall laufen.

**Empfehlung**
- Test müssen stabil laufen.
- Test sollen so schnell wie möglich korrigiert werden.
- Eventuell Performance-Tests

### 4. Auf dem Main Branch arbeiten
Änderungen sollten möglichst früh in den Main-Branch integriert werden, um unnötige Konflikte etc. vorzubeugen.

**Empfehlung**
- **Kurze, gezielte Branches** statt langem Abseitsentwickeln.
- **GitFlow oder GitHub-Flow** als Modelle für Teams
- **Ziel**: häufige, einfache Integration

### 5. Jede Änderung triggert einen Build
Der [[Buildserver]] prüft regelmässig, oder wird benachrichtigt, wenn es eine Änderung im [[Versionskontrollsysteme|VCS]] gegeben hat und startet dann einen Build.

Die Ergebnisse des Builds werden offensiv kommuniziert.

Bricht ein Build ab, sollte er möglichst schnell gefixt werden.

### 6. Schneller [[Buildprozess]]
Je schneller ein Entwickler Feedback bekommt, desto besser.

Da mache Tests länger dauern, kann auch ein Kompromiss mit einem **Nightly-Build** gemacht werden.

Der [[Buildprozess]] sollte nach dem Prinzip **Fail-Fast** aufgebaut sein

### 7. Auf/mit Kopien der produktiven Umgebung testen
Die Zentrale Build- und Testumgebung sollte möglichst ähnlich zur Produktiv-Umgebung sein.

Ideal wäre ein Kopie der Produktiven-Umgebung. Dies ist jedoch oft teuer und teilweise aus Dateschutgründen nicht möglich.

Alternativ können auch [[VSK/Containervirtualisierung/Docker|Docker]] eingesetzt werden.

Die Ähnlichkeit umfasst:
- Hardwareaustattung
- OS
- Laufzeitumgebung
- Netzwerzugriffe
- Datenqualität und Menge
- Technologien

### 8. Einfacher Zugriff auf aktuelle Buildartefakte
Sämtliche Buildresultate sollten jederzeit über den [[Buildserver]] / [[Binary-Repo]] abrufbar sein.

Dadruch kann schnell die neuste Version weiterfürend getestet werden.

### 9. Offensive Information über den aktuellen Zustand
Für jeden Entwickler ist jederzeit ersichtlich, wellche Änderungen:
- von wem und wann eingecheckt wurde.
- von welchem Build erstmals erfasst wurde.
- zu welchen Ergebnissen geführt haben.
- zu welchem Issue gehören.
- welche Massnahmen getroffen wurden.

Transparenz hier nicht als Kontrolle sonder als Unterstützung.

### 10. Automatisches Deployment
Wenn möglich sollten Build-Ergebnisse auch automatisch verteilt und installiert werden.

Zumindest sollte regelmässig automatische aktualisiert werden:
- z.B. Täglich, über Nacht etc.
- alle 5min eine Server-Applikation zu deployen macht wenig sind.

Die Software sollte möglichst schnell zum Testing und einholen von Feedback wieder bbereitstehen
---
aliases:
  - VCS
---
**Ziel**: Abfolge aller Bearbeitungsschritte an Artefakten benutzerbezogen und detailliert zeitlich **nachvollziehen** zu können.

Ein VCS hält die verschiedenen Revisionen fest und erlaubt jederzeit eine vorhergegangene Revision aufzurufen.
Dabei ist ein VCS für **konkurrenzierenden Zugriif** ausgelegt:
- Teamarbeit auf gemeinsamen Quellen.
- Automatisches Merging bei Konflikten.
- Zentrale oder verteilte Datenhaltung.

>[!warning]
>Im Gegensatz zu Filesharing Diensten werden keine Informationen im Hintergrund Synchronisiert. Jeder Schritt bei einem VCS wird explizit ausgeführt.

Änderungen werden als sogenannte **Changeset** innerhalb einer Transaktion gespeichert.


## Tags
Ein Tag markiert einen bestimmten Revisionsstand mti einem Namen, dies ist oft der Versionsname [[Semantic Versioning]].

Tags sind bei Releases sehr nützlich und dienen als Markierung von "Meilensteinen" (Releases).

Tagging wird verschieden ausgeführt:
- Markierung in jeder Datei (CVS)
- Kopie aller Artefakte in ein anderes Verzeichnis (Subversion)
- Identifikation eines Änderungsstandes des gesamten Dateisystems (git.)

## Branching
Ein Branch ist ein getrennter Entwicklungszweig (lokal oder zentral).
Er eignet sich für:
- Prototypen, Test und/oder Experimente.
- Bugfixing bereits geschlossener Versionen.
- Professionelle Workflows (GitFlow)
![[GitFlow.png]]

## Was wird alles Verwaltet
Es sollten ausschließlich Quell-Artefakte eingecheckt werden. (z.B. `*.java`, `*.properties`-Files).

Es sollten **nie generierte Artefakte** eingecheckt werden. z.B. `*.jar`-Files.

Dies kann mit einem `.gitignore` gesteuert werden (wird meistens generiert).

## Verteilt oder Lokal
![[VCS.png]]
Bei Git existiert immer Lokal ein Repository.
Wird Git zusammen mit einem Server eingesetzt, existiert auch auf dem Server ein Repository. Nun gibt es verschiedene Befehle um mit den verschiedenen Repositories umzugehen.
## Beispiele
- [[CVS]]
- [[SVN]]
- [[GIT]]
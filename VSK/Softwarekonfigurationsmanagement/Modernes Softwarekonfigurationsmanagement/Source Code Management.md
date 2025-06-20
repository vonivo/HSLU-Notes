Version Control Systems bilden die Basis für Konfigurationsmanagement. Alle Bestandteile müssen identifizierbar sein. (Code, Doku, Binärdateien, etc.)

Verschiedene Codeprojekte können in separaten Repositories verwaltet werden oder in einem einzigen.

Falls mehrere Repositories verwendet werden, muss eine **Verbindung** zwischen den **Versionen der Repositories** hergestellt werden. Dies wird durch **Tags** sichergestellt.
Der Tag enthält dann die Versionsnummer.

Oft werden auch verschiedene Repository-Typen eingesetzt:

| Typ                     | Technologie   |
| ----------------------- | ------------- |
| Source-Code             | Git           |
| Builds / Binärdateien   | Nexus         |
| Container-Images        | GitLab, Nexus |
| Umgebungs-Konfiguration | Git           |
| Manuelle Testfälle      | Spez. Tools   |
| Benutzer-Dokumentation  | Spez. Tools   |
| Release-Konfiguration   | Spez. Tools   |

## Build Id
Mithilfe einer automatisierten "immutable[^1] Build-ID welche sich **im Buildartefakt** befindet, kann ein Build zuverlässig identifiziert werden.

**Beispiel für das Einbetten einer Build-ID in C Artefakt**
1.  Zuerst wird die Build-ID (Commit-Hash) dem Build-Tool (hier Makefiles) mitgegeben:
```yaml
  build:
    stage: build
    script:
      - make BUILD_ID=\"$CI_COMMIT_SHA"
    artifacts:
      pahts:
        - logger
```
2. Die Build-ID wird an den Code als Parameter weitergereicht
```shell
  BUILD_ID="manual"
  logger: main.c
          gcc -o logger main.c -D BUILD_ID='$(BUILD_ID)'
```
3. Einbettung der ID im Build-Artefakt:
```c
  #include <stdio.h>
  int main(int argc, char* argv[]) {
    printf("Distributed Logging System (build ID: %s)\n", BUILD_ID);
    return 0;
  } 
```

Es ist wichtig, dass auch das **Dockerimage** oder die **Infrastruktur**, auf welchem der Build entstanden ist, **wiederherstellbar** ist. Dies sollte in regelmässigen Abständen **getestet** werden.

Alternativen zu Build IDs:
- Disk einer Entwicklungsmaschine abspeichern 
- Exaktes Manual, wie eine Umgebung aufgesetzt werden kann


[^1]: Echte Immutabilität nur möglich mit Signaturen, oft reicht schwierig änderbar
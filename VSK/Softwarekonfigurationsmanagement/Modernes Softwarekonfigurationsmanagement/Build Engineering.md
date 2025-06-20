Durch das Build-Engineering werden **identifizierbare** und **reproduzierbare** Builds sichergestellt.

Dabei sind:
- Builds verständlich, wiederholbar, schnell und zuverlässig.
- Jede Konfiguration identifizierbar.
- Source- und Compile Abhängigkeiten leicht zu ermitteln.
- Build-Anomalien leicht zu identifizieren und auf akzeptable Weise zu verwalten
- Ursachen für fehlerhafte Builds schnell und einfach zu identifizieren und beheben.

Dies wird sichergestellt durch:
- Verwendung **exakter Versionen** (kein SNAPSHOT oder latest)
- Deterministischer Builds (Gleicher Input => gleicher Output)
  - Ursachen für nicht deterministische Builds:
    - Timestamps
    - Parallele Kompilation -> Linking Reihenfolge bei C (=> Alphabetische Sortierung)
    - Code-Generierung
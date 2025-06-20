Für viele Sprachen gibt es Tools, welche Hinweise zur Codequalität liefern.
Meistens sind diese:
- Freistehend  -> In CI/CD nutzbar.
- Individuell und projektspezifisch konfigurierbar
- Plugins für IDE

**Beispiele**: Checkstyle, PMD, Spotbugs, [[SonarQube]]

Verwendung über:`mvn site`

## Herausforderungen
Es gibt viele verschiedene Tools, welche alle andere Schwerpunkte legen und auch verschiedene Qualitäten haben.

Die Standard-Herausforderungen sind:
- Pflege der Konfiguration (im Projekt oder Zentral)
- Unterschiedliches Reporting, Doppelbefunde.
- Umgang mit "false-positiv"
- Integration in Build- und Entwicklungsumgebung
- Wie werden Ergebnisse von verschiedenen Tools zusammengeführt?

Die Integration dieser Tools wird am einfachsten über Reporting gemacht, dies führt aber zu **langen Feedbackloops**. (Integration ist auch in IDE möglich, meist komplizierter.)
---
aliases:
  - API
---
>[!Definition]
>Ein API ist eine Schnittstelle die explizit darauf ausgelegt ist, eine Softwareeinheit (Modul, Library, System) nutzbar zu machen.

**Ziele**
- Möglichst einfache Nutzung ermöglichen
- Aufwand für Nutzer minimieren
- Unabhängig von konkrenten Implementation
- Hat implizites Mass an Öffentlichkeit

Eine API wird von Nutzern verwendet und von Anbieter implementiert.
- JPA (Java Persistance API)
- SLF4J

Eine API hat nicht nur eine Art von Nutzer -> Auch Anbieter von Implementationen sind Nutzer.


## API vs. Schnittstelle
Die Unterscheidung von API und Schnittstelle ist nur eine Frage des Scopes. Rein technisch sind beide identisch.

## Eigenschaften
**Gute** APIs haben ein grossen Wert:
- Fördern die [[VSK/Deployment/Modularisierung|Modularität]] und [[VSK/Modularisierung/Kopplung|Entkopplung]]
- Machen komplizierte Dinge viel einfacher nutzbar.
- Erlauben, die Implementation einfach auszutauschen.
- Gute, einfach APIs machen ein Produkt attraktiv für Benutzende
- Gute APIs binden die Nutzende.

**Schlechte APIs**
- Komplizierte, missverständliche Nutzung, aufwändige Fehlersuche, Support
- Verführen dazu, eine bereits existierende, gute Lösung nicht wiederzuverwenden.
- Verführen zu komplizierten Umwegen und unnötigen Fassaden oder Adaptern.

## Herausforderungen
Öffentliche APIs leben fast ewig.
- Alle Fehler welche im Design gemacht werden leben auch.
- APIs nur mit grossem Aufwand / Konsequenzen änderbar
- Meist nur eine Chance die API richtigzumachen.

Die Kunst ist die API so zu entwerfen, dass sie entwicklungsfähig ist.
-> KISS und YAGNI mit gesundem Augenmass

## Hauptziele der API
- Maximale Entkopplung
- Maximales Information Hiding
- Maximale Kohäsion.

## Qualitätsanforderungen
- **Konsistenz**: Namensgebung und -regeln konsequent einhalten.
- **Namensgebung**: Einfache, eingängige, treffende Namen wählen.
- **Verhalten**: Klare Erwartungen erfüllen, ohne Nebeneffekte
- **Erweiterbarkeit**: Offen für Weiterentwicklung
- **Dokumentation**: Einfache, hilfreiche, kompakte Dokumentation
- **Perspektive**: Einfache Nutzung
- **KISS**: Möglich einfach
- **Sicherheit**: Die Nutzung ist sicher zu gestalten.
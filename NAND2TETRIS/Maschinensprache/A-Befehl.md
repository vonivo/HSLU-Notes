>[!Definition]
>Der **A-Befehl** setzt das Register `A` auf einen 15-Bit-Wert:
>symbolisch: `@value`
>binär          : `0vvv'vvvv'vvvv'vvvv`

`value` ist entweder eine nicht negative Dezimalzahl oder ein Symbol das sich auf eine solche Zahl bezieht.

**Zwecke:**
- Programmgesteuertes Laden einer **Konstanten**.
- Schafft Voraussetzungen für einen nachfolgenden [[C-Befehl]], welcher eine bestimmte Datenspeicherstelle manipulieren soll, in dem `A` auf die Adresse dieser Stelle gesetzt wird.
- Schafft Voraussetzung für einen nachfolgenden [[C-Befehl]], welcher einen Sprung ausführt, indem die Adresse des Sprungziels in `A` geladen wird.

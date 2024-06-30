Der Datalink-Layer ist der zweite Layer im [[OSI Referenzmodell]] und ist für die Übertragung der [[Dataframes]] zuständig. Er betreibt ausserdem eine [[Fehlersicherung]] und die Adressierung der Pakete auf dem Medium [[Adressräume#MAC-Adressen|MAC-Adressen]].

Die zuverlässige Übertragung wird realisiert durch:
- [[Fehlersicherung]].
- Fehlerkorrektur falls möglich.
- Falls Empfang ok -> positive Rückmeldung.
- Kommt keine Meldung nach Timeout -> Frame nochmals senden.
- Durchnummerieren der Frames -> Verlorene Frames werden erkannt.

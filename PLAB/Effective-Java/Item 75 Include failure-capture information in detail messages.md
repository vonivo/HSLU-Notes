Wenn ein Programm fehlschlägt, soll die Error-Message so detailliert sein dass der Programmierer den Fehler gut analysieren kann.
Es kann sein, dass dem Programmierer nur die Fehlermeldung bleibt, da der Fehler z. B. nicht reproduziert werden kann.

Eine gute Fehlermeldung:
- enthält alle Werte von allen [[Parameter]] und [[Attribut|Attribute]] welche zum Fehler beigetragen haben. (Bsp: Bei `IndexOutOfBoundsException` sollte der `lowerBound`, `upperBound` sowie der `index` innerhalb der Meldung sein)
- enthält **keine** Passwörter, Encryption-Keys und andere sensitive Daten. (Fehlermeldungen werden teilweise von sehr vielen Personen gelesen.)
- enthält nicht viel Prosa. (**Informationsgehalt** steht über **Lesbarkeit**)

Ein guter Weg um diese Informationen zu erhalten ist, anstatt einem `String-Consturctor` einen `Constructor` bereit zu stellen, welcher die notwendigen Werte verlangt.
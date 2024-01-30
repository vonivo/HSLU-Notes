[[Streams]] sind ein Weg, um Bulk-operations einfach und deklarativ durchzuführen.
Dabei sind Stream in verschiedene Operationen aufgeteilt:
- **Source** -  Stream wird erstellt
- **Intermediate** - Veränderung / Bearbeitung des [[Streams]]
- **Terminal** - Konsumieren und schliessen des [[Streams]]

[[Streams]] sind "lazy", das heisst, sie werden erst mit einer Terminal-Operation ausgeführt. Die Stream-API ist "fluent", d. h. können mehrere Operationen aneinander gekettet werden.

>[!warning]
>Stream sollten mit bedacht eingesetzt werden, da sie einerseits Code vereinfachen können, andererseits aber auch extrem verkopmlizierern.

Zu beachten bei [[Streams]]:
- Wenn keine **expliziten Typen** angegeben werden, ist der **Name von [[Parameter]]** extrem **wichtig** für die **Lesbarkeit**.
- Der Gebrauch von **Helper-[[Methode|Methoden]]** **erhöht** bei [[Streams]] die **Lesbarkeit**, da [[Streams]] keine Methoden und Parameternamen besitzen.
- **Achtung bei Chars**.


## Vorteile von [[Streams]]
- Einheitliche **Transformation** von einer Sequenz von Elementen.
- **Filtern** einer Sequenz von Elementen.
- **Kombination** von einer Sequenz von Elementen.
- **Suche** nach einem bestimmten Element.
## Nachteile von [[Streams]]
- Es können nur Final oder quasi Final variablen genutzt werden.
- Kein `return`, `break`, `continue` und keine [[Exceptionhandling#Arten von Fehlern|checked Exceptions]].


>[!info]
> Wenn man sich nicht sicher ist, ob [[Streams]] oder nicht, beide Wege versuchen und danach entscheiden.




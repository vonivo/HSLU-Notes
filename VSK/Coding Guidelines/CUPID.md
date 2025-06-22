>[!Definition]
>CUPID fasst fünf wichtige Designprinzipien zusammen. Cupid ist dabei eine ergänzung zu [[SOLID]] und etwas positiver formuliert.

## Composable
Gute Code hat eine kleine Oberfläche, also er exponiert nur das absolut Nötige.
Dadurch kann:
- Die Wiederverwendung möglichst einfach gehalten werden.
- Es gibt weniger Konflikte bei Änderung und Verschiebung.
- Hohe [[VSK/Modularisierung/Kohäsion|Kohäsion.]]

Mit eindeutig definierten Schnittstellen ist er einfacher zu verstehen und leichter zu verwenden:
- Die Intention des Codes soll offensichtlich sein.
- Wissen über die Internals hingegen nicht 


## Unix Philosophy
Guter Code macht nur **eine** Sache diese dafür aber richtig.
[[Single Responsibility Principle (SPR)]]


## Predictable
Der Code verhält sich wie erwartet ohne unliebsame, unerwartete Überraschungen.
- Keine Nebeneffekte.
- Namensgebung: Verspricht nicht falsches.

Der Code ist deterministisch in der Ausführung.

Der interne Status einer Softwareeinheit kann von den Ausgaben zwar abgeleitet werden, ist aber nicht veränderbar.


## Idiomatic
- Die Nutzung des Codes fühlt sich natürlich an.
- Es werden die Idiome des Kontexts (Domäne, Firma, Team) sowei des Ökosystems der Programmiersprache verwendet.

## Domain-Based.
Für den Code wird die Domänensprache und deren Struktur genutzt.
Es wird keine Struktur eines Frameworks aufgezwungen.

Guter Code spiegelt die Lösung wieder und nicht das Framework.
Anstatt technischer Begriffe sollen die Domänenbegriffe verwendet werden.

>[!Definition]
>In einer verteilten Applikation sind die einzelnen Teile der Applikation ([[Systeme und Komponenten]], Module, Schichten, etc.) auf mehrere verschiedene Rechner verteilt.

- Die verschiedenen Teile laufen nun in **einzelnen**, **unabhängigen** Prozessen
- Die Teile laufen in **echter Parallelität**

## Anforderungen an verteilte Systeme
- Die Teile müssen über ein sinnvolles Medium miteinander kommunizieren.
- Die einzelnen Teile müssen sich gegenseitig finden und kennnen (**Binding**)
- Die Applikation muss resilient aufgebaut sein, sprich sie kann sich von gewissen Fehler erholen (Selbstheilend).

## Konsequenzen
Durch die Verteilung wird das Deployment des Systems deutlich komplexer.
Abhängigkeiten müssen beachtet und koordiniert werden.

## Muster
![[Pasted image 20260107163226.png]]
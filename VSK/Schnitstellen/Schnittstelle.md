Wenn verschiedene [[Komponente|Komponenten]] zusammengefügt werden sollen, müssen diese über eine **Schnittstelle** interagieren.

Eine Schnittstelle ist lediglich eine Verbindungsstelle. Selbst kann sie nichts und tut auch nichts.

**Verständlichkeit**
Eine Schnittstelle macht eine Software verständlicher, da es genügt, die Schnittstelle zu betrachten (Ganze Konzepte werden abstrahiert.)

**Reduktion von Abhängigkeiten**
Durch Schnittstellen werden Abhängigkeiten in der Schnittstelle konzentriert und man ist von keiner spezifischen Implementation abhängig.

**Wiederverwendbarkeit**
Schnittstellen erleichtern die Wiederverwendbarkeit von bewährten Implementierungen.

>[!info]
>Schnittstellen entfalten ihren Nutzen nur dann, wenn wirklich ohne
Bezug auf die Implementierung nur gegen Schnittstellen programmiert wird

## Breite
Die Breite einer Schnittstelle bestimmt über:
- Anzahl Operationen
- Anzahl Funktionsüberschneidungen
- Anzahl von Parametern
- Anzahl globaler Daten
- Typ der Parameter und Rückgabewerte

=> Schämlere Schnitstellen haben weniger Abhängigkeiten.

## Kriterien
- Möglichst schmal
- einfach zu verstehen
- gut dokumentiert

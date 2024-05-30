## Grundidee
Eine Hashtabelle ist eine [[Hashbasierte Datenstrukturen|hashbasierte Datenstruktur]] bei welcher der Hashwert direkt als Index eines [[Array|Arrays]] verwendet wird.
![[Hashtable.png]]

Wenn diese Tabelle so umgesetzt wird, ist jedoch immer ein Array mit der Grösse $2^{31}$ notwendig, da der Hashwert vom Typ Integer ist.

### Lösung
- Das Array wird viel kleiner angelegt.
	Die Grösse des Arrays bestimmt den **Load-Factor** ($\frac{\text{Anzahl Daten}}{\text{Array Grösse}}$) somit wird der Speicherbedarf deutlich reduziert.
- Da der Hashwert nun nicht mehr direkt als Index verwendet werden kann, wird er mittels Modulo berechnet: $\text{Hash } \% \text{ Size} = \text{Index}$.
- Durch diese Berechnung können nun Kollisionen (Unterschiedliche Daten mit selben berechneten Index) auftreten.


## Umgang mit Kollisionen
Es wird vorausgesetzt, dass im Normalfall durch gute Hash-Funktionen möglichst keine Kollisionen auftreten und dies ein Spezialfall ist.

Der **Load-Factor** hat direkten einfluss auf die Anzahl Kollisionen:
- Ist der Loadfaktor klein, besitzt das Array viel Speicherplatz im Vergleich zu der Datenmenge $\implies$ weniger Kollisonen, mehr Speicher
- Ist der Loadfaktor gross, wird das Array kleiner im Vergleich zu der Datenmenge $\implies$ weniger Speicher, mehr Kollisionen

Da Kollisionen eher selten sind, darf ruhig etwas mehr Zeit beansprucht werden, um diese zu beheben (vgl. [[Binärer Suchbaum|nicht perfekter Suchbaum]]).

### Sondieren
Die Idee das Sondieren ist wie folgt, ist der berechnete Index des Elements $E_{1}$
schon besetzt, wird rechts von diesem Index weitergesucht, bis ein freier Platz gefunden wird.
Ist die Suche am Ende des Arrays angelangt, wird am Anfang des Arrays gestartet (**rotierend**). Wenn die Suche beim Startindex angekommen ist, wird abgebrochen.

$\implies$ Sondierungsketten beeinflussen alle weiteren Operationen auf der [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]].


## Operationen
- [[Einfügen in eine Hashtabelle|Einfügen]]
- [[Entfernen aus eine Hashtabelle|Entfernen]]
- [[Sucher in einer Hashtabelle|Suchen]]



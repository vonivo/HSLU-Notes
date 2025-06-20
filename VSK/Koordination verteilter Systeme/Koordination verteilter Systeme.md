Heute wird die Zeit mittels der TAI-International Atomic Time gemessen. Sie misst seit 1.1.1958 die Anzahl Ticks der Cäsium 133-Uhren.

Warum muss es eine Einigung auf die Zeit geben?
![[KoordinationVerteilterSysteme.png]]
Dies hat zur Folge, dass `output.c` nicht neu kompiliert wird, weil `output.c` scheinbar früher erstellt wurde.


## Lokale Uhren
Ein Timer ist eine Schaltung im Computer, welche die Zeit verwaltet.
Er misst die **Schwingungen eines Quarzkristalls unter Spannung** und erzeugt
Interrupts in bestimmten Intervallen (Tick).

-> Diese Zeitwerte laufen auseinander (auch wenn anfänglich synchronisiert)
da Quarzkristalle mit unterschiedlicher Qualität verwendet werden (-> Unterschiedliche Frequenzen). Das nennt man Uhrasymmetrie.

Methodne zur Synchronisation:
- [[Algorithmus von Cirstion]]
- [[Berkley-Algorithmus]]
- [[Network Time Protocol - NTP]]

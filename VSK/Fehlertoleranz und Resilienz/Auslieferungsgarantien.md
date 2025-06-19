>[!Definition]
>Es gibt folgende Auslieferungsgarantien:
>- **At-lest-once**: Message wird so oft gesendet, bis eine Antwort eintrifft. (Kann zu duplikaten führen)
>- **At-most-once**: Message wird höchstens einmal gesendet. (Aktion kann auch nicht ausgeführt werden.)
>- **Exactly-once**: Message wird exakt einmal ausgeführt. (Aufwändig und teuer, meist unnötig.)

## Idempotenz
Ein Funktion welche auf sich selbst angewandt das identische Resultat ergibt:
$$
f(x)=f(f(x))
$$
**Beispiel:** $f(x)=\mid x\mid$

### Idempotente Anfragen
Anfragen sind idempotent, wenn die Funktion auf der Gegenseite idempotent ist.

**Wichtig:** Eine idempotente Anfrage darf **keine** Nebeneffekte bewirken und kann ohne Probleme mehrmals ausgeführt werden.

**Beispiele für idempotente Anfragen**
- Lese-Anfragen von einem HTTP-Server
- Adressänderung von $A$ auf $B$ ohne Nebeneffekte.

**Beispiele für nicht idempotente Anfragen**
- Bestellung / Reservation in einem Restaurant.
- Löschen eines Files, falls das File in Zwischenzeit wieder erstellt werden kann.


## At-least-once Duplikatserkennung
At-least-once Duplikatserkennung simuliert **exactly-once**.

Die Duplikatserkennung kann wie folgt gemacht werden:
- **Heuristik:** Falls eine gewisse Fehlerwahrscheinlichkeit tolerierbar ist.
	- Methode um trotz unvollständigem Wissen praktikable Ergebnisse zu erzielen.
- **Sequenznummer:** falls alle Duplikate erkannt werden sollen.

### Mit Heuristik
Der Client sendet dem Server ein Duplikats-Flag mit (Optimiert Server).
Der Server verwendet dann diverse Kriterien um zu entscheiden, ob er die Aktion bereits ausgeführt hat.

![[heuristik.png]]
### Sequenznummer
- Jeder Request erhält eine Sequenznumer.
- Server merkt sich die schon verarbeiteten Sequenznummern.

Mögliches Vorgehen:
- Server sendet bei der ersten Verbindungsaufnahme eine Sequenznummer mit.
- Der Nächste Request muss dies Sequenznummer verwenden.
![[Sequenznummer.png]]


## Exactly-Once mit [[Transaktion]]
- Bereitstellung einer [[Persistente Kommunikation|Message Oriented Middleware]] welche Transaktionen unterstützt.
- Einsatz von 2 Transaktionsmanager.
![[exactly-once.png]]
1. Verteilte [[Transaktion]] 1 speicher Überweisung in Konten-DB und in MOM. Message in MOM nur einmal vorhanden, falls alles richtig gemacht ist.
2. Auditsystem liest und entfernt Nachricht aus MOM und speichert in Audit DB. Rollback falls etwas nicht funktionierte, dann befindet sich Message immer noch in MOM.
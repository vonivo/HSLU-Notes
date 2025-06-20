>[!Definition]
>Last wird auf mehrere Instanzen verteilt, sodass keine Instanz überlastet ist, solange noch andere Instanzen Kapazität haben.


## Round-Robin
Bei der Lastverteilung im Round-Robin-Verfahren wird eine Liste mit allen Instanzen abgearbeitet. Jede Anfrage wird nun an den Nächsten in der Liste gesendet. Am Ende der Liste wird wieder von Vorne begonnen.

- Gut für homogene Last
- Gut für homogene Systemausstattung.


## Anzahl bestehender Verbindungen
Diese Art der Lastverteilung leitet die Anfrage zu der Instanz wieder welche die geringste Anzahl an Verbindungen hat.

- Gut für langandauernde TCP-Verbindungen.

## Hash
Anwendung einer Hash-Funktion auf die IP-Adresse des Clients um die Zielinstanz zu definieren. Alle Anfragen einer IP-Adresse kommen so an dieselbe Instanz.

- Einfache Möglichkeit Requests an den gleichen Server zu senden.
- Benötigt stabile IP-Adressen.
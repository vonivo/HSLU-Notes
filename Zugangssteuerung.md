Bei der Zugangssteuerung muss der Router entscheiden, ob er einen neuen Datenfluss mit fester Ressourcenreservierung annehmen kann.

Grundlage für die Entscheidung: Fluss-Spezifikation

- Ein Sender erzeugt eine Fluss-Spezifikation und schlägt Parameter vor.
- Jeder Router ändert die Parameter gegebenenfalls ab.
- Spezifikation ist erst fix, wenn eine Bestätigung vom Server erhalten wird.


| Parameter             | Unit      |
| --------------------- | --------- |
| [[Token-Bucket]] rate | Bytes/sec |
| Token-Bucket size     | Bytes     |
| Peak data rate        | Bytes/sec |
| Minimum packet size   | Bytes     |
| Maximum packet size   | Bytes     |

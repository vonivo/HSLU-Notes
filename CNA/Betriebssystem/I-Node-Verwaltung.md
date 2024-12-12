Die I-Node Verwaltung hilft [[Blöcke]] in einem [[Dateisysteme|Dateisystem]] zu verwalten. 

Dabei erhält jede Datei eine I-Node Struktur:
- Diese enthält Dateiname, Dateiattribute und die Adressen der verschiedenen [[Blöcke]]

I-Nodes haben eine feste Länge und nur Platz für 12 [[Blöcke]]
- besteht die Datei aus weiteren Blöcken ist die letzte Adresse in der I-Node ein verweis auf einen Block mit weiteren Adressen

Nur die I-Nodes geöffneter Dateien sind im Memory


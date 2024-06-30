Der **Auslagerungsbereich** (Swap-Space) bezeichnet eine Datei oder eine Swap-[[Partition]] auf einem Massenspeicher um den RAM zu erweitern.

Empfehlung für Swap-Grössen:

| RAM             | Swap-Speicher    | Swap-Speicher wenn Ruhezustand    |
| --------------- | ---------------- | --------------------------------- |
| 2 GiB           | Zweimal das RAM  | Dreimal das RAM                   |
| 2 GiB - 8 GiB   | Gleich wie RAM   | Zweimal das RAM                   |
| 8 GiB - 64 GiB  | Mindestens 4 GiB | 1.5-facher RAM                    |
| Mehr als 64 GiB | Mindestens 4 GiB | Ruhezustand wird nicht empfohlen. |

# Swap erstellen
1. Einer [[Partition]] mit dem Dateisystem-Typ `linux-swap` erstellen
2. Swap-Signatur auf [[Partition]] erstellen `mkswap /dev/sdb1`
3. Aktivieren `swapon /dev/sdb1`
4. Automount via [[Mounting|Fstab]]

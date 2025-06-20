## Zustandslose Systeme
Bei zustandslosen Systemen sind alle Anfrage unabhängig.
- Mehrere Instanzen einer Serveranwendung starten.
- Jede Anfrage je nach Auslastung an die Instanzen verteilen.
**Einfache Lastverteilung**

## Zustandsbehaftete Systeme mit temporären Daten
- Mehrere Serverinstanzen der Serveranwendung starten.
- Erste Anfrage einer Session je nach Auslastung an eine Instanz $N$ weiterleiten.
- Folge-Anfrage der gleichen Session werden wieder an $N$ weitergeleitet.
**Komplexere Lastverteilung oft mittels Inspektion der Kommunikation**

## Zustandsbehaftete Systeme mit persistenten Daten
- Daten [[VSK/Konsitenz und Replikation/Replikation|replizieren]] (ggf. partitionieren, d.h. zwischen Instanzen aufteilen).
- Anfragen an diejenigen Instanzen der Serveranwendung verteilen welche entsprechenden Daten vorhält.
**Komplexeste Lastverteilung (read vs. write, Konsistenz der [[VSK/Konsitenz und Replikation/Replikation|Replikas]], etc.)**


![[Lastverteilung.png]]
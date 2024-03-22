#flashcards/Rechenarchitekturen 
Die Von-Neumann-Architektur folgt dem **Fetch->(Programcounter ++)->Decode-Exceute**-Cycle.


| Operation         | Beschreibung                                                                             |
| ----------------- | ---------------------------------------------------------------------------------------- |
| Fetch             | Laden des nächsten Befehls in das Befehlsregister                                        |
| Programcounter ++ | Der Programcounter (speichert die Adresse des aktuellen Befehls) wird um eins erhöht     |
| Decode            | Dekodieren des Befehls im Befehlsregister                                                |
| Execute           |  Befehl wird ausgefürt                                                                   |

Eine Von Neumannmaschine beseht aus vier Komponenten:
- Rechenwert
- Speicher
- Steuerwerk
- I/O
![[von-Neumann.png]]


Eine Genauere Auflistung der Komponenten sieht so aus:
![[vonNeuman-Detail.png]]

# Kontrollfragen
**Wird bei einem Von-Neumann-Rechner zwischen Daten- und Befehlsspeicher unterschieden?**
?
nein

**Welche Schleife durchläuft ein Rechner bei der Abarbeitung eines Befehls**
? 
Fetch/PC++/Decode/Execute
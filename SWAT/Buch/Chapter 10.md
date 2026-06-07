**What is the difference between an open layer and a closed layer?**
Ein offener Layer kann vom darüberliegenden Layer übersprungen werden, bei einem geschlossenen nicht.

**Describe the concept of *layers of isolation* and its benefits**
Layers of isolation beschriebt wenn die alle Layer closed sind und ein Layer ohne weiters ausgetauscht werden kann ohne veränderung in den darüber und darunterliegenden Layers auszlösen. Damit dies möglich ist, braucht es sauber definierte Schnittstellen.

**What is the Architecture Sinkhole antipattern**
Das ist wenn ein Aufruf einfach nur durch die Layer durchgereicht wird ohne weitere verarbeitung.

**What are some of the main architecture characteristics that would drive you to use a layerd architecutre**
- Kosten
- Einfachheit
- Responisveness

**Why isn't testability well supported in the layerd architecutre style**
Das Hauptproblem bei der Testability ist, dass immer die komplette Anwendung getestet werden muss und das oft sehr zeitintensiev ist.

**Why isn't agility well supportet in the layered architecture style?**
Dieser Style ist nicht agil, weil ein einfacher 3 Zeilen-Change die komplette Release-Zeremonie durchlaufen muss.
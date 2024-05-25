Die Queue ist eine [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]], welche Elemente in einer Warteschlange speichert.
Die Queue biete im Normalfall diese Methoden an:
- **E dequeue()** -> Returniert das Element, welches als Nächstes dran ist. (Zugriff auf **Anfang**)
- **enqueue(E e)** -> Reiht das Element in die Warteschlange mit ein. (Zugriff auf **Ende**)

Die Queue ist im Gegensatz zum [[AD/Datenstrukturen/Stack|Stack]] nach dem FIFO-Prinzipt (First-In-First-Out) aufgebaut.

## Implementation mit [[Liste]]
- Verwenden einer doppelt verketteten Liste (**konstanter** zugriff auf **head** und **tail**)
- **dequeue()**: Konstante [[Komplexität]] $O(1)$
- **enqueue()**: Konstante [[Komplexität]] $O(1)$

- Doppeltverkette Liste notwendig
- Leere Queue benötigt fast keinen Speicherplatz
- Grösse und Speicherbedarf dynamisch
- Speicheranforderung -> eher langsamer
## Implementation mit [[Array]]
- Man implementiert einen Ringbuffer so, dass man die Elemente nicht verschieben muss. (über Index und Modulo). Dabei gibt es einen Index für das erste Element (**head**) und das letzte (**tail**).
![[Ringbuffer.png]]
- **dequeue()**: Konstante [[Komplexität]] $O(1)$
- **enqueue()**: Konstante [[Komplexität]] $O(1)$

- Grösse ist beschränkt
- Maximaler Platz ist immer belegt
- Schnell

## Java Klassen
![[Queue_JCF.png]]
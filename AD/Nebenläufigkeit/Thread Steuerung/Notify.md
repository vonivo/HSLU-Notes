Um einen [[Thread]] zu signalisieren, dass er aus dem [[Wait|Wait-Pool]] aufwachen kann, werden die beiden [[Methode|Methoden]] `notify`/`notifyAll` benutzt.

Diese Methoden signalisieren den Threads, welche sich iim Wait-Pool des Lock-Objekts aufhalten, dass sie aufwachen können.

Um `notify`/`notifyAll` benutzen zu können, muss der Thread den [[Synchronized|Lock]] des Lock-Objekts besitzen.



## Notify
Die Methode `notify()` weckt **einen beliebigen** Thread aus dem Wait-Pool auf.

## NotifyAll
Die Methode `notify()` weckt **alle** Thread aus dem Wait-Pool auf.

- Es wird empfohlen, immer `notifyAll` zu verwenden, da so der gewünschte Thread aufgeweckt wird.
- NotifyAll kann die Performance des Programmes beinflusse, da alle Threads welche geweckt werden wieder Bedingungen auswerten müssen.
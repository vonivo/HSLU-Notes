Die [[Methode]] `object.wait()` versetzt den [[Thread]] in den Wait-Pool des Lock-Objekts ([[Lebenszyklus eines Threads|Wartemodus]]). Gleichzeitig wird der [[Synchronized|Lock]] des Objekts freigegeben.

Die Methode `wait` muss in einem [[Synchronized|Synchronized-Block]] aufgerufen werden.
$\implies$ Um `wait` aufzurufen, wird der **Lock des Objekts benötigt.**

**Wait-Signature:**
`public final void wait() throws InterruptedException`
`public final void wait(long timeout) throws InterruptedException`

Um einen [[Thread]] aus dem [[Lebenszyklus eines Threads|Wartemodus]] zu wecken, gibt es folgende Möglichkeiten:
- Ein anderer Thread **signalisiert** durch den Aufruf von [[Notify]] den Zustandswechsel
- Das Timeout ist abgelaufen
- Ein anderer [[Thread]] ruft einen [[AD/Nebenläufigkeit/Thread/Interrupt|Interrupt]] auf dem aktuellen [[Thread]] auf.


## Best Practice
- Die Methode `wait` immer in einer Schleife verwenden, da Threads teilweise versehentlich aufgeweckt werden.
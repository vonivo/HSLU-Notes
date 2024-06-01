Eine atomare Operation ist eine Operation, die durch den Scheduler nicht unterbrochen werden kann und verhält sich ähnlich wie [[Gegenseitiger Ausschluss]].

- In Java ist das **Lesen** und **Schreiben** auf primitive Datentypen atomar und daher **nicht unterbrechbar**.
	-> Ausnahme sind `double` und `long`.
- Zugriff auf Referenzvariablen sind immer atomar.
- Wird eine Variable als `volatile` deklariert, ist der Zugriff immer atomar.

Codemässig besteht eine Operation meist aus mehreren Schritten, welche auf den Blick als eine Operation erscheinen und daher atomar sein müssten.
**Bsp**
`counter++;`
-> In Wirklichkeit sind as aber mindestens 3 Operationen:
1. `counter` lesen.
2. Dem Registerinhalt 1 hinzufügen.
3. `counter` mit dem neuen Wert überschreiben.
-> Daher **nicht Atomar**.

Die Lösung für dieses Problem sind **Atomic Variables**.


## Atomic Variables
Atomic Variablen übernehmen den [[Gegenseitiger Ausschluss|locken]] der Ressource auf Hardware ebenen und somit extrem schnell.

Wenn zwei Threads gleichzeitig auf einen Atomic Variable zugreifen, wird ein [[Thread]] den Bus blockieren und der zweite Thread muss warten.

Für die primitiven Datentypen existieren dedizierte Klassen wie `AtomicInteger` und für komplexe Datentypen kann die Wrapperklasse `AtomicReference` genutzt werden.

### AtomicInteger
- `bool compareAndSet(int expect, int update)` -> Wenn der Inhalt mit `expect` überinstimmt, wird der neue Wert `update` gespeichert.
	- Wenn keine Übereinstimmung passiert, wird nichts gemacht.
	- der Rückgabewert `boolean` zeigt an, ob eine Modifikation vorgenommen wurde.
- `int addAndGet(int delta)` -> Wert wird um `detlta` erhöht und dann zurückgegeben.
- `int incrementAndGet()` -> Der Wert wird inkrementiert und zurückgegeben.
- `int decrementAndGet()` -> Der Wert wird dekrementiert und zurückgegeben.
Alle Methoden mit `AndGet()` können auch umgedreht werden. (bsp. `getAndIncrement()`)



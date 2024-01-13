Datenstrukturen speichern eine Menge an Daten um sie effizient zu speichern und verarbeiten zu können

Java verwendet dafür das Java Collections Framework (JCF)

Dieses besteht aus:
- [[Interface |Interfaces]]
	- Abstrakte Datentypen die es erlauben Datenstrukturen ohne eine Konkrete Implementation zu verwenden
- Implementationen
	- Konkrete Implementationen der Interfaces 
- Algorithmen
	- Methoden zur Bearbeitung der Datenstrukturen

Datenstrukturen funktionieren mit [[Polymorphie#Parametrisierte Klassen (Generics)|Generics]] und können deshalb jede Art von Objekt enthalten wenn man es mit `<Klasse>` angibt
- `List<Temperatur> = new Arraylist<>()`

## Best Practices
- Immer einen so allgemeinen [[Datentyp#Klassen Datentypen|Klassendatentyp]] wie möglich verwenden
# [[Interface|Interfaces]]
  
 - `Collection<E>` – Eine Menge von Objekten vom Typ E.   
	 - `Set<E>` – Keine Duplikate erlaubt, jedes Objekt  einzigartig.  
	- `SortedSet<E>` – Sortiertes Set (natürlich oder speziell).  
	- `List<E>` – Geordnete Menge von Objekten mit Direktzugriff.  
	- `Queue<E>` – Menge von Objekten für eine (Warte-)Schlange.  
	- `Deque<E>` (double ended queue) – Spezielle Queue mit  zusätzlichen Methoden.  
- `Map<K,V>` – Paarweise Ablage von Werten (Value) unter einem  Schlüssel (Key).  
	- `SortedMap<K,V>` – Nach Keys sortierte Map  

### Collections

Das [[Interface]] Collections enthält z.B. folgende [[Methode|Methoden]]:
- sort(…) → schnelles, stabiles sortieren
- shuffling(…) → Randomisieren der Reihenfolge
- reverse(…) → Umkehren der Reihenfolge
- fill(…) → Füllt eine Liste
- copy(…) → Kopiert eine Liste in eine andere Liste
- swap(…) → Tauscht die Plätze von zwei Listenelementen
- min/max(…) → Liefert das kleinste/grösste Element
- frequency(…) → Zählt ein bestimmtes Element in der Liste

Diese Methoden können statisch verwendet werden 
```java
final Temperatur maxima = Collections.max(list);
```

- Diese Methoden lassen isch unterteilen in 
	- Abfragemethoden (query operations)
	- Mutatormethoden (modification operations)
	- Massenverarbeitung (bulk methods)

Damit die Algorithmen einer Datenstruktur richtig funktionieren müssen zwingen [[Equals & Hashcode]] und [[compareTo & Comparable]] richtig implmentiert sein. 

#### Set
- Jedes Objekt ist nur einmal enthalten (wird per [[Equals & Hashcode]] festgelegt)
- Objekte die in ein Set eingefügt wurde sollte nicht mehr verändert werden
	- Objekte entfernen/ändern/wieder hinzufügen
- Implementationen: HashSet, LinkedHashSet, TreeSet, EnumSet

#### List
- Per Index kann direkt auf einzelne Objekte zugegriffen werden
- Geordnete → Alle Elemente behalten ihren Platz
- Kann mehrmals das gleiche Objekt enthalten
- Zero-based Index → Das erste Element hat den Index 0
- Implementationen: ==ArrayList==, LinkedList

#### Queue
- Semantik einer Warteschlange (first in first out (FIFO))
- Typische [[Methode]] 
	- offer() → Hängt ein Element am Ende an
	- poll()  → Entnimmt ein Element am Anfang
- Grösse kann statisch und begrenzt sein
- Typische Zweck → Zwischenspeicher
- Implementationen: ArrayQueque, DelayQueue, LinkedBlockingQueue, PriorityQueue

#### Deque (Double ended queue)
- Queue welche in beide Richtungen funktioniert
- Kann auch als Stack (first in last out) verwendet werden
	- push() - Element auf Stack legen
	- pop() - Element von Stack abheben
- Implementation: ArrayDeque, ConcurrentLinkedDeque, LinkedBlockingDeque, LinkedList

### Map
- Spezielle Datenstruktur für Schlüssel-Wert-Paare (key-value pairs)
	- Erlaubt die ABlage von einem Value unter einem eindeutigen Schlüssel
- Ein Schlüssel muss eindeutig sein innerhalb der Map
- Wert und Schlüssel dürfen null sein (Schlüssel nur einmal)
- Schlüsselobjekte sollten nach dem Einfügen nicht verändert werden
	- Objekte entfernen/ändern/wieder hinzufügen
- Implementationen: EnumMap, HashMap, Hashtable, Properties, TreeMap
- String als Keys sind sehr ineffizient
# Eigenschaften von Datenstrukturen
- Grösse
	- Dynamisch
	- Statisch
- Zugriff 
	- Direktzugriff 
	- Sequentiell
- Sortierung
	- Sortiert
	- Unsortiert
- Suche
	- Beschleunigte Suche
- Effizienz
	- Der Operationen (Einfügen, Anhängen, Entfernen)

# ArrayList
Die ArrayList ist die Datenstruktur welche man am meisten braucht:
- Sie ist dynamisch und passt den Platzbedarf automatisch an
- Elemente sind geordnet  (sie behalten ihren Platz), aber nicht automatisch sortiert)
- Man hat Direktzugriff auf die einzelnen Elemente `get(int index)`

```java
// Arraylist erstellen
final List<Temperatur> verlauf = new ArrayList<>();

// Element hinzufügen 
verlauf.add(new Temperatur(10f));

// Bestimmter Index setzen
verlauf.set(1, new Temperatur(20f));

```

# Iteratoren
Iterationen erlauben das iterative verarbeiten von einzelnen Elementen in einer Datenstruktur unabhängig dessen um welche Art von Datenstruktur es sich handelt.

Iterator → Kann nur vorwärts traversieren
ListIterator → Kann vorwärts und rückwärts
- Ist nur auf ausgewählten Datenstrukturen verfügbar

mit der [[Methode]] iterator() lässt sich ein Iterator beziehen:
- **Für jede neue Iteration sollte ein neuer Iterator bezogen werden**

die next() Methode auf dem iterator ist konsumieren, das heisst sie liefert eine Element und geht dann direkt weiter. 

**Ein Iterator kann auch sehr gut durch ein [[Iteration#foreach|foreach]] ersetzt werden oder durch [[Streams]]**

## Best Practices
- Während der Iteration den Inhalt der Datenstruktur nicht verändern
	- Will man ein Element während dem iteriieren entfernen verwenden man die remove() Methode auf dem Iterator
## Beispiel
Folgende Codeblock summiert alle Celcius Werte einer Liste mit Temperaturen (um danach die Durchschnittstemperatur zu berechnen)
```java
Iterator<Temperatur> iterator = temperaturen.iterator();

	while (iterator.hasNext()) {
            addedTemperatur += (float) iterator.next().getTemperaturCelcius();
    }

```

Folgender Codeblock geht durch eine Liste von Temperaturen durch und fürht auf jeder Temperatur eine [[Methode]] aus.
```java
Iterator<Temperatur> iterator = list.iterator();
while (iterator.hasNext()) {
            final Temperatur t = iterator.next();
            t.doSomething();
    }
```
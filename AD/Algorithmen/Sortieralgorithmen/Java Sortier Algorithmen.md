Damit das Sortieren und Ordnen in Java funktioniert müssen unbedingt die [[Equals & Hashcode]]-Methoden überschrieben werden.

## [[Array|Arrays]] sortieren
Arrays kännen mit den Methoden von `java.util.Arrays` sortiert werden:
 - `static void srot(int[] a)`
 - `static void srot(int[] a)`
 - `static <T> void srot(T[] a, Comparator<? super Tc)`

## [[Liste|Listen]] sortieren
Listen werden über die Klass `java.uitl.Collections` sortiert;
- `static <T extends Comparable<? super T>> void sort(List<T> list)`
- etc.

## Geordnete Collections
**für ungleiche Objekte**
- TreeSet

**für Key/Value-Paar**
- TreeMap
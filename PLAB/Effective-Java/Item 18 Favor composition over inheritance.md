[[Vererbung]] ist eine gute Möglichkeit, um Code wiederzuverwenden, falls sie richtig eingesetzt wird. 
[[Vererbung]] **bricht die Kapselung**, da eine Sub-Klasse abhängig von der Implementation der Super-Klasse ist. Wenn sich die Super-Klasse verändert, kann es sein, dass dies die Sub-Klasse kaputt macht und diese darum auch gefixt werden muss.

**Beispiel**
Die Klasse `HashSet` wird an die Klasse `InstrumentedHashSet` vererbt, welche auch noch einen Counter implementiert.
Dies funktioniert nur mit dem Wissen, wie die Super-Klasse aufgebaut ist.

**Lösung**
Diese Probleme mit [[Vererbung]] kann mittels der Komposition gelöst werden. Damit diese Komposition sauber funtkioniert, braucht es noch ein [[Methode|Methoden]]-forwarding.

Dies könnte wie folgt aussehen:
```java
public class InstrumentedSet<E> extends ForwardingSet<E> {
    private int addCount = 0;

    public InstrumentedSet(Set<E> s) {
        super(s);
    }

    @Override public boolean add(E e) {
        addCount++;
        return super.add(e);
     }
     @Override public boolean addAll(Collection<? extends E> c) {
         addCount += c.size();
         return super.addAll(c);
     }
     public int getAddCount() {
         return addCount;
     }
}

**// Reusable forwarding class**
public class ForwardingSet<E> implements Set<E> {
    private final Set<E> s;
    public ForwardingSet(Set<E> s) { this.s = s; }

    public void clear()               { s.clear();            }
    public boolean contains(Object o) { return s.contains(o); }
    public boolean isEmpty()          { return s.isEmpty();   }
    public int size()                 { return s.size();      }
    public Iterator<E> iterator()     { return s.iterator();  }
    public boolean add(E e)           { return s.add(e);      }
    public boolean remove(Object o)   { return s.remove(o);   }
    public boolean containsAll(Collection<?> c)
                                   { return s.containsAll(c); }
    public boolean addAll(Collection<? extends E> c)
                                   { return s.addAll(c);      }
    public boolean removeAll(Collection<?> c)
                                   { return s.removeAll(c);   }
    public boolean retainAll(Collection<?> c)
                                   { return s.retainAll(c);   }
    public Object[] toArray()          { return s.toArray();  }
    public <T> T[] toArray(T[] a)      { return s.toArray(a); }
    @Override public boolean equals(Object o)
                                       { return s.equals(o);  }
    @Override public int hashCode()    { return s.hashCode(); }
    @Override public String toString() { return s.toString(); }
}
```
Durch diese Lösung wird das Programm extrem flexibel, da die Wrapper-Klasse das Interface `Set<>` implementiert und als einzigen [[Konstruktor]]-[[Parameter]] ein `Set<>` annimmt.
Dies nennt man **Decorator-Pattern**.


## Vorteile
- Kapselung wird eingehalten
- Flexibel
- Keine inkonsitente Zustände möglich (Bsp. Properties)
- Robust und mächtiger
## Nachteile
- Können nicht bei Callbacks benutzt werden
- Für jedes Interface muss ein `Forwarding...`-Klasse geschrieben werden
- 
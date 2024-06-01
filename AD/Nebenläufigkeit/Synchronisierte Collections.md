Bei dem Java Collections Framework sind Collections standardmässig **nicht [[Synchronized|synchronisiert]]** um keine Performanceverlust bei Single-Threaded-Applications zu erhalten.

Um dem entgegezuwirken existieren [[Synchronized|synchronized]] Wrapperklassen.
```java
List<BankAccount> list = new ArrayList<>();
List<BankAccount> syncList = Collections.synchronizedList(list);
```

Dieses Konzept ist gut geeignet, für [[AD/Datenstrukturen/Datenstruktur|Datenstrukturen]] auf die **wenig zugegriffen** (lesend und schreibend) wird.
In der Praxis treten oft folgende Probleme auf:
- Synchronized-Collections stellen einen Engpass dar.
- Kein rein paralleles Lesen möglich.
- Inkonsistenz tritt schnell auf.
	z.B. muss eine Iteration über eine synchronisierte Collections auch synchronisiert sein, da nur der Zugriff auf die Liste selbst geschützt ist.

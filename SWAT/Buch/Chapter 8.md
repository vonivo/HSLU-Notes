**We defined the term component as a building block of an application - something the application des. A component usually consists of a group of classes or source files. How do componetns typically manifest within an application or service**
Eine Komponente manifestiert sich meistens as ein einzelnen Package oder Directory.

**What is the difference between a technical partitionaning and domain partitioning**
Partitionierung nach Domäne unterteilt die Funktionaliät anhand ihrer Domänen- /Subdomänenzugehörigkeit. Sprich alles was z.B. mit der Abwicklung der Bestellung zu hat gehört zusammen und alles was mit der Registrierung eines Benutzers zu tun hat.
Technischepartition hingegen wäre wenn wir alle DB-Enity-Klassen zusammen gruppieren, alle Controller usw.

**What is the advantage of domain partitioning**
Die gesamte Codebase ist einfach zu lesen/verstehenda man die logischen Komponenten viel besser sieht. Es führt auch zu besserer Wartbarkeit da zufällige Kopplung minimiert werden kann.

**Under what circusmstances would technical partitioning be a better choice than domain partitioning?**
Wenn eine sehr kleine Applikation entwicklet werden muss oder als Startpunkt ist die technische Partitionierung keine schlechte Option.

**What is the Entity Trap. Why is it not a good approach for component identification**
Die Entity-Trap ist wenn beim erstellen der Komponenten zuerst auf die Domain-Entities fokussiert wird. Hat man die Core-Entities werden alle funktionaliäten welche die Entity betreffen oft zu einer "Manager"-Componente oder ähnliches zusammengefasst.
Dies ist aus folgenden Gründen suboptimal:
1. Der Name der Komponente ist viel zu generisch und daruch unverständlich.
2. Die Komponenten sind oft sehr augebläht und ähneln eher einer sehr grossen Uitility-Sammlung als sich auf eine Sache zu fokussieren.
3. Die Komponente werden zu gorss und verlieren an Wartbarkeit

**When might you choose the Workflow approach over the Actor/Action approach when identifying core components**
Der Actor-Approach generiert meistens mehr Komponenten.
Der Worklfow-Approach wird eher gewählt, wenn der Businessprozess wichtiger ist als der Aktor.
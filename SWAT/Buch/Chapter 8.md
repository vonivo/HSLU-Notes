**We defined the term component as a building block of an application - something the application des. A component usually consists of a group of classes or source files. How do componetns typically manifest within an application or service**
Eine Komponente manifestiert sich meistens as ein einzelnen Package oder Directory.

**What is the difference between a technical partitionaning and domain partitioning**
Partitionierung nach Domäne unterteilt die Funktionaliät anhand ihrer Domänen- /Subdomänenzugehörigkeit. Sprich alles was z.B. mit der Abwicklung der Bestellung zu tun hat gehört zusammen und alles was mit der Registrierung eines Benutzers zu tun hat.
Technischepartition hingegen wäre wenn wir alle DB-Enity-Klassen zusammen gruppieren, alle Controller usw.

**What is the advantage of domain partitioning**
Die gesamte Codebase ist einfach zu lesen/verstehen da man die logischen Komponenten viel besser sieht. Es führt auch zu besserer Wartbarkeit da zufällige Kopplung minimiert werden kann.
Neben der besseren Lesbarkeit und Wartbarkeit nennt das Buch als Hauptvorteile, dass die Architektur näher an der tatsächlichen Arbeitsweise des Business modelliert ist, es viel einfacher ist, cross-funktionale Teams darum herum zu bilden, und es spätere Migrationen zu verteilten Systemen (wie Microservices) stark vereinfacht

**Under what circusmstances would technical partitioning be a better choice than domain partitioning?**
Kleine Anwendungen oder strikte Budgets/Zeitpläne profitieren von der Einfachheit. Ein weiterer im Buch genannter Grund ist, dass technische Partitionierung extrem gut darin ist, kundenspezifischen Code (Customization) sauber abzutrennen (z.B. Common Code vs. Local Code) und sie die Grundlage für die klassische Layered Architecture bildet

**What is the Entity Trap. Why is it not a good approach for component identification**
Die Entity-Trap ist wenn beim erstellen der Komponenten zuerst auf die Domain-Entities fokussiert wird. Hat man die Core-Entities werden alle funktionaliäten welche die Entity betreffen oft zu einer "Manager"-Componente oder ähnliches zusammengefasst.
Dies ist aus folgenden Gründen suboptimal:
1. Der Name der Komponente ist viel zu generisch und daruch unverständlich.
2. Die Komponenten sind oft sehr augebläht und ähneln eher einer sehr grossen Uitility-Sammlung als sich auf eine Sache zu fokussieren.
3. Die Komponente werden zu gorss und verlieren an Wartbarkeit

**When might you choose the Workflow approach over the Actor/Action approach when identifying core components**
Der Actor-Approach generiert meistens mehr Komponenten.
Der Worklfow-Approach wird eher gewählt, wenn der Businessprozess wichtiger ist als der Aktor.
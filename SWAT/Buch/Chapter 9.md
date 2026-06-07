**List the eight fallacies of distributet computing**
1. Das Netzwerk ist reliable
2. Latenz ist null
3. Es existiert unlimitierte Bandbreite
4. Das Netzwerk ist sicher
5. Das Netzwerk ändert nicht
6. Es existiert nur ein Admin
7. Transportkosten sind null
8. Das Netzwerk ist homogen
Encore:
9. Versionierung ist einfach
10. Kompensationsupdates funktionieren immer
11. Obersabilit ist optional

**Name three challenges that distributed architectures have that monolithic architectures don't**
1. Verfügbarkeit der einzlenen Services
2. Datenqualität und Konsistenz
3. Auslieferungsgarantien
4. Latenz

**What is stamp coupling? What are some ways of addressing stamp coupling?**
Stamp-Coupling bezeichnet das Verhalten ein Service gewisse Daten eines anderen Abfrägt und dann viel mehr Felder als nötig erhält. Dies kann z.B. mit GraphQL, privaten APIs, Feld-Selektoren, value-driven contracts mit conusmer drive-contracts oder internen messaging endpoints vorgebeugt werden.

**What is the difference between technical versus domain partitioning?**
Partitionierung nach Domäne unterteilt die Funktionaliät anhand ihrer Domänen- /Subdomänenzugehörigkeit. Sprich alles was z.B. mit der Abwicklung der Bestellung zu hat gehört zusammen und alles was mit der Registrierung eines Benutzers zu tun hat.

**List three characteristics that distinguish an architectureal style form a pattern.**
Ein Architektur-Style beschreibt eher:
- Dy Physische Architektur
- Das Deployment
- Componenten Topology
- Kommunikations-Style
- Daten-Topologie
Ein Pattern hingegen ist eine kontextualisierte Lösung zu einem bestimmten Problem.
[[Immutable Objects]] sind Objekte welche nicht verändert werden können.

## Klasse Immutable machen
1. Keine Zustandsveränderenden [[Methode|Methoden]] anbieten.
2. Sicherstellen, dass die Klasse nicht verändert werden kann
3. Alle [[Attribut|Attribute]] `final` machen
4. Alle [[Attribut|Attribute]] `private` machen
5. Keine Objektreferenzen zu Mutable-Objekte exponieren

Da immutable Klassen nicht so gute Perfomance habe kann dies über:
- Lazy initialization
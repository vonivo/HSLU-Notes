Der `for-each`-Loop bringt die Vorteile von **Lesbarkeit, Flexibilität und Fehlerprävention** bei keiner Performance-Einbusse. Daher sollte, wo immer möglich, der `for-each`-Loop benutzt werden.

## Beispiel
**Iterieren über einen Iterator**
```java
for (Iterator<Element> i = c.iterator(); i.hasNext(); ) {
    Element e = i.next();
    ... // Do something with e
}
```
**Iterieren über Index**
```java
for (int i = 0; i < a.length; i++) {
    ... // Do something with a[i]
}
```
**Iterieren mittel `for-each`**
```java
for (Element e : elements) {
    ... // Do something with e
}
```

### Beispiel für einen Fehler
```java
List<Card> deck = new ArrayList<>();
for (Iterator<Suit> i = suits.iterator(); i.hasNext(); ) {
    for (Iterator<Rank> j = ranks.iterator(); j.hasNext(); ) {
        deck.add(new Card(i.next(), j.next()));
	}
}
```
Hier wird `i.next()` viel zu oft aufgerufen, richtig wäre:
```java
List<Card> deck = new ArrayList<>();
for (Iterator<Suit> i = suits.iterator(); i.hasNext(); ) {
	Suit suit = i.net();
    for (Iterator<Rank> j = ranks.iterator(); j.hasNext(); ) {
        deck.add(new Card(suit, j.next()));
	}
}
```

**Mittels `for-each`**
```java
for (Suit suit : suits) {
    for (Rank rank : ranks) {
        deck.add(new Card(suit, rank));
	}
}
```

## Schwachstellen
`for-each` kann nicht angewant werden bei:
- **destruktivem Filtern**
	Muss über einen expliziten `Iterator` gemacht werden (über dessen `remove()`). Kann teilweise mittels `Collection.removeIf()` umgangen werden.
- **transformieren**
	Muss über Index respektive `Iterator` gemacht werden
- **paralleler Iteration**
	Muss über `Iteraotr` gemacht werden da explizite Kontrolle über diesen benötigt wird.
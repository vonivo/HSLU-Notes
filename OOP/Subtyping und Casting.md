Subtyping und Casting sind ein zentrales Konzept der [[Polymorphie]]
# Subtyping
- [[Vererbung]]
	- Unterklasse ist ein Subtyp der Oberklasse
- [[Interface|Interfaces]]
	- Implementierende [[Klasse]] ist ein Subtyp des [[Interface|Interfaces]]
	
Jede Reverenzvariable kann nicht nur Objekte des deklarierten Typs aufnehmen sondern auch alle Subtypen.

Ein Objekt hat einen **statischen Typ** und einen **dynamischen Typ**
- Statischer Typ → Typ von z.B. einer Variable welcher zum Programmierzeitpunkt festgelegt wird (Verpackung)
- Dynamischer Typ → Tatsächlicher Typ des Objektes
## Beispiel
Sowohl ein Circle als auch ein Rectangle sind eine Shape und können in eine Shape “verpackt” werden. Innerlich bleiben sie aber Circle und Rectangle Objekte. Shape ist hier der statische Typ und Rectangle/CIrcle der dynamische. 

```java
Shape shape1 = new Circle();
Shape shape2 = new Rectangle();
```

# Casting
Als Casting bezeichnet man die Konvertierung von einem Typen zum anderen. Ein Cast verändert nie den dynamischen Typ des Objekts sondern nur den Typ der Referenz (statisch).

## Upcasting → Vom Subtyp zum Typ 
- Funktioniert immer 
- findet implizit statt kann aber auch explizit angegeben werden

```java
// implizites Casting
Shape shape1 = new Rectangle();
// explizites Casting (nicht zwingend notwendig)
Shape shape2 = (Shape) new Rectangle();
```

## Downcasting → Vom Typ zum Subtyp
- Funktioniert nicht immer 
	- Dynamische Typ des Objekts muss kompatibel sein
- **Muss immer explizit erfolgen**

```java
// Voraussetzung 
Object object = new Rectangle();

// Erlaubte Downcastings
Shape shape = (Shape) object;
Rectangle rectangle = (Rectangle) object;

// Nicht erlaubte Downcastings
Circle circle = (Circle) object;
Person person = (Person) object;
```

## Elementare [[Datentyp|Datentypen]]
Auch Elementare Datentypen können gecastet werden. 

Folgende elementaren Datentypen können implizit gecastet werden:

| von | nach |
| ---- | ---- |
| byte | short, int, long, float, double |
| char, short | int, long, float, double |
| int | long, float, double |
| float | double |
| Alle | String (wenn sie mit einem anderen String verbunden werden) |
**Dabei kann es zu Genauigkeitsverlusten kommen**

Um Beispielsweise ein long in ein int zu casten müsste das explizit erfolgen (downcasting), da man sich nicht sicher sein kann das der long in den int passt. 
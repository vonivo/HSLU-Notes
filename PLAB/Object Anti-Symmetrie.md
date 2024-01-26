Es wird klar unterschieden in Objekte und Datenstrukturen.

**Objekte** verstecken ihre Daten hinter Abstraktion und stellen [[Methode|Methoden]] zur Verfügung, welche anhand dieser Daten Operationen durchführen.
**Datenstrukturen** exponieren ihre Daten und stellen keine signifikanten [[Methode|Methoden]] zur Verfügung.

**Objekte** sind also genau das Gegenteil von **Datenstrukturen**.

>[!info]
>**Prozedurale Programmierung** (mit Datenstrukturen) macht es einfach neue Funktionen hinzuzufügen, ohne die bestehenden Datenstrukturen zu ändern.
>**Objektorientierte Programmierung** macht es einfach neue Klassen hinzuzufügen, ohne bestehende Funktionen zu verändern.
>
>Das Ganze kann auch umgekehrt werden:
>**Prozedurale Programmierung** (mit Datenstrukturen) macht schwierig neue Datenstrukturen hinzuzufügen, da alle Funktionen angepasst werden müssen.
>**Objektorientierte Programmierung** macht es schwierig neue Funktionen hinzuzufügen, da alle Klassen angepasst werden müssen.


Darum sollte stets vermieden werden **Datenstrukturen und Objekte zu mischen**. Entweder sollte eine [[Klasse]] eine **Datenstruktur** sein oder ein **Objekt**.


## Prozedurale Programmierung
**Klassen**
```java
public class Square {  
     public Point topLeft;  
     public double side;  
   }  
  
   public class Rectangle {  
     public Point topLeft;  
     public double height;  
     public double width;  
   }  
  
   public class Circle {  
     public Point center;  
     public double radius;  
   }
```
**Prozedur**
```java
public class GemoentryFunctions {  
     public final double PI = 3.141;  
  
     public double area(Object shape) throws NoSuchShapeException  
     {  
       if (shape instanceof Square) {  
         Square s = (Square)shape;  
         return s.side * s.side;  
       }  
  
       else if (shape instanceof Rectangle) {  
         Rectangle r = (Rectangle)shape;  
         return r.height * r.width;  
       }  
       else if (shape instanceof Circle) {  
         Circle c = (Circle)shape;  
         return PI * c.radius * c.radius;  
       }  
       throw new NoSuchShapeException();  
     }  
   }
```
Wenn in diesem Beispiel eine neue [[Methode|Methoden]]  z. B. für die Oberfläche einer `Shape` erstellt werden muss, muss nur die Prozedur angepasst werden. Die verschiedenen `Shapes` bleiben unverändert.

Falls jedoch eine neue `Shape`-[[Klasse]] hinzugefügt wird, müssen alle [[Methode|Methoden]] innerhalb der Prozedur angepasst werden.

## Objektorientierte Programmierung
**Klassen**
```java
public class Square implements Shape {  
	private double side;  
	
	@Override
    public double area() {  
      return side*side;  
    }  
}  
  
public class Rectangle implements Shape {   
	private double height;  
	private double width;  
    
    @Override
	public double area() {  
		return height * width;  
	}  
}  
  
public class Circle implements Shape {  
	private double radius;  
	public final double PI = 3.141592653589793;  

	@Override
	public double area() {  
		return PI * radius * radius;  
	}  
}
```
Nun wird keine Prozedur mehr benötigt.
Wenn nun eine neue [[Klasse]] hinzugefügt wird, können alle anderen Klassen unverändert bleiben. Wenn jedoch einen neue [[Methode|Methoden]] dazukommt, müssen alle Klassen abgegändert werden.

Das Liskov Substitutions-Prinzip besagt, dass ein Objekt der [[Klasse]] `X` durch ein Objekt der [[Klasse]] `Y`, welches eine Subklasse von `X` ist, ausgetauscht werden kann, ohne dass sich das Verhalten des Programms verändert.

## Beispiel
```java
public class Rectangle {
	private int height;
	private int width;

	public Rectangle(int, height, int width) {...}

	// getters and Setters

	public int area() {
		return height * width;
	}
}

public class Square extends Rectangle {

	@Override
	public void setHeight(int height) {
		this.height = height;
		this.width = height;
	}

	@Override
	public void setWidth(int width) {
		this.height = width;
		this.width = width;
	}
}
```
Wir haben die [[Klasse]] Rechteck und die [[Klasse]] Quadrat welche von Rechteck [[Vererbung|erbt]].
Die [[Klasse]] Quadrat stellt sicher, dass die Seite gleich lang ist wie die Länge.

```java
public void increaseWidthByOne(Rectangle rectangle) {
	rectangle.setWidth(rectangle.getWidth() + 1);
}

Rectangle rectangle1 = new Rectangle(2, 10);
Rectangle rectangle2 = new Rectangle(5, 5);

increaseWidthByOne(rectangle1);
increaseWidthByOne(rectangle2);

System.out.println(rectangle1.area());
System.out.println(rectangle2.area());
```
Dieses Programm würde nun einmal 22 ausgeben (2 * (10+1)) und 30 (5 * (5+1)).
Wenn man nun genau hinschaut ist `rectangle2` ein Quadrat, also tauschen wir das aus:

```java
public void increaseWidthByOne(Rectangle rectangle) {
	rectangle.setWidth(rectangle.getWidth() + 1);
}

Rectangle rectangle1 = new Rectangle(2, 10);
Rectangle rectangle2 = new Square(5, 5);

increaseWidthByOne(rectangle1);
increaseWidthByOne(rectangle2);

System.out.println(rectangle1.area());
System.out.println(rectangle2.area());
```
Nun werden wir aber die Ausgaben 22 und 36 bekommen.

Weil `rectanlge2` jetzt ein Quadrat ist, wird auch die Höhe um eins erhöht und wir bekommen $6\cdot 6 = 36$. 

Hier ist das **LSP verletzt**.
[[Konstruktor|Konstruktoren]] und [[Item 1 Consider static factory methods instead of constructors|statische Factory-Methoden]] skalieren nicht gut mit vielen optionalen [[Parameter]].

Traditionell wird dafür Teleskopkonstruktoren verwendet. Dies beinhaltet einen [[Konstruktor]] welcher alle Mandatory-[[Parameter]] hat und viele weitere für die optionalen [[Parameter]], welche dann untereinander verkettet werden. Dabei wird immer der [[Konstruktor]] mit allen [[Parameter]] als "richtiger [[Konstruktor]]" angesehen.
Dadurch kann der Benutzer gezwungen werden einen [[Konstruktor]] aufzurufen bei dem er viele [[Parameter]] einfach so mitgeben muss.

**Nachteile**
- Schwer zu Schreiben
- und noch schwerer zu lesen.

## Java Beans Pattern
Es gibt die Alternative des Java-Beans-Pattern welche einen Default [[Konstruktor]] aufruft und danach die Werte über Set-Methoden setzt.
=> Kann sein, dass sich das Objekt in **inkonsistentem** Zustand befindet.
=> Nicht Immutable


## Builder Pattern
Bei der Builder-Alternative wird zuerst eine [[Item 1 Consider static factory methods instead of constructors|statische Factory-Methode]] oder einen [[Konstruktor]] mit den  Mandatory-[[Parameter]] aufgerufen. Anstatt direkt das gewünschte Objekt zu erhalten wird ein `Builder`-Objekt zurückgegeben auf dem dann optionalen [[Parameter]] gesetzt werden können. Mit der `build`-[[Methode]] wird dann das richtige Objekt erstellt.

```java
public class NutritionFacts {
    private final int servingSize;
    private final int servings;
    private final int calories;
    private final int fat;
    private final int sodium;
    private final int carbohydrate;

    public static class Builder {
        // Required parameters
        private final int servingSize;
        private final int servings;

        // Optional parameters - initialized to default values
        private int calories      = 0;
        private int fat           = 0;
        private int sodium        = 0;
        private int carbohydrate  = 0;

        public Builder(int servingSize, int servings) {
            this.servingSize = servingSize;
            this.servings    = servings;
        }

        public Builder calories(int val)
            { calories = val;      return this; }
        public Builder fat(int val)
            { fat = val;           return this; }
        public Builder sodium(int val)
            { sodium = val;        return this; }
        public Builder carbohydrate(int val)
            { carbohydrate = val;  return this; }

        public NutritionFacts build() {
            return new NutritionFacts(this);
        }
    }

    private NutritionFacts(Builder builder) {
        servingSize  = builder.servingSize;
        servings     = builder.servings;
        calories     = builder.calories;
        fat          = builder.fat;
        sodium       = builder.sodium;
        carbohydrate = builder.carbohydrate;
    }
}
```
Dadurch dass bei den Optionalen-[[Parameter]]-Methoden das Builder-Objekt zurückgegeben wird, ergibt es eine **fluent API**.
```java
NutritionFacts cocaCola = new NutritionFacts.Builder(240, 8)
        .calories(100).sodium(35).carbohydrate(27).build();
```

### Vorteile
- Lesbarer
- Simuliert benannte optionale [[Parameter]]
- Eignet sich gut für Klassenhierarchie
```java
public abstract class Pizza {
   public enum Topping { HAM, MUSHROOM, ONION, PEPPER, SAUSAGE }
   final Set<Topping> toppings;

   abstract static class **Builder<T extends Builder<T>>** {
      EnumSet<Topping> toppings = EnumSet.noneOf(Topping.class);
      public T addTopping(Topping topping) {
         toppings.add(Objects.requireNonNull(topping));
         **return self();**
      }

      abstract Pizza build();

      // Subclasses must override this method to return "this"
      rotected abstract T self();
   }
   Pizza(Builder<?> builder) {
      toppings = builder.toppings.clone(); // See Item  50
   }
}
```
- Kann mehrere Varargs enthalten

### Nachteile
- Um ein Objekt zu erstellen muss zuerst der Builder erstellt werden -> kann Performance Auswirkungen haben
- Gibt mehr aufwand, sollte daher ab 4 oder mehr optionalen Parametern verwendet werden.
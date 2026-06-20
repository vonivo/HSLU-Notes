Zur Realiseriung des Datentyps Array.
**API**
```java
function Array new(int size)
method void dispose()
```

- `new` **nicht als Konstrukotr** implementieren. Die Implementierung muss `Memory.alloc` aufrufen.
- `dispose` muss `Memory.deAlloc` aufrufen.

## Definition
Ein fehlschlagender Methodenaufruf sollte das Objekt in dem Status belassen, indem es vor dem aufruft war. Dadurch wird verhindert, dass sich das Objekt in einem inkonsistenten Zustand befindet. (**Gilt vor allem für [[Exceptionhandling#Arten von Fehlern|checked Exceptions]]**.)

Teilweise kann Failure Atomicity nicht erreicht werden (Beispielsweise bei verschieden Threads).
Es kann auch vorkommen, dass Failure Atomicity nicht erwünscht ist, wenn dafür die Kosten und die Komplexität zu gross sind, wenn das der Fall ist **sollte dies jedoch dokumentiert werden.**
## Beispiel
```java
public Object pop() {
    Object result = elements[--size];
    elements[size] = null;
    return result;
}
```
Diese `pop`-[[Methode]] aus einem Stack kann die `ArrayIndexOutOfBoundsException` produzieren. Dies passiert, wenn die `size` z.B. `null` ist. Passiert dies, wird die `size` jedoch negativ und die `pop`-Methode wird jetzt **immer einen Fehler produzieren**.

### Mit failure Atomicity
```java
public Object pop() {
	if (size == 0) {
		throw new EmptyStackException();
	}
    Object result = elements[--size];
    elements[size] = null;
    return result;
}
```

## Lösung um Failure Atomicity zu erreichen
1. Das Benutzen von [[Immutable Objects]].
2. [[Parameter]] einer Operation vor der Objektmanipulation zu überprüfen.
3. Alle Operationen welche fehlschlagen könnten vor der Objektmanipulation durchführen
4. Die Operation an einer temporären Kopie durchzuführen
5. Recovery-Code zu schreibe (Wird nicht oft benutzt, nur bei disk-based Systeme)



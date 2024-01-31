Wenn die **`hashCode`** ([[Equals & Hashcode#Hashcode|HashCode-Methode]]) **muss zwingend** überschrieben werden, wenn die **`equals`**([[Equals & Hashcode#equals|Equals-Methode]]) auch überschrieben wird. Ansosnten kann es sein, dass die Klasse in Collections wie `HashMap` und `HashSet` nicht mehr richtig funktioniert.

**Beispiel**
```java
Map<PhoneNumber, String> m = new HashMap<>();
m.put(new PhoneNumber(707, 867, 5309), "Jenny");
map.get(new PhoneNumber(707, 867, 5309))
```
Dieses Statement sollte eigentlich `Jenny` ergeben, da aber in der Klasse `PhoneNumber` nur die `equals`-Methode überschrieben wurde, sucht die `HashMap` im falschen Hashbucket und es wird `null` zurückgegeben.

## HashCode-Implementation
### Variante 1
```java
@Override public int hashCode() {
    int result = Short.hashCode(areaCode);
    result = 31 * result + Short.hashCode(prefix);
    result = 31 * result + Short.hashCode(lineNum);
    return result;
}
```
Diese Variante ist sehr schnell, jedoch etwas mühsam zu erstellen

### Variante 2
Man kann auch `com.google.common.hash.Hashing` von der Libaray Guava verwenden. Bringt weniger Kollisionen mit sich

### Variante 3
```java
@Override public int hashCode() {
   return Objects.hash(lineNum, prefix, areaCode);
}
```
Funktioniert gut, ist jedoch etwas langsamer, da aus den Elementen ein Array erstellt wird und es ein Auto-Boxing machen muss
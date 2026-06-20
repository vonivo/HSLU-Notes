Zur Realisierung des Datentyps String.

**API**
```java
constructor String new(int maxLength);
method void dispose();
method int length();
method char charAt();
method void setCharAt(int j, char c);
method String appendChar(char c);
method void eraseLastChar();
method int intValue();
method void setInt(int j);
method char backSpace();
method char doubleQuote();
method char newLine();
```

**Gebrauch**
![[Pasted image 20260620145506.png]]

## int zu string
```java
/* Returns the string representation of a non-negative int*/
int2String(int val):
	lastDigit = val % 10;
	c = character representing lastDigit
	if (val < 10)
		return c (as string)
	else
		return int2String(val/10).append(c)
```

## string zu int
```java
string2Int(String str):
	val = 0;
	for(i=0...str.length) do:
		d = integer value of str[i]
		val = val*10+d
	return val
```

## Notes
- `length`, `charAt`, `setCharAt`, `appenChar`, `eraseChar` mit Arraymanipulation implementieren.
- `newLine`, `backSpace`, `doubleQuote` Implementierung durch Rückgabe der int-Werte `128,129,34`
- 
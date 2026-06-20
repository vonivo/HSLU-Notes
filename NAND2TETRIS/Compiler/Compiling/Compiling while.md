Auch bei der Kompilation von While wird derselbe Trick wie bei [[Compiling if]] verwendet.

```java
while(expression) {
	...statements...
}
```
wird zu: 
```
label L1
// VM Code by compileExpression
neg
if-goto L2
	//VM Code by compileStatements
	goto L1
label L2
```

**Pseudocode**
![[Pasted image 20260620111251.png]]

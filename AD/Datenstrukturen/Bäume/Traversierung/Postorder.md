Bei der Postorder Traversierung wird zuerst der linke Kind-Knoten eines  [[Binäre Bäume|binären Baumes]], dann rechte Kind-Knoten und am Schluss der eigentliche Konten verarbeitet.
Diese Reihenfolge wird **Nebenreihenfolge** genannt.

## Algorithmus
1. Traversiere den linken Teilbaum von x gemäss `preorder(x.getLeftChild())`.
2. Traversiere den rechten Teilbaum von x gemäss `preorder(x.getRightChild())`.
3. Besuchen (verarbeiten) den Knoten x.

### Implementation
```java
public static void postOrder(Node x) {
	// traves left
	postOrder(x.getLeftChild());

	// traverse right
	postOrder(x.getRightChild());

	// do some Calculationw with x
	System.out.println(x);
}
```
### Beispiel
![[TreeTraversion_postOrder.png]]
Die Nummer gibt an, in welcher Reihenfolge die Knoten besucht wurden.
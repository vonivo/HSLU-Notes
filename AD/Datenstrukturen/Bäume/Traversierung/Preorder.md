Bei der Preorder Traversierung werden die Knoten eines [[Binäre Bäume|binären Baumes]] zuerst verarbeitet und dann wird mit den **linken** und anschließend den **rechten**.
Wird als **Hauptreihenfolge** bezeichnet.

## Algorithmus
1. Besuchen (verarbeiten) den Knoten x.
2. Traversiere den linken Teilbaum von x gemäss `preorder(x.getLeftChild())`.
3. Traversiere den rechten Teilbaum von x gemäss `preorder(x.getRightChild())`.

### Implementation
```java
public static void preOrder(Node x) {
	// do some Calculationw with x
	System.out.println(x);

	// traves left
	preOrder(x.getLeftChild());

	// traverse right
	preOrder(x.getRightChild());
}
```

### Beispiel
![[TreeTaversion_preorder.png]]
Die Nummer gibt an, in welcher Reihenfolge die Knoten besucht wurden.
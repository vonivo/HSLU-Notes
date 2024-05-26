Bei der Inorder Traversierung wird zuerst der linke Kind-Knoten eines [[Binäre Bäume|binären Baumes]] besucht, dann der Knoten bearbeite und am Schluss der rechte Kind-Knoten besucht.
Diese Reihenfolge wird **symmetrische Reihenfolge** genannt.

## Algorithmus
1. Traversiere den linken Teilbaum von x gemäss `preorder(x.getLeftChild())`.
2. Besuchen (verarbeiten) den Knoten x.
3. Traversiere den rechten Teilbaum von x gemäss `preorder(x.getRightChild())`.


### Implementation
```java
public static void inOrder(Node x) {
	// traves left
	inOrder(x.getLeftChild());
	
	// do some Calculationw with x
	System.out.println(x);
	
	// traverse right
	inOrder(x.getRightChild());
}
```
### Beispiel
![[TreeTraversion_inorder.png]]
Die Nummer gibt an, in welcher Reihenfolge die Knoten besucht wurden.

Bei einem [[Binärer Suchbaum|binärem Suchbaum]] liefert die **Inorder**-Reihenfolge die enthaltenen Elemente gemäss ihrer Einordnung/**Sortierung** von links nach rechts.
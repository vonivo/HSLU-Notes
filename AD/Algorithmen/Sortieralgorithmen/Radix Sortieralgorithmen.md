Radix [[Sortieralgorithmus|Sortieralgorithmen]] bedingen spezielle Anforderungen an die Schlüssel und finden daher entsprechend **selten Verwendung**.

## Beispiel
Daten: D1, D2, D3, D4 ($n=4$).
Als Schlüssel kommt genau jeder int-Wert $1\dots n$ genau einmal vor.
$\implies$ \[D1/**2**, D2/4, D3/1, D4/3\]
Die Schlüssel geben somit direkt die Reihenfolge für die Sortierung an: \[D3/**1**, D1/**2**, D4/**3**, D2/**4**].

Damit ist gezeigt, dass sich Radix Sortieralgorithmen **bestenfalls** in $O(n)$ lösen lassen.

**Beispiele:**
- Counting-Sort
- Radix-Sort
- Bucket-Sort

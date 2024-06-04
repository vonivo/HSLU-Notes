Der Heapsort ist ien [[Vergleichsbasierte Sortieralgorithmen|vergleichsbasierter Sortieralgorithmus]] welcher sich die [[AD/Datenstrukturen/Datenstruktur|Datenstruktur]] [[Heap]] zunutze macht.

Heapsort arbeitet [[Sortieralgorithmus#Stabilität|instabil]] mit einer generellen [[AD/Algorithmen/Komplexität|Komplexität]] von $O(n\log n)$.

## Prinzip
1. [[Heap]] aufbauen: Man fügt $n$ Mal mit `insert()` ein Element in den Heap ein => $O(n\log n)$. (Ist etwas geschickter sogar mit $O(n)$ möglich)
2. Elemente sortieren: Man entnimmt $n$ Mal mit `getMax()` aus dem schwinden [[Heap]] das grössete Elment => $O(n\log n)$.
=> [[AD/Algorithmen/Komplexität|Komplexität]] von $2\times O(n\log n) \implies O(n\log n)$.

![[HeapSort_Stages.png]]


Durch geschicktes implementieren, braucht der Heapsort keinen zusätzlichen Speicherplatz und hat somit eine Speicherkomplexität von $O(n)$.
Ein Heap ist ein [[Binäre Bäume|binärer Baum]] mit strukturellen Bedingungen:
- Der Baum muss [[Füllgrad eines Baumes#Voll|voll]] sein
und einer inhaltlichen Bedingung:
- Jeder Knoten ist $\geq$ seine Kinder
und ist in einem [[Array]] abgespeichert.

=> An der Wurzel befindet sich das grösste Element

![[Heap.png]]
## Speicherung
Der Heap wird in einem [[Array]] gespeichert:![[heap_array.png]]
Navigiert wird wie Folgt:
**Fater finden**
$\frac{Index -1}{2} = \text{Fater Index}$

**Linker Sohn**
$\text{Linker Sohn}=(2\times i)+1$

**Rechter Sohn**
$\text{Rechter Sohn}=2\times(i+ 1)$


## Operationen
### GetMax
Nach dem Entfernen des Wurzel-Elements wird das Letze blatt im Array als neue Wurzel definiert. Damit wurde die strukturelle Bedingung (voll) erfüllt.
![[Heap_getMax_1.png]]
=> [[AD/Algorithmen/Komplexität|Komplexität]] vom $O(1)$.

Damit die inhaltliche Bedingung auch erfüllt ist, muss nun ein Sinkprozess gemacht werden.
#### Sinkprozess
1. Wähle das Grössere Kind des akutellen Knoten (wenn kein rechtes Kind wähle das link, wenn keine Kinder mehr -> terminiere).
2. Überprüfe ob das gewählte Kind grösser ist als der aktuelle Knoten
	- Wenn ja -> vertauschen und bei 1. weitermachen
	- Wenn nein -> fertig.
![[Heap_getMax_sinking.png]]

=> Damit resultiert eine Komplexität von $O(1) + O(\log_{2}n) \implies O(\log n)$

### Insert
Bei Einfüge wird der neue Wert in den nächsten freien Platz im Array gesetzt.
Dadruch ist gewährleistet, dass die strukturelle Bedingung erfüllt ist.
Danach erfolgt der sogenannte Steigprozess.
![[Heap_insert.png]]

#### Steigprozess
Der Stegiprozess verläuft so:
1. Vater-Knoten ermitteln
2. Wenn eingefügtes Element grösser ist als der Vater-Knoten tauschen (weiter mit 1.)
![[Heap_insert_rise.png]]

=>[[AD/Algorithmen/Komplexität|Komplexität]] vom $O(1) + O(\log n) \implies O(n\log n)$

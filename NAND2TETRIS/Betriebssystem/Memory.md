Handelt Memory-Zugriff auf RAM.

**API**
```java
function int peek(int address);
function void poke(int address, int value);
function Array alloc(int size)
function void deAlloc(Array o)
```


- Highlevel-Programme benötigen direkten Zugriff auf einzelne Wörter im RAM.
- Das Betriebssystem soll Lowlevel-Dienste bereitstellen, die den direkten RAM-Zugriff erleichtern.
	- peek
	- poke

**Beispiel**
```java
let x = Memory.peek(19003)         // z.B. x = 7
do Memory.poke(19003, -1)          // RAM[19003] = 1111...1
```


## Implementation
### Peek und Poke
```java
class Memory {
	static Array ram;

	function void init() {
		let ram = 0;
	}
	
	function int peek(int address) {
		return ram[address];
	}

	function void poke(int address, int val) {
		ram[address] = val;
	}
}
```
>[!Info]
>Durch diesen Trick wird der gesammte RAM als einziges Array zur Verfügung gestellt. Dies funktioniert nur, da [[JACK]] schwach typisiert ist.

### Alloc und DeAloc
Der Freie Heap verwaltet werden kann, wird eine Verkettte-Liste verwendet, welche die Freien Segmente verkettet. Dadruch wird aber pro Segment 2-Wörter "geopfert" welche die Meta-Daten:
- `next`
- `size`
enthalten.
![[Pasted image 20260620140303.png]]

Nun findet `alloc` ein Segment der Grösse `size+2` in einem der Segmente, entfernt ihn aus dem Segment und gibt dann die Baseadresse an den Client weiter. (Hier können verschiedene Strategien genutzt werden. z.B. `first fit` oder `best fit`)

`deAlloc`
Hängt das Objet/den Block an die FreeList an.

Je mehr `deAlloc` aufgerufen wird, dest fragmentierter wird der Heap. Dies kann durch defragmentierung behoben werden.

```java
class Memory {
	static Array heap;
	static Array freeList;

	function void init() {
		let heap = 2048;
		let freeList = heap;
		let heap[0]=0;
		let heap[1]=14334;
	}
	
	function int alloc(int size) {
		Search freeList using best-fit or first-fit heuristics 
			to obtain a segment with segment.length > size 
		If no such segment is found, return failure 
			(or attempt defragmentation)
		block = needed part of the found segment 
			(or all of it, if the segment remainder is too small)
		Update freeList to reflect the allocation 
		block[-1] = size+1  // Remember block size, for de-allocation 
		Return block
	}

	function void poke(int address, int val) {
		segment = object-1 
		segment.length = object[-1] 
		Insert segment into the freeList;
	}
}
```

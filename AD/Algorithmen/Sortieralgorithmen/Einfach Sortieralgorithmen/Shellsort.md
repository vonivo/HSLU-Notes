Shellsort ist eine **Verfeinerung des [[Insertion Sort]]** und erfolgt in mehreren Stufen. Sprich zuerst wird "grob" und danach "fein" sortiert.

Die Grob-Sortierung erfolgt über "grosse Distanzen" und die Feinsortierung dann über kleine.

Das eigentlich Sortieren entspricht 1:1 dem [[Insertion Sort]].

### Prinzip
![[ShellSort_1.png]]
![[ShellSort_2.png]]
![[ShellSort_3.png]]![[ShellSort_4.png]]![[ShellSort_stages.png]]

## Analyse
- Allgemeine [[AD/Algorithmen/Komplexität]] von $O(n^{2})$
- Folgen von $1,2,4,8,\dots,2^{k}$ schlechte Folge
- Optimale Folgen können [[AD/Algorithmen/Komplexität]] deutlich vermindern:
	- Knuth-Folge: $1,4,13,40,\dots,\frac{(3^{k}-1)}{2}$
	- Hibbard-Folge: $1,3,7,15,\dots,2^{k}-1$ -> $O(n^{1.5})$

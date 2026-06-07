**Why is cyclomatic complexity such an import metric to analyze for architecture**
Die Zyklomatische Komplexität ist ein gutes Mass, um die Komplexität der Codebase zu bestimmen. Dabei kann es aber auch zu "Accidential Komplexity" kommen -> sprich der Code an sich ist schlecht strukturiert.

**What are architecture fitness functions? How can they be used to analyze architecture**
Eine Fitness-Funktion ist ein Code-Stück was die Code-Base auf das Einhalten einer Architektur-Entscheidung oder Archtiektur-Charakteristik misst.
Einerseits können so direkt in der Pipeline Verstösse erkannt werden, oder es können Metriken gemessen und über Zeit ausgewertet werden.

**Provide an example of an architecture fitness function to measure the scalbility of an architecture**
Um die Scalabilty zu messen könnte einerseits Load/Performance-Tests mittels z.B. Jmeter gemacht werden. Dann wird die durchschnittliche Antwortzeit, Thorughput und die Ausreisser gemessen und angeschaut.

**What is the most important criterion for an architecture characteristic to allow architects and developers to create fitness functions**
Das wichtigste Kriterium ist die objektive Messbarkeit. Wenn nicht gemessen werden kann, kann es auch keine Fitness-Funktion dazu geben.
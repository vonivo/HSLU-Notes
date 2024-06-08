Java biete mehrere Frameworks an, um [[AD/Nebenläufigkeit/Thread/Task|Aufgaben]] [[Nebenläufigkeit und Parallelität|nebeläufig]] abzuarbeiten:
- [[Fork-Join-Pool|Fork-Join Framework]]
	Das Fork-Join-Framework wird benutzt, um [[Rekursion|rekursive]] "Devide and Conquer"-Aufgaben zu lösen.
- [[Item 48 Use caution when making streams parallel|Parallell Array- und Streamverarbeitung]]
	- Mit Java 8 wurde sowohl für [[Array|Arrays]] und auch für Collections die **parallele** Verarbeitung eingeführt.
	- Streams sind Abstraktionen, welche es ermöglicht Collections sequenziell oder parallel abzuarbeiten.
- [[Future|Completable Future]]
	- Mit Java 8 gibt es die Erweiterung des Future Patterns.
[[Prozess Kontrol Block|Prozesse]] werden in Queues gespeichert, im einfachen Fall besteht dies aus zwei einzenel Queues:
- Ein für die Prozesse welche zur Ausführung bereit sind.
- Eine für die Prozesse welche blockiert sind
![[Pasted image 20250107170041.png]]
Dies hat den Nachteil, dass bei einem Event immer alle Prozesse der Blocked-Quee durchsucht werden müssen und die passenden Prozesse zu verschieben.

Beim Forgeschritten Queuingmodell wird pro Event eine Blocked-Queue gespeichert. Wenn der Event auftritt wird die ganze Queue in die Ready Queue verschoben:
![[Pasted image 20250107170305.png]]
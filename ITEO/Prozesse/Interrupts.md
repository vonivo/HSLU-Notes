Ein laufender Prozess kann von einem der folgenden Events unterbrochen werden:
- Hardware-Interrupt: kommt von externen Events z.B. i/O -> sind asynchron
- Hardware-Trap: HW Traps sind synchron oder Asynchron und stehen in Beziehung zum momentan in Ausführung befindlichen Prozess: Z.B NPE oder Division durch 0
- Software Initiated Trap: werden von System verwendet, um einen Event zu forcieren, wie z.B. so schnell wie möglich ein Prozess-rescheduling oder eine Netzwerkpaketverarbeitung zu erzwingen

## Interrupt-Prios

1. Maschinenfehler
2. Zeitgeber
3. Disk
4. Netzwerkfehler
5. Terminals
6. Software-Interrupts

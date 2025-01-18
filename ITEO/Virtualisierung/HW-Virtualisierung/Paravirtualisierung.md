Bei der Paravirtualisierung spricht die Vm direkt mit dem Hypervisor über sogenannte Hypercalls.

Daher muss in der VM der Kernel so modifiziert werden, dass alle nicht virtualisierbaren Instruktionen durch einen Hypercall ersetzt werden, welcher direkt den Hypervisor anspricht und dann von ihm gehandelt werden.
![[Pasted image 20250107211127.png]]

## Nachteile
- Braucht immer verändertes OS
- Regel von Popek und Goldberg verletzt.

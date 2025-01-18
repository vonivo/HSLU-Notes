Binary-Translation ist ein Workaround, um volle Virtualisierung zu erreichen auf x86 Systemen.

User-Level-Code wird weiterhin direkt ausgeführt. 
Kontrollkritische Instruktionen werden erkannt und übersetzt und im cache abgelegt.

=> Der Hypervisor ist immer in der Leitung und entscheidet, ob die Instruktion übersetzt werden muss.

![[Pasted image 20250107210832.png]]
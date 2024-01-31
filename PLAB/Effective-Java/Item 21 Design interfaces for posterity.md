Mit Java 8 können Interfaces erweitert werden, ohne dass  jede implementierende [[Klasse]] geändert werden muss. Somit konnte z. B. die Collections-API um die [[Methode]] `removeIf()` erweitert werden.

Das ganze funktioniert dank der Default-Implementation auf Interfaces. Jedoch sind diese Default-Implementierungen ein zweischneidiges Schwert. Es kann sein, dass z. B. eine Externe Library auf diesem [[Interface]] basiert und die Default-Implementierung dort nicht funktioniert.

# Beispiel
Die Default-Implementation von `removeIf()` funktioniert bei der Klasse `rg.apache.commons.collections4.collection.SynchronizedCollection` nicht. Da diese Default-Implementation keinen Zugriff auf das Lock-Objekt oder ähnliches hat.


Darum ist es fundamental wichtig, dass Interfaces immer weitsichtige entwickelt werden und dass die Änderungen sich potenziellen Änderungen auf ein Minimum begrenzen.
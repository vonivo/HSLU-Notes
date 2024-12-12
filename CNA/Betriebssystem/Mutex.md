Ein Mutex (Mutual Exclusion) ist ein Kontrollelement für [[Interprocess Communication]] und wird dafür verwendet kritische Bereiche zu schützen.

Ein Mutex besteht aus einer Variablen mit den Zuständen **locked** und **unlocked**. 
- Dadurch wird ein **wechselseitiger Ausschluss** erzielt 

Vor dem Zugriff auf die gemeinsame Ressource wird die Operation `mutex_lock` ausgeführt.
Gibt man die Ressource frei wird `mutex_unlock` ausgeführt.

Erhält ein Prozess keinen Zugriff suspendiert er isch selbst.

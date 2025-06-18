>[!Definition]
>Ein **Integrationstest** prüft die **[[Schnittstelle]]** und das **Zusammenspiel** der Systemkomponenten.

> [!error]
>  Vorbedingung ist, dass die einzelnen Komponenen/ Module soweit wie möglich erfolgreich getstet werden.

Folgende Sachen werden durch Interfaces getestet:
1. [[Schnittstelle]] (direkt Abhängigkeit)
	- Objekt-Kompatibilitäten (Typen und Wertebereich)
	- Aufrufsequenz
	- Inputvalidierung
2. **Datenabhängigkeiten**
	- Pro Komponente Datenabhängigkeit ermitteln und testen.
	- Gemeinsam genutzte Ressourcen (z.B. Dateien, Shared-Memory, etc.)
3. **Abdeckung des Call-Graphs**:
	- Bei Komponenten die von verschiednen Aufrufer genutzt werden, auch alle Varianten testen.

>[!error]
>Wenn zwei Komponenten auf eine gemeinsam genutzte Ressource gleichzeitig zugreiffen kann eine [[Race Condition]] entstehen. Dies ist **schwierig zu testen.**
>
>Getesteter Code ist in dynamischer Umgebung ggf. immernoch fehlerhaft.


## Integrationstests entwerfen
1. **Wechselwirkung analysieren**: Welche Operationen von Modul `B` werden durch das Modul `A` aufgerufen?
2. **Parametersätze der Aufrufe von B ermitteln:** (ggf. mittels [[Äquivalenzklassenanalyse]])
3. **Testfallinputs ermitteln**: Welche Aufrufsequenz von `A` sind notwendig, um die Aufrufe vom `B` die in Schritt 2 ermittelten Parametersätze auszulösen.
4. **Soll-Ist-Vergleich**: Wie kann die Sollreaktion von `B` ermittelt werden.

>[!info]
>Um ein Testobjekt zu testen, müssen alle Komponenten die das Testobjekt benötigt, in der Testumgebung installiert und im Testverlauf mitverwendet werden können (siehe [[Testdouble]]).
>Werden [[Testdouble|Testdoubles]] verwendet, können Tests selektiver gestaltet werden.


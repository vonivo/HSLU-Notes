Der Bildprozess enthält alle Schritte, die in der Software nötig sind, um eine Programm (bestehend aus Source-Code) so zu verpacken, dass es ausgeführt und deployed werden kann.
Dies beinhaltete Schritte wie:
- Generieren (z. B. [[gRPC|Protocol Buffers]])
- Teste
- Paketieren,
- Java Doc erzeugen
- etc.

Jeder dieser Schritte ist, wenn manuell ausgeführt, Zeitintensiv. Wenn das $n$-Mal pro Tag von Hand gemacht werden muss, benötigt extrem viel Zeit -> [[Buildautomation]]
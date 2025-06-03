Wenn ein [[Spanning Tree Protokoll]] im einsatz ist, kann es sein, dass ein Port etwas Zeit benötigt bis er [[Frame Forwarding]] betreibt. Dies kann dazu führen, dass DHCP-Request Timeouts erhalten.
**Nur für Access-Ports** kann Port-Fast eingeschaltet werden ->unmittelbarers Forwarding.

Ein Port-Fast switch sollte nie BPDUs erhalten -> Spanning Tree Loop
Die Lösung dazu ist BPDU-Guard -> setzt Portin in errdisabled state wenn ein BPDU-Frame erhalten wird.
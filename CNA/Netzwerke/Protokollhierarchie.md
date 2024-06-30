Bei einem Schichtenmodell kommunizieren immer zwei gegenüberliegende Schichten miteinander über ein **Protokoll**.

Zwischen den einzelnen Schichten auf einer Seite sind Schnittstellen angebracht.
![[Protokollhierarchie.png]]
# Paketaufbau
Ein Paketaufbau könne wie folgt aussehen:
1. Nachricht wird von Schicht 5 an 4 übergeben.
2. Schicht 4 kodiert die Nachricht und vergibt einen Header, danach übergibt es dieses der Schicht 3.
3. Schicht teilt das Paket in 2 verschieden Pakete auf und versieht beide mit einer Adresse. Und gibt beide der Schicht 1 weiter.
4. Schicht eins Setzt einen wetieren Header an die Beiden Pakete und versendet diese.
![[Paketaufbau.png]]
# Service-Access-Point
Die Schnittstelle (Interface) ist die Grenze zwischen zwei Schichten und definiert die Regeln, wie die beiden Schichten miteinander kommunizieren.
Der Service-Access-Point ist der einzige Zugang zur über- bzw. untergeordneten Schicht.
## Service Primitives
Die Service-Access-Points können mit definierten Service-Primitives angesprochen werden.

| Primitive  | Meaning                                                                |
| ---------- | ---------------------------------------------------------------------- |
| Request    | Invokation of a service by service user                                |
| Indication | Notification form the service provider that a request bas been invoked |
| Response   | Acknowledgement issued by a service user in response to an indication  |
| Confirm    | Acknowledgement from the service provider in response to the request   |
![[ServicePrimitives.png]]

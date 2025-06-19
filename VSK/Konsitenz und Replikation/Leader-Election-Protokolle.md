## Mittels Quorum

>[!Definition]
>Ziel der **Leader-Election-Protokolle** ist es ein neuer Leader mittels Quorum (Mehrheitsentscheid) zu wählen.

**Vorgehen**
- 1 oder mehr [[VSK/Konsitenz und Replikation/Replikation|Replika]] erkennen Ausfall des Primary.
- Replika $R$ sendet **Vote Request** an alle anderen Replikate.
- Die anderen Replikate senden **Vote Grant**, falls diese mit Wechsel einverstanden sind (keine anderen Request; erkennen Primary als Down).
- Replika $R$ wird neues Priamry, falls es $\left\lfloor  \frac{N}{2}  \right\rfloor+1$ Vote Grant erhält.
![[QuorumElection.png]]

### Notwendigkeit des Quorums
Bei Netzwerpartitonierung darf nur eine Partition weiter operieren.

Ein Quorum ist ab $N\geq 3$ Systemen möglich, wobei $N$ sinnvollerweise **ungerade** ist.
![[Quorum.png]]

## Leader Election mit Externem Store
Ein kleiner aber Ausfallsicherer zentraler Store implementiert den Quorum-Algorithmus. Dieser Store wird von grösseren Systemen verwendet.

**Beispiel:** ZooKeeper (generischer Store in Java) oder etcd (Kubernetes).


**Ablauf**
- $N$ Replika senden Election-Request an einen zentralen Store, einer der Replika wird als Primary eingetragen.
![[QuorumStore.png]]

### ZooKeeper
- Zentraler Informationsdiesnt in Java.
- Ausfallssicher druch Konsensus-Protokoll
- Bietet verteilten Systemem folgende Funktionalität:
	- Namensdienste (Auffinden von Systemen).
	- Verteilte Synchronisation (z.b. systemübergreifende Locks).
	- Verwaltung von Gruppenzugehörigkeit.
![[ZooKeeper.png]]
- ZooKeeper impelementiert ein hierarchischen Namesraum mittels iner Baumdatenstruktur.
- Nodes können Informationen (bytes) und / oder weitere Kinder haben.
- Nodes sind `PERSISTENT` oder `EPHERMAL`:
	- `PERSISTANT`: Überdauern Verbindungsabbruch  durch Client.
	- `EPHEMERAL`: Gelöscht nach Verbindungsabbruch durch Client.

![[ZooKeperTree.png]]
**Persistente Node erstellen**
```java
zk.create("/app1/p_3", myData, Ids.OPEN_ACL_UNSAFE, CreateMode.PERSISTENT);
```
**Abrafge von Daten und Change-Listener**
`stats` beinhaltet statistiken.
```java
byte[] data = zk.getData("/app2", event -> setChanged(), stat);
```


**Leader-Elektion**
```java
public final static String PATH = "/myAppLeader";
public final String instance_name = ... ; // unique instance name
public String primary_name = null;// primary name (not known at 
								  // startup)

public void getOrBecomeLeader() {
	try {
		// try set self as leader
		zk.create(PATH, instance_name.getBytes(), Ids.OPEN_ACL_UNSAFE,
					CreateMode.EPHEMERAL);
		primary_name = instance_name
	} catch (KeeperException.NodeExistsException e) {
		// leader already exists, get leader name.
		// retrigger leader-election when changed with 
		// event -> getOrBecomeLeader()
		try {
			byte[] data = zk.getData(PATH, event->getOrBecomeLeader()
									, stat);
			primary_name = new String(data);
		} catch (KeeperException.NoNodeException ex) {
			getOrBecomeLeader(); // leader has changed
		}
	}
}
```
---
aliases:
  - Replikat
  - Replikate
---

**Replika**
- Eine Replika ist eine Kopie eines Systems.
- Je nach Anwendung muss diese nicht Bit für Bit identisch sein, muss aber die gleichen Informationen enthalten.

**Replikation**
- Der Prozess aus einem Original (**Primary**) eine Kopie (**Replika**) herzustellen.
- Hauptanwendung der Replikation bei verteilten Systemen:
	- **Ausfallsicherheit**: Fäll Primary $A$ aus, kann ein Replika $B$ übernehmen.
	- **Performance:** Verteilung von Anfragen über mehrere Systeme.



## Klassische Replikation
Ein Scheduler führt in **regelmässigen Intervallen** folgende Anweisungen aus:
1. Erstellung eines Abbilds $A$ des Primarys.
2. Einspielung von Abbild $A$ in alle Systeme, welche als Replikat dienen sollen.

![[KlassischeReplikation.png]]
Dies Art bietet [[Eventual Consistency]].


## Primary-Backup Protokoll für On-The-Fly Replika
- 1 Primary: Behandelt alle Schreibzugriffe.
- $N$ Replikate: Beantworten Lesezugriffe, leitet Schreibzugriffe an Primary weiter.

![[Replikation.png]]
**Eigenschaften**
Bei der Standard-Implementation kehrt die Schreibanfrage erst zurück, wenn alle Replikas die Daten geschrieben haben.
- Push-Prinzip
- [[Sequential Consistency]]
- Ausfallsicherheit?


## Variationen von Primary-Backup-Protocol
Implementiert von vielen Produkten (Oracle, MySQL, etc.), aber nicht in der ursprünglichen Form.

**Nicht blockierender Schreibzugriff**
- Ggf. Datenverlust (Daten nicht auf Replikat) nach Crash von Primary oder Primary muss nach Crash wiederhergestellt werden.

**Push- vs. Pull-Prinzip**
- In festgelegtem Intervall: Keine sequentielle Konstenz, aber je nach Daten und Anwendungszweck immer noch [[Eventual Consistency]]

**Einzelner vs. verteilte Primarys**
- Jedes Teilnehmende System kann für gewisse Operationen Primary und für andere Objekte Replikat sein.
- Komplexer aber schneller durch verteilte Schreibzugriffe.


>[!error]
>Betriebssysteme haben i.d.R. eine Filesystem-Cache. Änderungen kommen zuerst in den Cache und erst nach einer Zeit auf die Disk. Für [[Sequential Consistency]] muss Schreiben auf der Disk erzwungen werden.



## Implementation 

**Primary**
```java
public class Replication implements Runnable {
	private final String replicationAddress;
	private final Queue<Message> replicationQueue
		 = new ConcurrentLinkedQueue<>();

	public Replication(String replicationAddress) {
		this.replicationAddress = replicationAddress;
	}

	@Override
	public void run() {
		try (ZContext context = new ZContext()) {
			ZMQ.Socket socket = context.createSocket(SocketType.REQ);
			socket.connect(replicationAddress);
			processReplicationQueue(socket);
		} catch (Exception e) {
			LOG.error(ex.getMessage(), ex);
		}
	}

	public void addMessage(Message message) {
		replicationQueue.add(message);
		notifyWaiters();
	}

	public void waitForSynchronization() {
		waitForCondition(true);
	}

	private synchronized void waitForCondition(boolean isEmpty) {
		while (replicationQueue.isEmpty() != isEmpty){
			this.wait();
		}
	}

	private void processReplicationQueue(ZMQ.Socket socket) {
		while(true) {
			waitForCondition(false);
			Message message = replicationQueue.peek();
			socket.send(message.toString());
			socket.recvStr();
			replicationQueue.remove();
			notifyWaiters();
		}
	}
}
```
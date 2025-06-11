>[!Definition]
>Verbindeen von **einer Menge von Clients** mit **einer Menge von Services**.

**Halbduplex**
- Nur der Client kann eine Nachricht initiieren.
**Volldupeles**
- Sowohl Client als auch Server können eine Nachricht initiieren.
![[request_reply.png]]


## Beispiel mit [[ZeroMQ]]
**Client**
```java
public static final String ADDRESS = "tcp://localhost:5555";

public static void main(String[] args) {
	try (ZContext context = new ZContext()) {
		LOG.info("Echo client conntection to: " + ADDRESS);

		ZMQ.Socket socket = context.createSocket(SocketType.REQ);
		socket.connect(ADDRESS);

		var in = new BufferReader(new InputStreamReader(System.in));
		while(...) {
			String input = in.readLine();
			// auf jedes send muss recv folgen
			socket.send(input.getBytes(ZMQ.CHARSET));
			byte[] reply = socket.recv();
			LOG.inf("Received: " + new String(reply, ZMQ.CHARSET));
		}
	}
}
```

**Server**
```java
public static final String ADDRESS = "tcp://localhost:5555";

public static void main(String[] args) {
	try (ZContext context = new ZContext()) {
		ZMQ.Socket socket = context.createSocket(SocketType.RES);
		// bind
		socket.bind(ADDRESS);

		while(...) {
			// auf jedes recv muss send folgen
			byte[] reply = socket.recv();
			LOG.inf("Received: " + new String(reply, ZMQ.CHARSET));
			socket.send(reply);
		}
	}
}
```

In [[ZeroMQ]] is kein Threading vorhanden. Alle Anfragen kommen in eine Queue und werden über `.recv()` ageholt.

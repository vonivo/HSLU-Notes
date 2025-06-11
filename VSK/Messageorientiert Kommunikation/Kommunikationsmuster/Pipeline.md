>[!Definition]
>Mittels der Pipeline kann nach dem Fan-out / Fan-In Pattern aufgaben verteilt werden. (Ähnlichkeit zu [[Fork-Join-Pool]]).

Das Pattern kann mehrere Stufen und Schleifen enthalten.
![[pipeline.png]]

## Beispiel mit [[ZeroMQ]]
**Producer**
```java
public static final String ADDRESS = "tcp://localhost:5555";

public static void main(String[] args) {
	try (ZContext context = new ZContext()) {
		ZMQ.Socket socket = context.createSocket(SocketType.PUSH);
		// bind
		socket.bind(ADDRESS);

		var in = new BufferReader(new InputStreamReader(System.in));
		int i = 0;
		while (...) {
			String workPackage = "Work Package #" + ++i;
			socket.send(workPackage.getBytes(ZMQ.CHARSET));
			LOG.info("Send task '" + workPackage + "'");
			Thread.sleep(1000);
		}
	}
}
```

**Consumer**
```java
public static final String ADDRESS = "tcp://localhost:5555";

public static void main(String[] args) {
	try (ZContext context = new ZContext()) {
		ZMQ.Socket socket = context.createSocket(SocketType.PULL);
		// connect
		socket.connect(ADDRESS);

		while(...) {
			byte[] bytes = socket.recv();
			LOG.info("Received task");
			Thread.sleep(3000);
			LOG.info("Processed task");
		}
	}
}
```
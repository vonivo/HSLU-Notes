>[!Definition]
>Verbinden von einer **Menge von Publisher** mit einer **Menge von Subscriber**.

Das Publisher-Subscribe ist verbeitet im Enterprise-(ActiveMQ/Websphere) und IoT-Umfels (MQTT).

![[Publischer-Subscriber.png]]

Bei diesem Muster existieren sogenannte Topics.
- Ein oder mehrere **Publisher** können eine Nachricht an ein Topic **publizieren**
- Auf ein Topic können $[0;n]$-Subscribers hören.
- Immer wenn auf einem Topic etwas publiziert wird, erhalten alle Subscriber diese Nachricht.

>[!error]
>Dieses Kommunikationsmuster ist unidirektional.


**Anwendungsbeispiel**
- Ein Angestellter ändert seine Adress -> Alle möglichen Services werden über eine Subscription über diese Änderung benachrichtigt.

## Beispiel mit [[ZeroMQ]]
**Publisher**
```java
public static final String ADDRESS = "tcp://localhost:5555";

public static void main(String[] args) {
	try (ZContext context = new ZContext()) {
		ZMQ.Socket socket = context.createSocket(SocketType.PUB);
		// bind
		socket.bind(ADDRESS);

		var in = new BufferReader(new InputStreamReader(System.in));
		while(...) {
			long station = (long) Math.floor(Math.random() * 3.0);
			long temp = 15 + (long) Math.floor(Math.random() * 10.0);

			// Topic ruch msg-Prefix impliziert
			String msg = "TEMP/" + station + "/" + temp
			String input = in.readLine();
	
			socket.send(input.getBytes(ZMQ.CHARSET));
		}
	}
}
```

**Subscriber**
```java
public static final String ADDRESS = "tcp://localhost:5555";

public static void main(String[] args) {
	try (ZContext context = new ZContext()) {
		ZMQ.Socket socket = context.createSocket(SocketType.SUB);
		// connect
		socket.connect(ADDRESS);
		// subscribe
		socket.subscribe("TEMP");

		while(...) {
			byte[] msg = socket.recv();
		}
	}
}
```
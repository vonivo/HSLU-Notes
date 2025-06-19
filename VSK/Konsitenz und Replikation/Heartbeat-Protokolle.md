>[!Definition]
>Ziel eines Heartbeat-Protokolls ist es einen Ausfalls eines Systems (Primary oder z.B. [[VSK/Konsitenz und Replikation/Replikation|Replika]]) festzustellen.

**Vorgehen**
- Primary sendet Heartbeat-Messages in festem Intervall.
- $N$ Replika überprüfen, ob diese mindestens ein Heartbeat-Signal innerhalb eines Timeout-Intervalls erhalten haben. Ist dies nicht der Fall, wird der Server als Down betrachtet.
![[Heartbeat.png]]

## Beispiel
**Sender**
```java
private static final long HEARTBEAT_INTERVAL = 100; // [ms]
private final ScheduledThreadPoolExecutor executor
	= new ScheduledThreadPoolExecutor(1);
private ZContext zContext;
private ZMQ.Socket socket;

// Heart-Beat Runnable
private final Runnable action = new Runnable() {
	public void run() {
		socket.send(new byte[0]);
	}
};

public void start() {
	zContext = new ZContext();
	socket = zContext.createSocket(SocketType.PUB);
	socket.bind("tcp://localhost:7777");
	
	// Sende Heartbeat in intervall
	executor.scheduleWithFixedDelay(action, HEARTBEAT_INTERVAL,
	HEARTBEAT_INTERVAL, TimeUnit.MILLISECONDS);
}
```

**Empfänger**
```java
private static final long HEARTBEAT_DETECTION_INTERVAL = 1000; // [ms]
private ZContext zContext;
private ZMQ.Socket socket;

private final Runnable action = new Runnable() {
	public void run() {
		while(running) {
			if (socket.recv() == null) {
				running = false;
				noResponseHandler.run();
			}
		}
	}
};

public void start() {
	zContext = new ZContext();
	socket = zContext.createSocket(SocketType.SUB);
	socket.subscribe(new byte[0]);
	socket.connect("tcp://localhost:7777");
	// Timeout auf maximle Zeit ohne Heartbeat. Dann wird 
	// socket.recv() zurück kehren
	socket.setReceiveTimeOut(HEARTBEAT_DETECTION_INTERVAL);

	// Monitor Heartbeat in seperaten Thread
	Thread thread = new Thread(action);
	running = true;
	thread.start();
}
```

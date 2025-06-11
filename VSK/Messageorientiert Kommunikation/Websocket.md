>[!Definition]
>Websocket ist eine Protokoll welches [[Synchrone Kommunikation|synchrone]] [[Messageorientierte Kommunikation]] im [[Request-Reply|Full-Duplex]] erlaubt.

- Protokoll auf Anwendungslevel.
- Basiert auf HTTP

**Initialisierung**
![[WebSocket.png]]
**Anfrage**
```
GET /chat HTTP/1.1
Host: server.example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: x3JJHMbDL1EzLkh9GBhXDw==
Sec-WebSocket-Protocol: chat, superchat
Sec-WebSocket-Version: 13
Origin: http://example.com
```

**Antwort:**
```
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: HSmrc0sM
Sec-WebSocket-Protocol: chat
```


**Methdoen bei z.B. Jetty**

| Methode                                                          | Beschreibung                                                       |
| ---------------------------------------------------------------- | ------------------------------------------------------------------ |
| `void onWebSocketConnect(Session session)`                       | Client hat sich verbunden.                                         |
| `void onWebSocketClose(int statusCode, String reason)`           | Session wurde clientseitig geschlossen                             |
| `void onWebSocketBinary(byte[] payload, int offset, int length)` | Binärdaten empfangen                                               |
| `void onWebSocketText(String message)`                           | Textnachricht empfangen (vollständige Message in String enthalten) |
| `void onWebSocketError(Throwable cause)`                         | Fehler aufgetreten.                                                |

## Beispiel
**Endpoint**
```java
public class ChatEndPoint implements WebSocketListener {
	private static final ChatSessions CHAT_SESSIONS = new ChatSessions();
	
	private Session session;
	private String username;

	public void onWebSocketConnect(Session session) {
		this.session = session;
		CHAT_SESSIONS.add(session);
	}
	
	public void onWebSocketClose(int statusCode, String reason) {
		CHAT_SESSIONS.remove(session);
	}

	public void onWebSocketError(Throwable cause) {
		CHAT_SESSIONS.remove(session);
		LOG.error("web socket error occurred" , cause);

	}
	public void onWebSocketText(String message) {
		if (username == null) {
			username = message;
		} else {
			CHAT_SESSIONS.broadcast(username + ": " + message);
		}
	}
}
```

**Einbettung in Jetty**
```java
private static final int PORT = 8080;

public static void main(String[] args) throws Exception {
	Server server = new Server(PORT);
	ServletContextHandler servletContextHandler = 
		new ServletContextHandler();
	server.setHandler(servletContextHandler);

	Servlet websocketServlet = new JettyWebSocketServlet() {
		@Override 
		protected void configure(
				JettyWebSocketServletFactory factory) {
			factory.setIdleTimeout(Duration.ofMinutes(30));
			factory.addMapping("/", (req, res) -> new ChatEndPoint());
		}
	};
	servletContextHandler.addServlet(
		new ServletHolder(websocketServlet), "/chat");
	JettyWebSocketServletContainerInitializer.
			configure(servletContextHandler, null);

	server.start();
	LOG.info("Chat server listening on port " + PORT);
}
```
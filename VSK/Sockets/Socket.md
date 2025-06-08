>[!Definition]
>Ein Socket ist ein Kommunikationsendpunkt in [[TCP|TCP/IP]]-Netzwerk.

Es existiren zwei Arten von Sockets:
- **ServerSocket**
- **Socket**

## ServerSocket
Der ist ein Spezieller Socket, welcher auf eingehende Verbindungen reagiert und diese einem eigenen **Socket** zuweisen.

=> Jede TCP-Verbindung benutzt nach dem Verbindungsaufbau einen eigenen Socket auf dem Server.

Serversockets hören auf einem **zugewiesenen Port** auf Anfragen. Diese Portnummer erhält der **Client-Socket** um einen Verbindungsaufbau zu starten.

**Regeln für Portnummern:**
- Die Portnummer darf nicht in Benutzung sein.
- Kann nach der Bnutzung für einen bestimmten Zeitraum gesperrt sein (typisch 4 min)
- Falls $<1024$ nur Nutzbar mit einem Rootbenutzer bei UNIX-Systemen

## Verbindungsaufbau:
**Client**
1. Socket erzeugen.
2. Socket einem freien Port zuweisen.
3. Verbindung zu ServerSocket über IP und Port aufbauen.
4. Daten über Socket lesen/schreiben.
5. Connection schliessen.

**Server**
1. ServerSocket erzeugen.
2. Mit `severSocket.accept()` warten bis eine Verbindung augebaut wird.
3. Über den Socket welcher `severSocket.accept()` zurückgibt Ein- und Ausgabestrom verknüpfen.
4. Daten lesen und schreiben (entsprechend dem [[Kommunikationsprotokoll]])
5. Stream von Client-Socket schliessen
6. Bei Schritt 2 weiter machen. Oder ServerSocket schliessen.

**Warten auf Verbindung:**
- Nur die `accept`-Methode nimmt eine Wartende Verbindung an, und zwar genau eine.
- `accept` ist blockierend.
- Die Kommunikation läuft nicht über den ServerSocket.
- Das Programm sollte so schnell wie möglich zurück zu `accept` gelangen, um neue Verbindungen anzunehmen. (Nebeläufigkeit)

## Beispiel
**Client**
```java
static void getTime(String host, int port) throws IOException {
	Socket socket = new Socket(host, port);
	DataInputStream is;

	is = new DataInputStream(socket.getInputStream());
	byte[] bytes = is.readAllBytes();
	socket.close();
	
	String time = new String(bytes);
	System.out.println(time);
}
```
**Server**
```java
public static void main(final String[] args) {
	try {
		final ServerSocket listen = new ServerSocket(1300);

		while (true) {
			try (final Socket client = listen.accept()) {
				final DataOutputStream dout =
					new DataOutputStream(client.getOutputStream());
				final Date date = new Date();
				dout.write((date.toString()).getBytes());
			}
		}
	} catch (IOException ex) {
		LOG.debug(ex.getMessage());
	}
}
```

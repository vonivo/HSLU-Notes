Selbst wenn [[Integrationtests mit JUnit|Integrationstests]] automatisiert sind, benötigen sie alle nötigen "Umsysteme", welche meistens manuell installiert werden müssen.

Dabei hilft Testcontainers, dies zu automatisieren.

>[!Definition]
>Testcontainers ist ein JUnit ergänzendes Framework, welches:
>- Eine Java-API zu vilene Dokcer-Aktionen anbietet.
>- Das Hoch- und Runterfahren weitgehend automatisiert.
>- Sic automatisch um das Portmapping kümmert.

## Beispiele
### Echo-Server
```java
@Testcontainers
class EchoServerDefaultPortIT {
@Container
GenericContainer<?> echoServer = new GenericContainer<(
			DockerImageName.parse("repo/echoserver:latest"))
	.withStartupTimeout(Duration.ofSeconds(3))
	.withExposedPorts(EchoServer.DEFAULT_PORT);
```
- `@Testcontainer` markiert die Testklasse für das Framework.
- `@Container` definiert einen konkreten Container (als Objekt), in max. 3s muss er oben sein (auf Port reagieren), sonst failure!
- Container erhält dynamische IP und Port, stellt sicher, dass es keine
- Kollisionen mit bereits laufenden Containern gibt!

```java
@Test
void testServerStart() {
	assertThat(echoServer.getLogs())
		.contains("started").contains("5555");
}
```
- `getLogs` kann man Ausgaben des Containers abrufen.

```java
@Test
void testServerGetEchoAndLog() {
	final String url = String.format("tcp://%s:%s",
		echoServer.getHost(), echoServer.getFirstMappedPort());
	try ( ZMQ.Socket socket = new 
			ZContext().createSocket(SocketType.REQ)) {
		socket.connect(url);
		socket.send("Hallo!".getBytes(ZMQ.CHARSET));
		
		assertThat(new String(socket.recv(),
								ZMQ.CHARSET)).isEqualTo("Hallo!");
	}
	assertThat(echoServer.getLogs()).contains("Hallo!");
}
```
- `getHost()` und `get[First]MappedPort` liefer die dem Container dynamisch zugewiesene IP bzw. Ports.


```java
@Container
GenericContainer<?> echoServer = new GenericContainer<>(new
		ImageFromDockerfile("ad-hoc/echoserver-temurin", false)
	.withFileFromFile("./target/echoserver.jar", new 
		File("./target/echoserver.jar"))
	.withDockerfileFromBuilder(builder -> builder
		.from("eclipse-temurin:21.0.4-jre-alpine")
		.expose(5555)
		.workDir("/app")
		.copy("./target/echoserver.jar", "/app/")
		.cmd("java", "-jar", "echoserver.jar")
		.build()))
	.withStartupTimeout(Duration.ofSeconds(3))
	.withExposedPorts(5555)
```
Baut ein Adhoc Image zusammen.


## Herausforderungen
- Benötigit Infrastruktur
	- Docker-Registry
	- Individuelle Umgebung muss auf [[Buildserver]] portiert werden
- Docker in Docker notwendig.

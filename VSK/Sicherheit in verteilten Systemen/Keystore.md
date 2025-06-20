Um eine [[Transportlayer Security|TLS]]-Verbindung in Java aufzubauen wird der **Keystore** verwendet.

**Keystore (Serverseitig)**
Der Keystore enhält das Server-Zertifikat und den Private-Key des Server.

```sh
# create PKCS12 bundle contains server private key and certificate as
# well as rootCA certificate
openssl pkcs12 
	-export 
	-in server.crt 
	-inkey server.key 
	-chain -CAfile rootCA.crt 
	-name localhost 
	-out server.p12

keytool -importkeystore 
	-deststorepass myServerPass 
	-destkeystore server.jks 
	-srckeystore server.p12 
	-srcstoretype PKCS12
```




**Truststore (Clientseitig)**
Der Truststore enthält die trusted Root-CA auf Client-Seite.
```shell
## create java keystore containing certificate of our own CA
keytool -import -v -trustcacerts -alias server-alias 
	-file rootCA.crt 
	-keystore cacerts.jks 
	-keypass myCaCertsPass 
	-storepass myCaCertsPass
```

## Aufbau sicherer Verbindung
```java
private static final String HOST = ...;

public static void main(final String[] args) {
	SSLSocketFactory factory = (SSLSocketFactory) 
		SSLSocketFactory.getDefault();
	try (SSLSocket socket = (SSLSocket) 
			factory.createSocket(HOST, 1234)) {
		socket.setEnabledProtocols(new String[] {"TLSv1.3"});
		socket.setEnabledCipherSuites(new String[] 
						{"TLS_AES_128_GCM_SHA256"});
	} 
}
```

Die Applikation muss noch mit den Entsprechenden Truststores gestartet werden:
**Server**
```shell
java -Djavax.net.ssl.keyStore=server.jks \
	-Djavax.net.ssl.keyStorePassword=myServerPass \
	myServerClassName
```
**Client (Nur bei Self-Signed)**
```shell
java -Djavax.net.ssl.trustStore=cacerts.jks \
	-Djavax.net.ssl.trustStorePassword=myCaCertsPass \
	myClientClassName
```

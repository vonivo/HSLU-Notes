Konzept für Dateneingabe und Datenausgabe
Packages: `java.io` und `java.nio`

Zwei Arten von Datenströmen: 
- Byte Datenströme (Folge von 8 Bit Werten)
- Zeichen Datenströme (Textdaten)

**Achtung bei Pfadangaben in Windows müssen immer zwei \\ verwendet werden z.B “c:\\temp\\test.txt”** 

## Best Practices
- Überlegen ob Zeichen oder Byteströme
	- Byteströme → Effizient und kompakt
	- Zeichenströme → Für Menschen lesbar
- Bei Zeichendatenströme das Encoding beachten
- [[Exceptionhandling]] mit try-with-resources
- I/O Streams sollten immer sauber geschlossen werden
# Bytedatenströme
- Basisklasse Inputstream und Outputstream
	- Die meisten Klassen welche spezialisieren verwenden in ihren Konstruktoren wiederum Input- Outputstream → Verschachtelung möglich
- Daten werden als Byte behandelt aber als int dargestellt

[[Klasse|Klassen]]
- `FileInputStream` und `FileOutputStream` → Dateien
- `BufferedInputStream` und `BufferedOutputStream` → gepufferten I/O Streams
- `DataInputStream` und `DataOutputStream` → Lesen und Schreiben von elementaren Datentypen
- `PrintStream` → Ausgabe von ASCII-Text auf die Konsole

## Beispiel
```java
// DataInputStream
DataInputStream dis = new DataInputStream (new FileInputStream("c:\\temp\\test.dat"))
// read int from file
int number = dis.readInt();
// Close DataStream
dis.close();
// DataOutputStream
DataOutputStream dos = new DataOutputStream (new FileOutputStream("c:\\temp\\test.dat"))
// write int to 
dos.writeInt(number);
// Close DataStream
dos.close();
```

# Zeichen Datenströme
- Basisklasse Reader und Writer
- Daten werden als 16bit-Unicode-Charakter behandelt aber in Java als int dargestellt
- **Encoding beachten**

[[Klasse|Klassen]]:
- Reader und Writer → I/O mit Unicode-Zeichen
- ``BufferedReader`` und ``BufferedWriter`` → erhöhen Performance durch Pufferung
- ``InputStreamReader`` und ``OutputStreamWriter`` → Koppeln Bytedatenströme mit Zeichendatenströmen
- ``FileReader`` und ``FileWriter``  → Textdateien (**Encoding**)
- ``PrintWriter`` → Konsolenausgabe von Unicode Zeichen
- 

## Beispiele 
Bei der Arbeit mit Zeichendatenströmen muss immer das Encoding mitgegeben werden.
```java
// Printwriter um einen Text in ein File zu schreiben
PrintWriter pw = new PrintWriter(new OutputStreamWriter(new FileOutputStream("c:\\temp\\test.txt"), Charset.forName("UTF-8")));
// Schreiben von einem Text
pw.println(text);
// Buffered Reader um einen Text aus einem File zu lesen
BufferedReader br = new BufferedReader(new InputStreamReader(new FileInputStream("c:\\temp\\test.txt"), Charset.forName("UTF-8")));
//Lesen von dem Text
line = br.readLine()
// Schleife um mehrere Zeilen auszulesen und zu einem Text zusammenzufügen
String text = null;
String line;
while ((line = br.readLine()) != null) {
	LOG.info("Read " + line + " from " + file);
    text += line;
}
```

# [[Exceptionhandling]]
Datenströme müssen jeweils explizit geöffnet und auch wieder geschlossen werden.
Da das bei einer Exception nicht garantiert werden kann kennt Java die **try-with-resources** welche automatisch am Ende alle Closable Objekte schlisst. 

Dafür steht die Initialisierung von Data Streams in den runden Klammern des `try` Blocks. Also müssen Data Input Streams eigentlich immer so geöffnet werden:

```java
try (DataInputStream dis = new DataInputStream (new FileInputStream("c:\\temp\\test.dat")))
{
	int number = dis.readInt();
}
catch (IOException ioe)
{
	OG.error("Datei nicht lesbar.", ioe);
}
```

Wenn man direkt mehrere DataStreams initialisieren möchte trennt man diese per Semikolon
```java
try (DataInputStream dis = new DataInputStream (new FileInputStream("c:\\temp\\test.dat")); DataOutputStream dos = new DataOutputStream (new FileOutputStream("c:\\temp\\test.dat")))
{
	int number = dis.readInt();
	dos.writeInt(number);
}
catch (IOException ioe)
{
	OG.error("Datei nicht lesbar.", ioe);
}
```

Da beim [[Exceptionhandling]] von Streams of verschiedene Exceptiontypen vorkommen welche gleich behandelt werden sollen, verwendet man dafür ein [[Exceptionhandling#Multiple Catch|Multiple Catch]]. 
Bei Blocking I/O ist ein [[Thread]] blockiert, während er auf neue Daten wartet:
```java
DataInputStream is;
is = new DataInputStream(socket.getInputStream());
byte[] bytes = is.readAllBytes(); // <-- blockiert während Warten
```

- Einfach zu porgrammieren.
- Falls mehr als eine Verbindung benögitg: Pro Verbinudng und ServerSocket jeweils einen eigenen Thread erstellen.


| Variante                               | Einsatzgebiet                                                                                |
| -------------------------------------- | -------------------------------------------------------------------------------------------- |
| - Blocking I/O<br>- Single-Threaded    | Eine langlebige oder wenige kurzlebige Verbindungen                                          |
| - Blocking I/O<br>- Mehrere Prozesse   | Wenige langlebige Verbindungen                                                               |
| - Blocking I/O<br>- Mehrere Treads     | Wenige langlebige Verbindungen                                                               |
| - Blocking I/O<br>- Thread-Pools       | Viele kurzlebige Verbindungen                                                                |
| - Nonblocking I/O<br>- Single-Threaded | Viele Verbindungen (kurz- oder langlebig), mit wenig Bearbeitungszeit                        |
| - Nonblocking I/O<br>- Multi-Threaded  | Viele Verbindungen (kurz- oder langlebig), mit wenig bis viel Bearbeitungszeit               |
| - Blocking I/O<br>- Virtual Threads    | Way to go.<br>Viele Verbindungen (kurz- oder langlebig) mit wenig bis viel Bearbeitungszeit. |

>[!Definition]
>Die Präsentationsschicht ist für die Visualisierung, das User-Interface und die UI-Logik einer Applikation zuständig.

Die Präsentationsschicht kann lässt sich je nach Technologie natürlich noch unterteilen.

- Model View Controller
	- Spezielle Modell für Präsentation
	- Wiederverwendbare Views
	- Präsentationslogik im Control-Teil
- Thin-Clients (WEB) ist Trennung sogar zwinged notwendig
	- View -> HTML, CSS
	- Präsentationslogik und Modell
		- Im Cleint (z.B. Java-Script, JSON, XML)
		- im Server (Servlet, Pojo's, JSON, XML)
![[Pasted image 20250118194831.png]]
**Schwachstellen**:
- Der Sessionkey ist vorhersagbar.
- Der Sessionwert kann vom Client gesetzt werden.
- Die [[Cookies|Cookie]]-Attribute `Secure`, `Same-Site` und `HttpOnly` sind nicht gesetzt.
- Cookie-Domain oder Pfad sind nicht so eingeschränkt wie möglich.
- Die Session wird beim Logout nicht richtig invalidiert.
- die Session hat kein server-seitiges Timeout.

**Massnahmen**
- lange und kryptografisch zufällige Sessionkeys wählen.
- nur vom Server gewählte Keys akzeptieren.
- Cookies als `Secure`, `Same-Site` und `HttpOnly` mit eingeschränkter Domain und Pfad setzen.
- Session serverseitig beim Logout oder Timeout invalidieren.
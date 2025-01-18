Cookies sind kurze Textdaten, welche vom Server als Header an den Browser übermittelt werden und von diesem ebenso als Header bei Request mitgesendet werden. 

Cookies können im Browser verwaltet werden.

**Eigenschaften**
- Persistent (mit Ablaufdatum) oder Session-Cookie (ohne Ablaufdatum)
- Secure (wird nur über HTTPS übertragen)
- HTTP Only (darf nur von HTTP gelesen werden -> kann nicht via js ausgelesen werden)
- Same Site (wird nicht bei Cross-Domain-Aufrufen mitgesendet, z.B. bei embedded Link Image)
- 
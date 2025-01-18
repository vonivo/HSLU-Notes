HTTP ist ein Stateless-Protokoll und kommuniziert über Request und Responses.

**Request**
- Request line (method + resource)
- request hedader fields
- message body (optional)

**Response**
- status line with status code
- response header fields
- message body (optional)

## Request-Methoden
- GET -> Daten vom Server abrufen, Serverzustand wird nicht verändert.
- POST -> Darf Serverzustand verändern. Wird nicht gecachet.

## Response-Code
- 200 OK
- 204 No Content
- 301 Moved Permanently
- 304 Not Modified
- 400 Bad Request
- 403 Forbidden
- 404 Not Found
- 500 Internal Server Error

## Responses Headers
**HSTS**
`Strict-Transport-Security: max-age31500600; includeSubDomains`
Seite wird nur via HTTPS aufgerufen. Max-Age muss hoch gesetzt werden.

**Frame-Options**
`X-Frame-Options: deny`
Verbietet das Einbinden der Seite mit einem Frame oder erlaubt es nur für bestimmte Domains.

**XSS-Protection**
`X-XSS-Protection: 1, mode=block`
Filter und säubert oder blockiert die Anzeige der Seite, wenn ein XSS-Angriff entdeckt.

**Content-Type-Options**
`X-Content-Type-Options: nosniff`
Verhindert, dass der Content als einer anderen MIME-Type interpretiert wird als angegeben.

**CSP**
`Content-Security-Policy: script-src 'self'`
definiert, welche Ressourcen (e.g. Bilder, Scripts, Fonts, etc.) von wo eingebunden werden können.

**CORS**
Cross-Origin-Resource-Policy definiert, wer alles Request auf den Server machen können.

**HPKP** (deprecated)
`Public-Key-Pins: pin sha256="d6qzRu9zOECb90Uez27xWltNsj0e1Md7GkYYkVoZWmM="; pin-sha256=Ë9CZ9INDbd+2eRQozYqqbQ2yXLVKB9+xcprMF+44U1g=";report-uri="http://example.com/pkp-report"; max-age=10000; includeSubDomains`
Nur das Serverzertifikat mit dem korrekten Fingerprint wird akzeptiert.

## Sessionmanagment
Da HTTP ein zustandsloses Protokoll ist existieren verschiedenen Möglichkeiten den Zustand trotzdem zu speichern:

Der Zustand kann in der Response an den Client übergeben werden. Dies kann in [[Cookies]] oder Hidden fileds gemacht werden.

Dabei sollte aber darf aber nicht der eingentliche Wert gespeichert werden (kann durch Client bearbeitet werden) sonder eine Grosse Zufallszahl welche dann im Server genutzt wird um den State aus einer Mapping-Tabelle zu lesen. (Session-Key)






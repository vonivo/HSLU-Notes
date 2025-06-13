## IP-Spoofing
Bei IP-Spoofing übernimmt ein Angreiffer eine IP-Adresse eines anderen Gerätes oder Random IP-Adressen.
IP-Spoofing ist schwierig zu verhindern, vorallem wenn es in einem Subnetz gemacht wird, wo die gespoofte IP zugehörig ist.

## MAC-Spoofing
Beim MAC-Spoofing verändert der Angreifer die MAC seines Host so, dass diese gleich ist wie die MAC eines andere Gerätes im Netz. Der Switch überschreibt dann den Eintrag in seinem [[Switch MAC-Adress Table]] und der Angreifer erhält nun Paket des anderen Host.

Sendet der echte Host jetzt wieder ein Paket, wird der Eintrag wieder umgeschrieben.
Dies verhindert der Angreifer jedoch mit einem Skript, dass periodisch eine Nachricht an den Switch


Kann nur mit [[IP Source Guard]] migitiert werden.
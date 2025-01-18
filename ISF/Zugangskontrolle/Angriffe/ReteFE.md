![[Pasted image 20250118153947.png]]
1. Eine [[Malware]] ändert den Eintrag des DNS-Servers auf einen bösartigen DNS-Server und installiert ein [[Vertrauensmodelle#Hierarchical Trust (PKI)|Root-CA-Zertifikat]].
2. Bei der Eingabe von "www.bank.ch" wird die URL Auflösung auf einen von Angreiffer kontrollierten Server weitergeleitet. (Durch das Root-CA fällt die Verbindung als "Sicher auf")
3. Es wird einen manipulierte Kopie der Bankenwebseite angezeigt, inkl einem Zertifikat welches von der neu installierten Root-CA signiert ist.
4. Beim Login gehen die Daten (Benutzername und Passwort) an den Angreiffer.
5. Der Benuter wird aufgefordert, eine 'neune Banking-App' zu installieren. Diese leitet in Wirklichkeit alle erhaltenen SMS an den Angreifer weiter.
6. Der Angreifer hat volle Kontrolle über das Benutzerkonto: er kann sich mit Benutzername und Passwrot einloggen und erhält die entsprechenden SMS weitergeleitet. Normalerweise verwendet der Angreifer dafür einen weiteren kompromitierten geographisch nahen Computer als Proxy um nicht aufzufallen.
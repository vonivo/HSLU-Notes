Bei CSRF bringt der Angreifer einen Benutzer dazu, einen Request aus seinem Browser abzusetzen und dadurch eine Aktion auf dem Server auszulösen.
Ist der Benutzer zu dem Zeitpunkt eingeloggt, wird das Cookie automatisch mitgeschickt.
![[Pasted image 20250120204902.png]]
## Massnahmen
-> CSRF-Token: Ein Secret Token als Teill des Formulars oder als Header mitgegeben wird, was mit dem Server übereinstimmen muss, um eine Aktion auszuführen.
-> Zusätzlich: Same-Site-Attribut setzen.
Das ALOHA Protokoll wurde 1970 von Prof. Abramson an der Universität Honolulu entwickelt. Das Ziel war eine kostengünstige Funkverbindung zwischen den Uni-Standorten auf den 4 hawaiianischen Inseln einzurichten.

Das ALOAH Protokoll ist die Grundlage das [[IEEE-802#Ethernet|Ethernet]]-Protokoll.

Beim ALOAH-Protokoll darf jeder Sender beliebig senden:
![[Aloah.png]]
- Wenn eine Kollision auftritt wird das [[Dataframes|Dataframe]] beschädigt.
- Druch Rückmeldung auf einem anderenen Funk-Kanal erfolgt die Kontrolle der Frameübertragung.
- Falls ein [[Frame]] beschädigt wurde -> nach einer zufälligen Wartezeit nochmals versuchen.

# Slotted ALOAH
Eine erste Verbesserung des ALOAH-Protokoll ist das Slotted ALOAH.
Dabei werden fixe Zeitslots definiert, in denen ein [[Frame]] versendet werden kann.

![[Slotted_aALOAH.png]]G -> Anzahl der Sendeverusche pro Frameübertragungszeit
S -> Kanaldurchsatz pro Frameübertragungszeit

Reines ALOAH: $S_{max}=18\%$
S-ALOAH: $S_{max}=37\%$

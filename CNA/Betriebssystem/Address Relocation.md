Address Relocation wird verwendet weil man nicht für jedes Programm fixe physische Memory Adressen einprogrammieren möchte. So handelt das [[Betriebssysteme|Betriebssystem]] das in dem es die physische Adressierung übernimmt und die Programme mit einfachen Adressen geschrieben werden können. 
# Statische Relocation (Verlagerung)
Bei der statischen Relocation weist der Loader des OS die Lade Adressen für den Code und die Daten eines Programmes zu. 
Das Programm verwendet dabei aber immer Adressen von 0000 bis XXXX, während physisch die Daten in den Adressen 0150 bis XXXX liegen können (siehe Illustration).
Das wird bewerkstelligt in dem immer eine fix festgelegte Konstante zu der Adresse hinzugerechnet wird, beim tatsächlichen herauslesen der Daten. 

![[Pasted image 20240526153628.png]]
# Dynamische Relocation
Bei der dynamischen Relocation werden die Adressen während der Laufzeit umgerechnet von der MMU (Memory Management Unit). Dafür verwendet es ein Relocation Register. In das Relocation Register wird zum einen der Startpunkt hineingeladen, wo die Adressen des Programmes physisch beginnen. Zum anderen wird das Limit festgelegt, also wie weit der Adressraum geht. 

![[Pasted image 20240526154126.png]]
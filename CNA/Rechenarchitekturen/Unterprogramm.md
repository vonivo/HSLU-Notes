Ein Unterprogramm ist ein Programm, das innerhalb eines Programms aufgerufen werden kann:
![[Unterprogramm.png]]
Das Unterprogramm wird mittels einer Rücksprungadresse aufgerufen.
Die Rücksprungadresse gibt an, wohin das Unterprogramm nach der Beendigung zurückkehren muss.
Die Rücksprungadresse wird dabei auf den [[CNA/Rechenarchitekturen/Stack]] gespeichert. Damit wird bewirkt, dass ein Unterprogramm wieder ein Unterprogramm aufrufen kann und immer wieder an den richtigen Ort zurückspringen kann.
![[Unterpgraomm_Call.png]]
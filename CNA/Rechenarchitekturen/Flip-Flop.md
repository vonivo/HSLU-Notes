Ein Flip-Flop ist eine Speichereinheit, welche genau ein Bit speichern kann. Dabei werden zwei [[Logische Verknüpfungen#OR|NOR-Gatter]] kreuzweise miteinander verknüpft.

## RS-Flip-Flop
![[Flip-Flop.png]]
Beim Flip-Flop existieren zwei Eingänge, eines ist um das Bit zu setzen und eines um das Bit zurückzusetzen. Das Signal **C** erlaubt das Setzen des Bits nur, wenn das Taktsignal der CPU an ist.

## D-Flip-Flop
Beim D-Flip-Flop wird der S-Eingang und der R-Eingang zusammen genommen und mit einem [[Logische Verknüpfungen#NOT|Not]]-Gate verknüpft. Damit der Zustand aber nicht immer wechselt sobald der Strom ein- bzw. ausgeschaltet wird. Kann auch dieses Signal nur mit dem CPU-Takt gesetzt werden. Dafür wird ein [[Logische Verknüpfungen#AND|AND-Gate]] verwendet:
![[D-Flip-Flop.png]]
# Flankengesteuert
Das Flankengesteuerte Flip-Flop erlaubt das Setzen des Flip-Flops nur wenn der Takt gerade eingeschaltet wird.
![[Flanken-Flip-Flop.png]]

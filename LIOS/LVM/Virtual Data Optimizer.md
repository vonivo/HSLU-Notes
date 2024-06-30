Der Virtual Data Optimizer (VDO) ist eine Software, die In-Line-Duplizierung auf Blockebene, Komprimierung und Thin-Provisioning Speicher auf einem [[LVM]] bereitstellt.

**Duplizierung**
Duplizierung ist eine Technik zur Reduzierung des Verbrauchs von Speicherressourcen, indem mehrere Kopien doppelter Blöcke eliminiert werden.

**Komprimierung**
Die Komprimierung nimmt die einzelnen eindeutigen Blöcke und schrumpft sie. Diese reduzierten Blöcke werden dann effizient in physischen Blöcke zusammengefasst.

**Thin Provisioning**
Thin Provisioning verwaltet die Zuordnung von logischen Blöcken, die von VDO präsentiert werden, zu dem Ort, an dem die Daten tatsächlich physisch gespeichert wurden und eliminiert auch alle Blöcke, die nur aus Nullen bestehen.


# Konfiguration
## Installation
```bash
[user@host ~]$ dnf install vdo kmod-kvdo
```
## Konfiguration
Beim Erstellen des [[LVM#Logisches Volumen (LV -> Logical Volume)|LV]] mit dem Parameter `--type vdo`
```bash
[user@host ~]$ lvcreate --type vdo ---name vdo-lv01 --size 5G vg01
```

**LVM** (Logical Volume Manager) ermöglicht das Strecken von Partitionen auf mehrere physische Geräte.
LVM biete Flexibilität in der Erweiterung von Partitionen, indem es eine logische Abstraktionsschicht über die physischen Geräte und [[Partition|Partitionen]] legt.

![[LVM.png]]

**Vorteile:**
- Dynamische Grössenänderungen von Volumen
- Verteilen von einem Volumen über mehrere physische Festplatten.
- Live-Kapazitätserweiterung -> Dynamische erweiterung von phy. Festplatten.
- Unterstützung für Snapshots.
# Aufbau
In LVM existiert:
- physische Geräte und Partitionen,
- physischen Volumen (PV)
- logische Volumen-Gruppen und
- logische Volumen (logische Partitionen).

## Volumengruppen (VG -> Volume Group)
Volumen-Gruppen sind Speichertools, die aus mindestens einem PV besteht.
Eine VG kann sich über mehrere PV auf mehreren physischen Festplatten erstrecken.
Ein PV kann jedoch nur einer VG angehören.

Die VG wird von LVM in Einheiten (physical Extents) unterteilt, dies kann auch manuell gemacht werden

## Logisches Volumen (LV -> Logical Volume)
**LV**s werden aus einer VG heraus erstellt und sind die Partitionen, die das Betriebssystem am Schluss sieht.
LVs sind eine Sammlung von physischen Extents. Durch die Konfiguration von LVs kann bezweckt werden, dass z.B. auf eine Spiegelung eingesetzt wird, sprich jedes LV wird mehreren PEs zugeordnet.


# Konfiguration
## Erstellen
Um ein LVM zu konfigurieren ist folgender Workflow anzuwenden:
1. Ermitteln der physischen Geräte, die zum Erstellen von physischen Volumen verwendet werden und diese Geräte als LVM-Volumen installieren.
2. Erstellen einer VG aus mehreren PVs.
3. Erstellen eines LV aus dem verfügbaren Speicherplatz einer VG.
4. Formatieren des LV mit einem [[Dateisystem]] und [[Mounting|mounten]].
![[LVMWorkflow.png]]

### Erstellen von physischer Gerätepartition
```bash
[user@host ~]$ parted /dev/vdb mklabel gpt mkpart primary 1MiB 769MiB
...output omitted...
[user@host ~]$ parted /dev/vdb mkpart primary 770MiB 1026MiB
[user@host ~]$ parted /dev/vdb set 1 lvm on
[user@host ~]$ parted /dev/vdb set 2 lvm on
```
Erstellt zwei LVM-Partitionen auf dem Gerät `/dev/vdb`.

### Erstellen von physischen Volumen
```bash
[user@host ~]$ pvcreate /dev/vdb1 /dev/vdb2
 Physical volume "/dev/vdb1" successfully created.
 Physical volume "/dev/vdb2" successfully created.
 Creating devices file /etc/lvm/devices/system.devices
```
Für die beiden erstellten Partitionen werden PVs erstellt.

### Erstellen von Volume-Gruppen
```bash
[user@host ~]$ vgcreate vg01 /dev/vdb1 /dev/vdb2
 Volume group "vg01" successfully created
```
Volumengruppe "vg01" auf den PVs `/dev/vdb1` und `/dev/vdb2` erstellen.

### Erstellen von Volumen
```bash
[user@host ~]$ lvcreate -n lv01 -L 300M vg01
 Logical volume "lv01" created.
```

### Filesystem erstellen
```bash
[user@host ~]$ mkfs -t xfs /dev/vg01/lv01
```
### [[Mounting]]
1. Mountpoint erstellen
2. FSTab berarbeiten: `/dev/vg01/lv01 /mnt/data xfs defaults 0 0`

## Erweitern
### Vergrössern der VG
Um eine VG zu vergrössern, muss eventuell neuer Festplattenspeicher hinzugefügt werden.

Mit dem [[Prompt|Befehl]] `vgextend` kann die VG vergrössert werden:
```bash
[user@host ~]$ vgextend vg01 /dev/vdb3
```

### Vergrössern des LV
LVs können ohne Aussfallzeit vergrössert werden.
```bash
[user@host ~]$ lvextend -L +500M /dev/vg01/lv01
 Size of logical volume vg01/lv01 changed from 300.00MiB (75 Extents) to 800.00MiB (200 Extents).
 Logical volume vg01/lv01 successfully resized.
```
### Dateisystem erweitern
#### XFS
```bash
[user@host ~]$ xfs_growfs /mnt/data
```
>[!error] Achtung
>Hier wird der Mount-Point verwendet um das Dateisystem zu indentifizieren


#### EXT4
```bash
[user@host ~]$ resize2fs /dev/vg01/lv01
```
#### SWAP
```bash
[user@host ~]$ swapoff -v /dev/vg01/lv01
[user@host ~]$ lvextend -L +300M /dev/vg01/swap
[user@host ~]$ mkswap /dev/vg01/swap
[user@host ~]$ swapon /dev/vg01/swap
```
>[!error] Achtung
>Eine Swap-Partition kann nur erweitert werden, wenn sie deaktiviert ist.


## Reduzieren
### Volume Group
Mit dem Reduzieren einer VG werden nicht verwendete PVs aus der VG entfernt.

Mit dem [[Prompt|Befehl]] `pvmove /dev/vdb3` werden Daten von Extents auf dem PV `/dev/vdb3` auf ein anderes PV in derselben VG geschoben.

Mit `vgreduce vg01 /dev/vdb3` kann ein PV aus der Gruppen entfernt werden.

## Entfernen
Um LV-Komponenten zu entfernen kann wie folgt vorgegangen werden:

```bash
[user@host ~]$ unmount /mnt/data
[user@host ~]$ lvremove /dev/vg01/lv01
[user@host ~]$ vgremove vg01
[user@host ~]$ pvremove /dev/vdb1 /dev/vdb2
```


# Statusanzeige
Statusinformationen rund um LVM können mit den Programmen `pvdisplay`, `lvdisplay` und `vgdisplay` angezeigt werden.
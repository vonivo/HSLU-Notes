ZFS setzt auf Pooled storage.(siehe [[Enterprise Storage Array Technologies]])

## ZFS vs. normale FS
Bei ZFS werden Änderung gruppenweise als Transaktion durchgeführt.

## Struktur 
ZFS ist Als Merkle Tree aufgebaut:
![[Pasted image 20250108163642.png]]  

- Jeder Innere Knoten enhält die Hasches seiner Kind-Knoten
- Daten befinden sich nur auf der Leaf ebene.
- Um die Daten zu verfizieren, müssen nur die Hashes abgeglichen Werden O(log(n))
- Ein Merkle Signaturschema braucht nur eine Pulbic Key für 2^n Knoten Signature.

## Raid Z
Der Raid Z besitzt folgende Eckdaten:
- Variable Blockgrösse: 512B-128K
- Single und Double Parity
- Detektiert Silent Corruption
- Checksummen getriebene kombinatorische Rekonstruktion
- Schützt vor meheren Block Ausfällen wenn nicht reduziert.
- Raid-Z1 verwendet eine Parity Disk
- Raid-Z2 verwendet zwei Parity Disks
- Raid-Z3 verwendet 3 Parity Disks
=> Parity Disks sind striped.
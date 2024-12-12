Als Virtualisierung bezeichnet man die Nachbildung einer realen Maschine mit einem OS durch Software. 
- Diese Software nennt man Hypervisor

Der Hypervisor kann auf einem Host-OS oder direkt auf der Hardware aufsetzen:
![[Pasted image 20240530121619.png]]

- Der Desktop einer virtuellen Maschine kann über das Netz auf einem entfernten [[Rechner]] angezeigt werden (Remote Desktop Virtualization)
- Durch Virtualisierung können auf einem Host mehrere OS betrieben werden, der Host wird [[Multisession]]fähig.

# Containervirtualisierung 
Container enthalten im Gegensatz zur herkömmlichen Virtualisierung kein komplettes OS sondern nur einen seperaten Userspace der auf dem Gast-OS aufsetzt. 

Die Applikation in dem Container sieht nur die Ressourcen welche dem User-Space des Containers zugewiesen werden:

![[Pasted image 20240530122111.png]]
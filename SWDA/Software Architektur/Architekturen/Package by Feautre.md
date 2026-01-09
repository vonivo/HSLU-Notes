>[!Definition]
>Bei Package by Feature wird alles was **fachlich** zusammengehört in ein Package verpackt. Die Packages werden nun **vertikal** geschnitten.

Ab Java 9 kann ein Package nicht mehr auf verschiedene [[JAR|JARs]] aufgeteilt werden. Sprich [[Schichtenbildung]] funktioniert nicht mehr über Package by Feature.

Als Lösung müssen zuerst Packages vertikal erstellt und danach horizontal verfeinert werden.

![[Package_By_Feature.png]]
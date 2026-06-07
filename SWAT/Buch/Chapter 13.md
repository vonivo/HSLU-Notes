**What is another name for the microkernel architecture style?**
Plugin-Architektur

**Und what situations is it ok for plug-ing componente to depende on other plug-in components?**
Bei sehr komplexten, reinen Micro-Kernel-Applikation ist es okay Plug-Ins mit dependencies zu bentutzen, jedoch sollte es auch da möglichst vermieden werden da sonst die Komplexität extrem gesteigert wird.

**What are some of the tools and frameworks that can be used to manage plug-ins?**
- OSGI
- Penrose
- Jigsaw
- Prism (.NET)
- Einfache Maps

**What would you do if you had a third-party plug-in that didn't conform the standard plug-in contract in the the core system**
Wenn das Pulgin-Nicht geändert werden kann, würde ich ein Adapter schreiben welche diese Schnittstelle adaptiert. Im Idealfall wäre dann auch dieser Adapter ein Pluing, damit der Core nicht verändert werden müsste.

**Provide two examples of the the microkernel architectures tyle**
1. Maven
2. Eclipse
3. Jira

**What characteristics of the core system determine its degree of microker-ality**
Die Microkern-ality wird von Funktionsumfang des Kernels bestimmt, ist der Kern wirklich nur "gerade lauffähig" ist es eine pure Microkernel-Applikation. Wird mehr Funktionalität, z.B. einem Webrowser, unterstützt, ist es eher eine Applikation welche Pulgi-ins unterstützt.

**Why is the microkernel architecure always a single architecture quanta?**
Weil immer egal wie die Plug-ins angeschlossen sind, alle Funktionalität zuerst durch den Core gehen müssen.

**What is domain/architecture isomorphism**
Es bedeutet, dass die Struktur der SW die Struktur der Domäne wiederspiegelt.
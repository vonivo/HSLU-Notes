Es gibt verschieden Spezialprozessoren, welche für einen bestimmten Zweck entwickelt wurden.

## Mikrocontroller
- Enthält [[Mikroprozessor]] + Peripheriefunktionen + Speicher => **System on a Chip: SoC**
- Wird bei embedded Systemen verwendet. (Eingebettete Systeme)
- Bitbreit: 4-, 8-, 16- und 32-Bit-Mikrokontroller

## DSP digitaler Signalprozessor
- Für die Bearbeitung von digitalen Signalen (Bsp: Audio- oder Video)
- [[Mikroprozessor]] + Multiplizier-Addier-Werke (Multiply-Accumulate, MAC)

## Grafikprozessor GPU Graphics Processing Unit
Weitere Namen: Grafikchip, VPU (Visual Processing Unit)
- Massiv parallele Systeme: Streamprozoessoren (Shader), Textureinheiten, Ränder-Einheiten, etc.
- Aufgaben:
	- rechenintensive Aufgabe der 2D- und 3D-Computergrafik
	- Dekodieren des Bildaufbaus, Raytracing
	- Kryptomining
	- KI-Beschleunigung
- Ansteuerung über:
	- DirectX, OpenGL, Vulkan: für Grafiken
	- **OpenCL für allgemeine Rechenaufgaben**
- **IGP** Integrated Graphics Processor GPU integriert auf einer CPU


## Beschleuniger
Beschleuniger sind Prozessoren, welche für die Beschleunigung von KI-Prozessen eingesetzt werden.
- TPU -> Tensor Processing Unit
- NPU -> Neural Processing Unit

## Verschlüsselung in Hardware
Ver- und Entschlüsselung von Daten. (Bsp. Freescale c29x-Familie)


# Kontrollfragen
#flashcards/Rechenarchitekturen 

**Nennen Sie einige Arten von Spezialprozessoren.?**
?
uC, DSP, GPU, Krypto-Prozessor

**Was ist der Unterschied zwischen einer GPU und einem IGP?**
?
GPU: Graphics Processing Unit = Grafikprozessor in einem Chip IGP: Integrated Graphics Processor, intergrierte Grafik): GPU ist mit uP auf einem Die (in einem Chipgehäuse) oder im Chipsatz integriert
Der Token-Bucket wird benutzt, um einen starken Sender zu einer gemäßigten Senderate zu drosseln.

- Für jedes Token in einem Tockenbucket kann ein Paket übertragen werden.
- Die Token werden kontinuierlich wieder aufgefüllt.
![[TockenBucket2.png]]


## Beispiel
Ein starken Server soll auf 1000 Pakete/s gedrosselt werden.
Der Server besitzt eine Kapazität von 2'000 Pakete/s.
Der Füllstand des Buckets beträgt zu Beginn 4'000 Tokens
Der Bucket wird mit 1000 Token/s aufgefüllt

Wie Lange kann ein Server mit einem Burst von 2'000 Pakete senden bis er reguleirt wird?
$$
\begin{align}
\text{Zeit}&=\frac{\text{Füllstand}}{\text{Abfluss} - \text{Zustrom}} \\
&=\frac{40000}{2000-1000} \\
&=\frac{4000}{1000} \\
&=4s
\end{align}
$$
![[TockenBucket1.png]]
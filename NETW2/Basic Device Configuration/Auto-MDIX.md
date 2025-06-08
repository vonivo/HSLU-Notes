Automatic Medium Dependent Interface Crossover (auto-MDIX) ist eine Funktion die es dem Switch erlaubt, jedes Ethernet-Kable zu verwenden (Straight through/Crossover).

Wenn diese Funktion nicht zur Verfügung steht, muss ein geignetes Kabel verwendet werden:

| Gerät 1 | Gerät 2 | Kabel            |
| ------- | ------- | ---------------- |
| PC      | Swtich  | Straight-Through |
| PC      | Router  | Straight-Through |
| Router  | Switch  | Straight-Thr     |
Werde zwei gleiche Geräte miteinander Verbunden, müssen Corssover-Kabel verwendet werden.

Wenn auto-MDIX verwendet wird, müssen [[Duplex und Speed]] auf `auto` sein.

```
S1(config-if)# mdix auto

# abfragen
S1# show controllers ethernet-controller
```
Wenn in Python normale Listen oder Arrays verwendet werden, verhalten sich Operationen mit [[Matrizen]] unintuitiv:

```python
Person_1 = [5.0,5.0,5.5]
Person_2 = [4.5,4.0,4.5]

Person_1 + Person_2
>> [5.0, 5.0, 5.5, 4.5, 4.0, 4.5]

Person_1 * Person_2
>> TypeError                        Traceback (most recent call last)
Cell In[5], line 1
----> 1 Person_1 * Person_2
```

- Bei der Addition werden die Listen einfach zusammengeführt, anstatt addiert zu werden.
- Die Multiplikation erzeugt einen Fehler.

Mit **NumPy** werden Matrix-Operationen komponentenweise ausgeführt:
```python
import numpy as np
P_1 = np.array(Person_1)
P_2 = np.array(Person_2)

(P_1 + P_2)/2

>>array([4.75, 4.5 , 5.  ]
```

NumPy unterstützt viele Funktionen direkt:
- Splicing-Operator
- `min`
- `max`
- `mean`, auch über Achsen
- `sum`, auch über Achsen
- `unique` -> Unique-Werte inklusieve Count suchen
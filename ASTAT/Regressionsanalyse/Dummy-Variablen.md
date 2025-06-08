Mithilfe von Dummy-Variablen können nicht [[Statistisches Merkmal|metrische Merkmale]] berücksichtigt werden.

- [[Statistisches Merkmal|ordinale Merkmale]] werden in vernüftige Zahlen übersetzt.
- [[Statistisches Merkmal|nominale Merkmale]] werden mit Dummy-Variablen $0/1$ abgebildet.

Für $k$ Werte braucht es $k-1$ Dummy-Variablen. Ein Wert wird dann zur Baseline

**Beispiel:**
Abbildung des Merkmals Farbe ($F$, Rot/Grün/Blau) mit $k-1=3-1=2$ Dummy-Variablen.
```
Farbe   Dummy-Rot   Dummy-Blau
------------------------------
Rot       1           0
Blau      0           1
Grün      0           0
```

Die Farbe Gründ wird somit zu Baseline, da das Nicht-Vorhandensein von Blau oder Rot die Farbe grün impliziert.

In `pandas` gibt es die Methode [get_dummies](https://pandas.pydata.org/docs/reference/api/pandas.get_dummies.html) , welche es ermöglicht, kategorische Variablen in Dummy-Variablen zu transformieren. Dabei wird ein neues Dataframe erstellt, welches für jede Ausprägung eines gewählten Attributs einen entsprechenden `True` oder `False`-Wert beinhaltet, je nachdem, ob der entsprechende Eintrag der Kategorie angehört.
```python
pd.get_dummies(immo["PropertyType"]).head()


   Multiplex 	Single Family 	Townhouse
1 	True        False           False
2 	False   	  True 	          False
3 	False 	    True 	          False
4 	False 	    True 	          False
5 	False       True 	          False
```

Damit nun eine Multikollinearität vermieden werden kann (nicht erwünscht, da sonst Regressionskoeffizienten nicht eindeutig bestimmbar sind), wird die erste Dummy-Variable `Multiplex`
zur Baseline:
```python
pd.get_dummies(immo["PropertyType"],drop_first=True).head()

 	Single Family 	Townhouse
1   False           False
2   True 	          False
3   True 	          False
4   True 	          False
5   True 	          False
```

Um mit grossen Datenmengen in Python zu arbeiten, kann die Bibliothek Pandas (Panel Data) verwendet werden.

Pandas kann Dateien mit folgenden Formaten umgehen:
- csv
- ods, xls, xlsx, mdb
- sav-Datein für SPSS
- dta-Dateine für STATA

**Pandas** (Panel Data) ist ein Python-Modul, das schnelle und flexible Datenstrukturen bereitstellt, die das Arbeiten mit Daten in Matrix-Form einfach und intuitiv macht

## Beispiel
**Dataframe erstellen**
```python
names = ["Greater London","Tokyo","Paris","New York"]
population = [8663300,9272565,2229621,8491079]
area = [1572,627,105,784]

import pandas as pd

df = pd.DataFrame({"cities":names,"population":population,"area":area})
df.head(2)
```

|     | cities         | population | area |
| --- | -------------- | ---------- | ---- |
| 0   | Greater London | 8663300    | 1572 |
| 1   | Tokyo          | 9272565    | 627  |

## Funktionen
Pandas biete auch viele Funktionen welche sonst mittels [[NumPy]] errechnet werden müssen.

Einzelne Spaten werden über Indexes aufgerufen:
```python
df["population"]
df[["cities","area"]][0:1]
```

**Index neu Setzen**
```python
df.set_index("cities",inplace=True) # inplace=True -> direkt im df
```

**Über Index lokalisieren**
```python
df.loc["Tokyo"]
```

**Neues Attribut setzen**
```python
# neues attribut pop_density
df["pop_density"] = df["population"]/df["area"]
df
```

**PDF einlesen**
```python
gla_cities = pd.read_csv("Daten/GLA_World_Cities_2016.csv")
```
**NaN löschen**
```python
gla_cities.dropna(how="all")
```

**Umbenennen:**
```python
renamecols = {"Inland area in km2":"Area km2"}
gla_cities.rename(columns=renamecols,inplace=True)
gla_cities.columns
```

**Typecasting:**
```python
gla_cities["Population"] = \
gla_cities["Population"].str.replace(",","").astype(float)
gla_cities.head(3)
```

**Funktion für jeden Wert ausführen**
```python
gla_cities["City Size"] = \
gla_cities["Population (M)"].apply(city_size)
gla_cities.head(3)
```

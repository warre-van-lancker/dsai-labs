# Cheatsheet 2: Python & Pandas (Practice)

## 1. Belangrijkste Libraries & Imports

```python
import numpy as np                                  # Wiskunde en arrays
import scipy.stats as stats                         # Statistische testen
import pandas as pd                                 # DataFrames en datamanipulatie
from pandas.api.types import CategoricalDtype       # Voor ordinale categorische data
import matplotlib.pyplot as plt                     # Basis visualisatie
import seaborn as sns                               # Geavanceerde visualisatie

```

## 2. Data Laden & Inspecteren

```python
# Laden van een CSV (lokaal of via URL)
df = pd.read_csv('url_of_pad_naar_file.csv')

# Laden met datum-parsing en indexinstelling
df = pd.read_csv('file.csv', index_col=0, parse_dates=True)

# Inspectie-commando's
df.head(5)                 # Eerste 5 rijen bekijken
df.shape                   # Geeft (aantal_rijen, aantal_kolommen)
df.info()                  # Overzicht van datatypes en missende waarden
df.dtypes                  # Datatypes per kolom
df.dtypes.value_counts()   # Telling van het aantal kolommen per datatype
df.count()                 # Aantal niet-missende waarden per kolom

```

## 3. Kolomtypes Aanpassen (Kwalitatief / Ordinaal)

```python
# Converteren naar een standaard nominale categorie
df['Survived'] = df['Survived'].astype('category')

# Converteren naar een Ordinale categorie (met vaste volgorde)
custom_order = CategoricalDtype(categories=['S', 'C', 'Q'], ordered=True)
df['Embarked'] = df['Embarked'].astype(custom_order)

```

## 4. Data Selecteren & Filteren

```python
# Kolommen selecteren
df['Age']                      # Voorkeursmanier (Series)
df[['Name', 'Age']]            # Meerdere kolommen (DataFrame)
df.iloc[:, 2:4]                # Selecteren op basis van kolompositie (index 2 tot 4 exclusief)

# Rijen selecteren
df.iloc[5]                     # Rij met indexpositie 5
df.iloc[0:4]                   # Eerste 4 rijen

# Filteren op conditie (Boolean Indexing)
df[df.Age < 18]                # Filteren: enkel minderjarigen
df[df.Age < 18][['Age', 'Sex']] # Filteren en specifieke kolommen behouden

# Filteren met .query() (handig voor complexe condities)
df.query("(Sex == 'male') and (Age < 18)")

```

## 5. Kolommen Verwijderen & Missende Data (NaN)

```python
# Kolom definitief verwijderen (inplace=True wijzigt het originele DataFrame)
df = df.drop("PassengerId", axis="columns")

# Controleren op missende waarden
df.isnull()                    # True als waarde NaN is
df.notnull().sum()             # Aantal niet-missende waarden per kolom

# Omgaan met NaN
df_cleaned = df.dropna()       # Verwijder elke rij die minstens één NaN bevat
df_cleaned = df.dropna(how="all") # Verwijder rij enkel als ALLES NaN is

# Imputeren (missende waarden opvullen)
avg_age = df['Age'].mean()
df = df.fillna(value={'Age': avg_age}) # Vul NaN in 'Age' op met het gemiddelde

```

## 6. Nieuwe Kolommen Berekenen & Mappen

```python
# Element-wise berekening (zonder loops!)
df['london_mg'] = df['station_london'] * 1.882
df['ratio'] = df['station_paris'] / df['station_antwerp']

# Waarden vervangen via een Dictionary (Mapping)
df['Sex'] = df['Sex'].map({'male': 0, 'female': 1})

# Waarden transformeren via een custom functie
def age_to_category(age):
    if age < 12: return "child"
    if age < 18: return "teen"
    return "adult"

df['AgeCategory'] = df['Age'].map(age_to_category)

```

## 7. Werken met Datetime

```python
# Verschil berekenen tussen opeenvolgende tijdstippen (uitgedrukt in uren)
df['timespan'] = df.index.to_series().diff().dt.total_seconds() / 3600

# Controleren of de tijdsstappen consistent zijn
df.timespan.value_counts()

```
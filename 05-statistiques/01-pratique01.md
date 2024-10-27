## 📊 Cours et Exercices de Statistiques en Python

### 1. Installation des Bibliothèques

Assurez-vous que les bibliothèques nécessaires sont installées. Colab les a souvent déjà installées, mais cela garantit qu’elles sont à jour.

```python
# Installation des bibliothèques
!pip install numpy pandas
```

### 2. Importation des Bibliothèques

On commence par importer **NumPy** et **pandas** :

```python
import numpy as np
import pandas as pd
```

---

### 3. Création d'un Ensemble de Données Simple

Commençons par créer un ensemble de données représentant les âges des étudiants :

```python
# Création d'un DataFrame avec des âges d'élèves
ages = pd.DataFrame({"Age": [8, 9, 10, 10, 11, 11, 12]})
ages
```

---

### 4. Concepts de Base : Moyenne, Médiane, Mode

#### Moyenne

La moyenne est la somme des valeurs divisée par leur nombre.

```python
# Calcul de la moyenne des âges
mean_age = ages["Age"].mean()
print("Moyenne:", mean_age)
```

#### Médiane

La médiane est la valeur du milieu dans une liste triée.

```python
# Calcul de la médiane des âges
median_age = ages["Age"].median()
print("Médiane:", median_age)
```

#### Mode

Le mode est la valeur la plus fréquente.

```python
# Calcul du mode des âges
mode_age = ages["Age"].mode()[0]
print("Mode:", mode_age)
```

---

### 🚀 Exercice 1 : Calculer Moyenne, Médiane, et Mode pour une Nouvelle Liste

1. Créez une liste de nombres représentant la taille (en cm) d'un groupe de personnes.
2. Utilisez les fonctions `mean`, `median`, et `mode` de pandas pour calculer la moyenne, la médiane et le mode de cette liste.

*Code de départ :*

```python
# Remplacez les valeurs par votre propre liste de tailles
heights = pd.DataFrame({"Height": [150, 160, 170, 160, 155, 150, 165, 170, 160]})

# Calcul de la moyenne, médiane, et mode des tailles
mean_height = heights["Height"].mean()
median_height = heights["Height"].median()
mode_height = heights["Height"].mode()[0]

print("Moyenne des tailles:", mean_height)
print("Médiane des tailles:", median_height)
print("Mode des tailles:", mode_height)
```

---

### 5. Étendue

L'étendue est la différence entre la valeur maximale et minimale.

```python
# Calcul de l'étendue des âges
range_age = ages["Age"].max() - ages["Age"].min()
print("Étendue:", range_age)
```

### 🚀 Exercice 2 : Calculer l'Étendue

Créez une liste de notes d'examen (de 0 à 20) et trouvez l'étendue de ces notes.

---

### 6. Variance et Écart-Type

La variance et l'écart-type permettent de voir comment les valeurs sont dispersées autour de la moyenne.

#### Variance

```python
# Calcul de la variance des âges
variance_age = ages["Age"].var()
print("Variance:", variance_age)
```

#### Écart-Type

```python
# Calcul de l'écart-type des âges
std_dev_age = ages["Age"].std()
print("Écart-type:", std_dev_age)
```

### 🚀 Exercice 3 : Calculer Variance et Écart-Type

1. Créez une liste de revenus mensuels de plusieurs personnes.
2. Calculez la variance et l’écart-type pour voir comment les revenus sont dispersés autour de la moyenne.

---

### 7. Diagrammes Simples pour Résumer les Données

Visualiser les données aide à mieux les comprendre.

```python
import matplotlib.pyplot as plt

# Création d'un diagramme à barres
ages["Age"].value_counts().plot(kind='bar', title="Répartition des Âges")
plt.xlabel("Âge")
plt.ylabel("Fréquence")
plt.show()
```

### 🚀 Exercice 4 : Créer un Diagramme à Barres

Utilisez une liste des matières préférées de vos amis et créez un diagramme à barres pour représenter les préférences.

---

### 8. Probabilité

Calculons la probabilité d'obtenir une certaine note dans un groupe.

*Exemple :* Si un groupe a les notes suivantes, quelle est la probabilité d’obtenir la note 10 ?

```python
# Liste de notes
notes = pd.Series([8, 9, 10, 10, 11, 12, 12, 10])

# Probabilité d'obtenir un 10
prob_10 = (notes == 10).mean()
print("Probabilité d'obtenir un 10:", prob_10)
```

### 🚀 Exercice 5 : Calculer une Probabilité

Créez une liste des couleurs préférées d'un groupe de personnes. Calculez la probabilité que la couleur préférée soit "bleue".

---

### 9. Quartiles et Interquartile

Les quartiles divisent les données en quatre parties égales.

```python
# Calcul des quartiles
q1 = ages["Age"].quantile(0.25)
q2 = ages["Age"].quantile(0.5)  # Médiane
q3 = ages["Age"].quantile(0.75)

# Calcul de l'écart interquartile
iqr = q3 - q1

print("Q1:", q1, " | Médiane (Q2):", q2, " | Q3:", q3)
print("Écart interquartile:", iqr)
```

### 🚀 Exercice 6 : Calcul des Quartiles et de l'Écart Interquartile

1. Créez une liste de dépenses hebdomadaires.
2. Trouvez les quartiles (Q1, Médiane, Q3) et l’écart interquartile.

---

### 10. Corrélations

Voyons comment deux variables sont liées, par exemple la taille et le poids :

```python
# Création d'un DataFrame avec taille et poids
data = pd.DataFrame({
    "Taille": [150, 160, 170, 180, 190],
    "Poids": [55, 60, 65, 70, 75]
})

# Calcul de la corrélation
correlation = data.corr().iloc[0, 1]
print("Corrélation entre Taille et Poids:", correlation)
```

### 🚀 Exercice 7 : Calculer une Corrélation

Créez une liste de valeurs pour les heures d’étude et les notes d'examens. Utilisez `.corr()` pour déterminer s’il y a un lien entre le temps d’étude et les notes.


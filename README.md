# Intervalle de confiance en Python

## Présentation du projet

Ce projet est un notebook pédagogique de science des données consacré aux intervalles de confiance en Python.

L’objectif est d’expliquer, à partir d’un exemple concret et visuel, comment interpréter une moyenne, une proportion ou une tendance statistique en tenant compte de l’incertitude.

Le notebook utilise le dataset `tips` de Seaborn, qui contient des données liées à des additions et des pourboires dans un restaurant. Ce contexte simple permet de comprendre plus facilement pourquoi une moyenne observée dans un échantillon ne doit pas être interprétée comme une certitude absolue.

## Objectif pédagogique

Le projet vise à répondre à une question simple :

> Lorsqu’on calcule une moyenne à partir d’un échantillon, quelle est l’incertitude autour de cette estimation ?

Le notebook montre comment utiliser Python pour :

- calculer une moyenne observée ;
- comprendre la notion d’échantillon ;
- calculer un intervalle de confiance à 95 % ;
- visualiser l’incertitude autour d’une moyenne ;
- comparer des moyennes entre groupes ;
- interpréter une bande de confiance autour d’une tendance ;
- comprendre l’effet de la taille de l’échantillon ;
- utiliser une approche bootstrap ;
- éviter les erreurs fréquentes d’interprétation.

## Notebook

Le notebook principal du projet est disponible ici :

[Ouvrir le notebook Jupyter](Intervalle_Confiance_Python_FR.ipynb)

Ce notebook présente une progression didactique, avec des explications en français, des exemples de code Python et plusieurs visualisations classiques utilisées pour représenter les intervalles de confiance.

## Jeu de données utilisé

Le projet utilise le dataset `tips`, disponible directement avec Seaborn.

Ce jeu de données contient des informations sur des repas dans un restaurant, notamment :

| Variable | Description |
|---|---|
| `total_bill` | Montant total de l’addition |
| `tip` | Montant du pourboire |
| `sex` | Sexe du client |
| `smoker` | Indication si la table est associée à un client fumeur |
| `day` | Jour du repas |
| `time` | Moment du repas, déjeuner ou dîner |
| `size` | Nombre de personnes à table |

Ce dataset est particulièrement adapté à un projet pédagogique, car il permet d’expliquer les intervalles de confiance avec des exemples simples et concrets.

## Approche méthodologique

Le notebook suit une démarche progressive.

### 1. Chargement des bibliothèques

Le projet utilise les bibliothèques Python nécessaires à l’analyse statistique et à la visualisation :

- NumPy ;
- Pandas ;
- Seaborn ;
- Matplotlib ;
- SciPy.

### 2. Chargement du dataset

Le notebook charge le dataset `tips` avec la fonction :

```python
sns.load_dataset("tips")
```

Une solution de repli est également prévue dans le notebook afin de créer un petit jeu de données synthétique si le dataset intégré de Seaborn n’est pas accessible dans l’environnement local.

### 3. Statistiques descriptives

Le notebook commence par explorer les variables principales, notamment :

- le montant moyen des additions ;
- le montant moyen des pourboires ;
- la dispersion des valeurs ;
- le nombre d’observations disponibles.

Cette étape permet d’introduire une idée essentielle : une moyenne observée est une estimation calculée à partir d’un échantillon.

### 4. Calcul manuel d’un intervalle de confiance

Le notebook calcule un intervalle de confiance à 95 % autour d’une moyenne à l’aide de la loi de Student.

Cette étape permet de comprendre les éléments suivants :

| Élément | Rôle |
|---|---|
| Moyenne | Valeur observée dans l’échantillon |
| Écart-type | Dispersion des valeurs |
| Erreur standard | Incertitude autour de la moyenne |
| Marge d’erreur | Distance ajoutée autour de la moyenne |
| Bornes de l’intervalle | Limites inférieure et supérieure de l’estimation |

### 5. Visualisation des intervalles de confiance

Le notebook utilise plusieurs visualisations classiques avec Seaborn.

#### Barplot

Le `barplot` permet de comparer l’addition moyenne par jour avec un intervalle de confiance à 95 %.

Il montre que chaque moyenne observée doit être interprétée avec son incertitude.

#### Pointplot

Le `pointplot` permet de comparer des moyennes selon plusieurs catégories, par exemple le jour et le moment du repas.

Les points représentent les moyennes et les segments verticaux représentent les intervalles de confiance.

#### Regplot

Le `regplot` montre la relation entre le montant de l’addition et le montant du pourboire.

La bande autour de la ligne représente l’intervalle de confiance de la tendance estimée.

#### Lineplot

Le `lineplot` permet d’observer l’évolution du pourboire moyen selon la taille du groupe à table.

La bande autour de la ligne représente l’incertitude autour de la moyenne estimée.

### 6. Effet de la taille de l’échantillon

Le notebook montre que la taille de l’échantillon influence directement la précision de l’estimation.

En général :

- un petit échantillon produit un intervalle plus large ;
- un grand échantillon produit un intervalle plus étroit ;
- une estimation basée sur plus d’observations est souvent plus stable.

### 7. Intervalle de confiance pour une proportion

Le notebook montre également comment calculer un intervalle de confiance pour une proportion.

Exemple :

> Quelle proportion des repas observés correspond au dîner ?

Cette section montre que les intervalles de confiance ne s’appliquent pas seulement aux moyennes, mais aussi aux proportions.

### 8. Bootstrap

Le notebook introduit aussi la méthode bootstrap.

Le bootstrap consiste à recréer plusieurs échantillons à partir des données observées, avec remise, afin d’observer comment une estimation varie.

Cette approche permet de visualiser l’incertitude de manière intuitive, sans dépendre uniquement d’une formule théorique.

## Interprétation des résultats

Une idée importante du projet est de distinguer une moyenne observée d’une estimation fiable.

Par exemple, si le pourboire moyen observé est de 3,00 dollars et que l’intervalle de confiance à 95 % est `[2.82, 3.17]`, cela ne signifie pas que 95 % des pourboires sont situés dans cet intervalle.

La bonne interprétation est la suivante :

> À partir des données disponibles, la moyenne réelle des pourboires se situe probablement dans cette plage de valeurs plausibles.

L’intervalle de confiance sert donc à éviter de présenter une estimation comme une certitude.

## Technologies utilisées

- Python ;
- Pandas ;
- NumPy ;
- Seaborn ;
- Matplotlib ;
- SciPy ;
- Jupyter Notebook.

## Structure du projet

```text
python-confidence-intervals-tutorial/
│
├── Intervalle_Confiance_Python_FR.ipynb
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

## Installation locale

### 1. Cloner le dépôt

```bash
git clone https://github.com/aidatamodels/python-confidence-intervals-tutorial.git
```

### 2. Accéder au dossier du projet

```bash
cd python-confidence-intervals-tutorial
```

### 3. Installer les dépendances

```bash
pip install -r requirements.txt
```

Sur Windows, il est aussi possible d’utiliser :

```bash
py -m pip install -r requirements.txt
```

### 4. Ouvrir le notebook

```bash
jupyter notebook
```

Ou ouvrir directement le fichier `Intervalle_Confiance_Python_FR.ipynb` dans Visual Studio Code ou Anaconda Navigator.

## Dépendances recommandées

Le fichier `requirements.txt` contient les bibliothèques nécessaires à l’exécution du notebook.

```text
numpy>=1.26,<2.0
pandas>=2.2,<3.0
seaborn>=0.13.2
matplotlib>=3.8
scipy>=1.11
jupyter>=1.0
```

Il est recommandé d’utiliser une version de `pandas` inférieure à 3.0 afin d’éviter certaines incompatibilités avec des versions plus anciennes de Seaborn.

## Limites du projet

Ce projet est conçu à des fins pédagogiques.

Les résultats présentés servent à illustrer les concepts statistiques et ne doivent pas être interprétés comme une étude réelle sur les habitudes de consommation ou de pourboire dans les restaurants.

Les principales limites sont les suivantes :

- le dataset est de petite taille ;
- les données servent principalement à l’apprentissage ;
- les résultats dépendent de l’échantillon disponible ;
- les intervalles de confiance supposent une interprétation statistique rigoureuse ;
- les visualisations doivent être lues avec prudence, surtout lorsque les groupes contiennent peu d’observations.

## À retenir

Ce notebook montre que, dans une analyse de données, il ne suffit pas de calculer une moyenne.

Il est souvent nécessaire d’accompagner cette moyenne d’une mesure d’incertitude.

L’intervalle de confiance permet justement de répondre à cette exigence : il transforme une valeur unique en une plage de valeurs plausibles, ce qui rend l’analyse plus prudente, plus transparente et plus professionnelle.

## Licence

Le code source du projet est distribué sous licence MIT.

Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## Auteur

Projet développé par `aidatamodels` dans le cadre d’une démarche pédagogique en science des données, statistique appliquée et visualisation avec Python.

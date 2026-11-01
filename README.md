# 📊 Projet d'analyse des ventes et commandes

## 🎯 Objectif du projet pédagogique

Ce projet a été réalisé dans un objectif **d'apprentissage et de mise en pratique de Power BI**.

L'objectif est de mettre en œuvre les différentes étapes nécessaires à la réalisation d'une analyse de données, depuis **l'importation et la préparation des données jusqu'à leur visualisation et leur analyse**.

Le projet a été réalisé en suivant une formation consacrée à Power BI proposée par la chaîne **Sébastien Daviot – Expertise Data**.

Cette formation aborde différentes notions clés de Power BI, notamment :

- la préparation des données ;
- le nettoyage et la transformation des données ;
- la modélisation des données ;
- la création de relations entre les tables ;
- la création de mesures ;
- la conception de visualisations ;
- la construction d'un rapport interactif.

> **Projet pédagogique :** ce projet a été réalisé dans le cadre de mon apprentissage de Power BI. Il ne représente pas une analyse réalisée pour une entreprise réelle.

---

## 📂 Source des données

Les données utilisées dans ce projet proviennent du jeu de données mis à disposition dans le cadre de la formation.

[Accéder aux données](https://drive.google.com/drive/folders/1y3BF2YPVCgtPYa5dvQa6NYdNYq7QC_d-?usp=sharing)

---

## 🛠️ Outils utilisés

### Power BI

Utilisé pour :

- la modélisation des données ;
- la création des mesures ;
- la conception du rapport ;
- la création des visualisations ;
- l'analyse des données.

### Power Query

Utilisé pour la **préparation et la transformation des données**, notamment :

- le nettoyage des données ;
- la vérification des types de données ;
- le renommage des colonnes ;
- la transformation des données ;
- la normalisation du modèle ;
- la création de tables de dimensions.

---

# 🔄 Évolution du projet

## 1. Importation et découverte des données

La première étape a consisté à récupérer le jeu de données fourni dans le cadre de la formation, puis à l'importer dans Power BI.

Avant de procéder aux transformations, une phase de découverte des données a été réalisée afin de mieux comprendre :

- la structure du jeu de données ;
- les différentes variables disponibles ;
- les valeurs présentes dans les colonnes ;
- les types de données ;
- les informations représentées par chaque variable.

Cette étape permet de mieux comprendre les données avant leur transformation et leur utilisation dans le modèle.

---

## 2. Vérification et transformation des données

Plusieurs opérations de préparation ont ensuite été réalisées avec Power Query.

### Vérification des types de données

Les types de données des différentes colonnes ont été vérifiés et adaptés lorsque cela était nécessaire.

### Renommage des colonnes

Afin de rendre le modèle plus lisible et plus facilement exploitable, les colonnes ont été renommées en français.

| Colonne d'origine | Nouvelle appellation |
|---|---|
| `OrderID` | Id commande |
| `CustomerID` | Id client |
| `CompanyName` | Nom client |
| `ProductID` | Id produit |
| `ProductName` | Nom produit |
| `Category` | Catégorie produit |
| `RegionID` | Id région |
| `RegionName` | Nom région |
| `OrderDate` | Date commande |
| `Quantity` | Quantité |
| `UnitPrice` | Prix unitaire |
| `TotalPrice` | Prix total |
| `OrderStatus` | Statut commande |

---

## 3. Normalisation et création des tables de dimensions

Afin d'améliorer la structure du modèle de données, certaines informations ont été séparées dans des tables de dimensions.

### 👤 Table Clients

La table `Clients` contient notamment :

- `Id client`
- `Nom client`

### 📦 Table Produits

La table `Produits` contient notamment :

- `Id produit`
- `Nom produit`
- `Catégorie produit`

### 🌍 Table Régions

La table `Régions` contient notamment :

- `Id région`
- `Nom région`

Cette organisation permet de séparer les informations descriptives des données liées aux commandes et de construire un modèle de données plus structuré.

---

## 📈 Suite du projet

Les étapes suivantes du projet portent sur :

- la mise en place du modèle de données ;
- la création des relations entre les tables ;
- la création des mesures DAX ;
- la création des indicateurs nécessaires à l'analyse ;
- la conception des différentes visualisations ;
- la construction du tableau de bord ;
- l'analyse des résultats.

---

## 🎓 Objectif personnel

Ce projet constitue un exercice pratique destiné à **mettre en application les connaissances acquises sur Power BI** et à mieux comprendre l'ensemble du processus de réalisation d'un projet de Business Intelligence :

**Données → Préparation → Modélisation → Analyse → Visualisation**

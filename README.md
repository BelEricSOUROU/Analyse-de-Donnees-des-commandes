# 📊 Projet Power BI — Analyse des ventes et des commandes

## 📌 Présentation

Ce projet consiste à concevoir un tableau de bord interactif avec Power BI afin d’analyser les ventes et les commandes d’une entreprise.

Réalisé dans le cadre de mon apprentissage de la Business Intelligence, ce projet me permet de mettre en pratique les principales étapes d’un processus d’analyse de données : préparation, modélisation, création de mesures et visualisation.

Il s’agit d’un projet pédagogique réalisé à partir d’un jeu de données fourni dans le cadre d’un atelier de formation Power BI.

## 🎯 Objectif

L’objectif est de transformer des données brutes en informations exploitables grâce à un rapport interactif permettant de suivre l’activité commerciale.

Le projet vise notamment à :

- Analyser le chiffre d’affaires et les volumes de ventes.
- Suivre le nombre de commandes et le montant moyen par commande.
- Étudier la répartition des ventes par région et par catégorie de produits.
- Analyser les commandes annulées et leur impact sur les ventes.
- Explorer les données selon plusieurs critères grâce aux filtres et aux interactions du rapport.

## 📊 Données

Le projet utilise le fichier `sales_2.csv`, fourni dans le cadre de l’atelier de formation.

[Accéder aux données sur Google Drive](https://drive.google.com/drive/folders/1y3BF2YPVCgtPYa5dvQa6NYdNYq7QC_d-?usp=sharing)

Le jeu de données contient des informations relatives aux :

- Commandes : identifiant, date et statut.
- Clients : identifiant et nom.
- Produits : identifiant, nom et catégorie.
- Régions : identifiant et nom.
- Ventes : quantités, prix unitaires et montants totaux.

Ces informations permettent d’étudier les ventes selon plusieurs dimensions et d’analyser les commandes annulées.

## 🧹 Préparation des données

La préparation des données est réalisée avec Power Query dans Power BI Desktop.

Les principales opérations prévues dans le processus de préparation sont :

- Importation du fichier CSV.
- Analyse de la qualité, de la distribution et du profil des colonnes.
- Vérification et adaptation des types de données.
- Renommage des colonnes pour améliorer leur lisibilité.
- Création de tables de référence à partir de la table d’origine.
- Vérification de la cohérence des identifiants des clients et des produits.
- Suppression des colonnes devenues inutiles.
- Préparation de la table de ventes destinée au modèle final.

Les colonnes sont renommées en français afin de faciliter la lecture et la compréhension du modèle.

## 🏗️ Modèle de données

Le modèle de données repose sur une table centrale `Ventes` et trois tables de dimensions :

| Table      | Informations principales                     |
| ---------- | -------------------------------------------- |
| `Ventes`   | Commandes, dates, quantités, prix et statuts |
| `Clients`  | Identifiant et nom du client                 |
| `Produits` | Identifiant, nom et catégorie du produit     |
| `Régions`  | Identifiant et nom de la région              |

Cette organisation vise à séparer les informations descriptives des données de vente et à structurer les relations entre les tables.

Les relations sont vérifiées dans la vue Modélisation de Power BI afin de permettre l’analyse des ventes par client, produit, région et période.

## 🧮 Mesures DAX

Les mesures DAX servent à calculer les principaux indicateurs du tableau de bord.

### Indicateurs de suivi des ventes

| Mesure                | Description                    |
| --------------------- | ------------------------------ |
| `Total ventes`        | Montant total des ventes       |
| `Nombre de commandes` | Nombre de commandes distinctes |
| `Quantité vendue`     | Quantité totale vendue         |
| `Commande moyenne`    | Montant moyen par commande     |

Les formules utilisées dans l’atelier sont les suivantes :

```dax
Total ventes =
SUM(Ventes[Prix total])
```

```dax
Nombre de commandes =
DISTINCTCOUNT(Ventes[Id commande])
```

```dax
Quantité vendue =
SUM(Ventes[Quantité])
```

```dax
Commande moyenne =
DIVIDE([Total ventes], [Nombre de commandes])
```

### Indicateurs des commandes annulées

Trois mesures complémentaires sont prévues pour analyser les commandes dont le statut est `Cancelled` :

- `Total commandes annulées` : nombre de commandes annulées.
- `Montant commandes annulées` : montant associé aux commandes annulées.
- `Pourcentage commandes annulées` : proportion des commandes annulées parmi les commandes comptabilisées.

Ces indicateurs permettent de compléter le suivi des ventes par une analyse spécifique des annulations.

## 📈 Visualisations

La page **Suivi ventes** regroupe les principaux indicateurs et graphiques nécessaires à l’analyse de l’activité commerciale.

Les visualisations prévues comprennent :

- **Cartes KPI** : chiffre d’affaires, nombre de commandes, quantité vendue et commande moyenne.
- **Graphique temporel** : évolution du chiffre d’affaires et des volumes de ventes.
- **Graphique en barres horizontales** : comparaison du chiffre d’affaires par région.
- **Graphique en anneau** : répartition du chiffre d’affaires par catégorie de produits.
- **Tableau détaillé** : consultation des informations relatives aux commandes.

L’objectif est de présenter une vue synthétique de l’activité tout en permettant d’accéder aux détails nécessaires à l’analyse.

## 🔎 Analyse des commandes annulées

Une seconde page, **Commandes annulées**, est consacrée à l’étude des annulations.

Elle s’appuie sur les indicateurs et visualisations suivants :

- KPI du nombre de commandes annulées, de leur montant et de leur pourcentage.
- Courbe d’évolution du pourcentage et du nombre de commandes annulées.
- Histogramme de la répartition des annulations par région.
- Treemap pour analyser le montant des commandes annulées par catégorie et par produit.
- Graphique en ruban pour étudier l’évolution trimestrielle des commandes annulées par produit.

Cette page vise à mieux comprendre la répartition des annulations et leur évolution au cours du temps.

## 🎛️ Fonctionnalités interactives

Le rapport prévoit plusieurs fonctionnalités destinées à faciliter l’exploration des données :

- **Filtre de dates** : sélectionner une période d’analyse.
- **Filtre de statut** : afficher les commandes selon leur statut.
- **Filtre de région** : analyser les résultats par zone géographique.
- **Menu de navigation** : passer d’une page du rapport à l’autre.
- **Info-bulles personnalisées** : afficher des informations complémentaires au survol de certaines visualisations.

Ces fonctionnalités permettent d’explorer les données selon différents critères et d’approfondir l’analyse sans multiplier les graphiques sur les pages principales.

## 🛠️ Technologies utilisées

- **Power BI Desktop** : conception du rapport et modélisation des données.
- **Power Query** : préparation et transformation des données.
- **DAX (Data Analysis Expressions)** : création des mesures et indicateurs.
- **Power BI Service** : publication du rapport en ligne, lorsque cette étape est réalisée.

## 📸 Aperçu du dashboard

Les captures d’écran du rapport seront ajoutées dans cette section afin de présenter les principales pages et visualisations du projet.

### Suivi ventes

\<!-- Ajouter ici une capture d'écran de la page Suivi ventes -->
![Page d'accueil du rapport Power BI](../Mes visuels/{2C81AA30-5299-4BF0-B562-7AC11F48692C}.png)

### Commandes annulées

\<!-- Ajouter ici une capture d'écran de la page Commandes annulées -->

## 🚀 Installation / utilisation

Pour consulter ou reproduire le projet :

1. Installer Power BI Desktop.
2. Récupérer le fichier `sales_2.csv` à partir de la source indiquée dans la section Données.
3. Ouvrir le fichier Power BI `.pbix` du projet, lorsqu’il est disponible.
4. Si nécessaire, mettre à jour le chemin d’accès au fichier CSV dans les paramètres de la source de données.
5. Actualiser les données.
6. Explorer les différentes pages du rapport et utiliser les filtres pour analyser les ventes et les commandes annulées.

La consultation du rapport publié dans Power BI Service dépend de son mode de partage et des autorisations d’accès.

## 💡 Principaux enseignements

Ce projet permet de mettre en pratique plusieurs notions importantes de la Business Intelligence :

- L’importance du nettoyage et de la qualité des données avant l’analyse.
- L’intérêt de structurer les données en tables de dimensions et table de faits.
- Le rôle des relations dans la cohérence des analyses.
- L’utilisation de mesures DAX pour construire des indicateurs dynamiques.
- Le choix de visualisations adaptées aux questions métier.
- L’intérêt des filtres, de la navigation et des info-bulles pour améliorer l’exploration des données.

Les enseignements métier et les résultats chiffrés seront complétés après validation du rapport final et analyse des données.

## 🔮 Améliorations possibles

Plusieurs évolutions pourront être envisagées dans une version ultérieure :

- Ajouter des indicateurs complémentaires pour approfondir l’analyse commerciale.
- Comparer les performances entre différentes périodes.
- Améliorer la présentation des résultats avec des commentaires analytiques.
- Enrichir le rapport avec de nouvelles visualisations adaptées aux besoins d’analyse.
- Documenter les résultats observés à partir des données réelles.
- Améliorer la présentation du projet dans le portfolio avec des captures d’écran et un lien de consultation, si le rapport est publié et partageable.

---

**Projet pédagogique réalisé dans le cadre de mon apprentissage de Power BI et de la Business Intelligence.**

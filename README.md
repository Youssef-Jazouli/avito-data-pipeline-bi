# 1. Nom du projet

**Nom du projet :** Avito Data Pipeline BI — Tableau de Bord Power BI du Marché Immobilier

---

# 2. Présentation du projet

Ce projet est une analyse de données couplée à un tableau de bord Power BI interactif qui permet de collecter, structurer et visualiser des annonces immobilières marocaines afin d'en comprendre les tendances de prix, la répartition géographique et l'évolution dans le temps.

Il s'adresse principalement aux personnes souhaitant étudier le marché immobilier marocain : acheteurs, investisseurs, agents immobiliers ou toute personne intéressée par l'analyse de données appliquée à l'immobilier.

Son objectif principal est de rendre lisibles et exploitables des données brutes issues du scraping d'annonces (site Avito), en les transformant en indicateurs clés (KPI), graphiques et cartes interactives.

---

# 3. Problématique

Le problème identifié est que les données d'annonces immobilières publiées en ligne sont dispersées, non structurées et difficiles à comparer d'une ville à l'autre, ce qui rend complexe l'analyse du marché (prix moyen, prix au m², tendances par ville ou par période).

La solution proposée permet de centraliser ces données dans un rapport Power BI unique, organisé en plusieurs pages thématiques (vue globale, prix, géographie, tendances), avec des filtres interactifs sur le prix et la surface pour explorer les données selon différents axes.

---

# 4. Fonctionnalités principales

- Visualiser le nombre d'annonces et leur évolution dans le temps
- Comparer les prix moyens et les prix au m² par ville
- Filtrer les annonces par plage de prix (MAD) et par surface (m²)
- Explorer la répartition géographique des annonces sur une carte
- Analyser les corrélations entre surface et prix via un nuage de points
- Suivre l'activité des annonces par jour de la semaine

---

# 5. Technologies utilisées

| Technologie | Utilisation dans le projet |
|-------------|----------------------------|
| Power BI Desktop | Conception et modélisation du rapport, création des visuels et des mesures |
| Power BI Service (Cloud) | Hébergement et création initiale du rapport |
| Scraping web (données Avito) | Collecte des données brutes d'annonces immobilières |
| DAX | Écriture des mesures calculées (ex. `Total_Annonces`) |
| GitHub | Versionnement et partage du projet |

> Nous avons utilisé **Power BI Desktop** pour construire les 4 pages du rapport, définir les mesures et connecter le modèle de données aux annonces collectées.

---

# 6. Installation et lancement

## 6.1 Prérequis

Pour utiliser ce projet, vous devez disposer de :

- Power BI Desktop (version 2.153.777.0 ou supérieure)
- Un compte Power BI Service (Cloud) si vous souhaitez republier ou actualiser le rapport en ligne
- Git (pour cloner le dépôt)
- Un accès à la source de données (fichier ou base issue du scraping Avito) pour actualiser le rapport
- Une connexion internet pour l'actualisation des données

---

## 6.2 Cloner le dépôt

```bash
git clone https://github.com/Youssef-Jazouli/avito-data-pipeline-bi.git
```

---

## 6.3 Ouvrir le dossier

```bash
cd avito-data-pipeline-bi
```

---

## 6.4 Installer les dépendances

Ce projet ne nécessite pas d'installation de dépendances logicielles (pas de `npm install`). Il suffit d'avoir Power BI Desktop installé sur votre machine.

---

## 6.5 Variables d'environnement

Ce projet n'utilise pas de fichier `.env` : il n'y a pas de backend, de base de données ni de clé API à configurer. La seule configuration nécessaire concerne la source de données à connecter dans Power BI pour l'actualisation.

---

## 6.6 Lancer le projet

```bash
Ouvrir le fichier "breif de power bi.pbix" avec Power BI Desktop
```

---

## 6.7 Ouvrir le projet

Après le lancement, le rapport s'ouvre directement dans l'application **Power BI Desktop** (il ne s'agit pas d'une application web accessible via `http://localhost`).

### Point de vigilance

- Vérifier que la source de données est bien accessible avant d'actualiser
- Vérifier la compatibilité de la version de Power BI Desktop
- Ne jamais publier :
  - mots de passe
  - clés API
  - tokens
  - identifiants

---

# 7. Captures d'écran

## Capture 1

### Titre

```
Vue Globale du Marché Immobilier
```

### Image

```md
![Vue Globale du Marché](chemin-vers-image.png)
```

### Explication

Cette capture montre la page 1 du rapport, avec le nombre total d'annonces, le prix moyen en MAD, le prix moyen au m² et la répartition des annonces par ville.

---

## Capture 2

### Titre

```
Analyse des Prix
```

### Image

```md
![Analyse des Prix](chemin-vers-image.png)
```

### Explication

Cette capture montre la page 2 du rapport, avec la distribution des prix par tranches et la corrélation entre la surface et le prix des annonces.

---

# 8. Contribution personnelle

Ma contribution principale a porté sur la collecte et la préparation des données d'annonces immobilières issues du scraping du site Avito.

J'ai également travaillé sur la modélisation des données et la création des mesures DAX (comme `Total_Annonces`) dans Power BI.

J'ai été responsable de la conception des 4 pages du rapport (vue globale, analyse des prix, analyse géographique, analyse des tendances) ainsi que de la mise en place des filtres interactifs.

---

# 9. Difficultés rencontrées

## Difficulté 1

### Problème rencontré

Les données issues du scraping d'annonces immobilières contenaient des formats hétérogènes (prix, surface, dates) rendant leur exploitation directe difficile dans Power BI.

### Recherches / Tests

J'ai testé plusieurs approches de nettoyage et de transformation des colonnes (`prix_mad`, `surface_m2`, `scraped_at`) afin de m'assurer que les types de données étaient corrects avant de construire les visuels.

### Solution

J'ai normalisé les colonnes numériques et de date directement dans le modèle de données de Power BI, ce qui a permis de créer des mesures fiables comme le prix moyen au m².

### Ce que j'ai appris

Cette difficulté m'a permis d'apprendre l'importance du nettoyage et de la préparation des données avant toute étape de visualisation.

### Texte final

J'ai rencontré le problème suivant : des données brutes hétérogènes issues du scraping rendaient les calculs de KPI incohérents.

Pour comprendre l'origine du problème, j'ai vérifié le type de chaque colonne et comparé les valeurs attendues aux valeurs affichées dans les visuels.

J'ai résolu le problème en nettoyant et en typant correctement les colonnes dans le modèle de données Power BI.

Cette difficulté m'a permis d'apprendre à structurer rigoureusement un modèle de données avant de construire des rapports.

---

## Difficulté 2

### Problème rencontré

Il était difficile de choisir les visuels les plus adaptés pour représenter à la fois la répartition géographique et l'évolution temporelle des annonces.

### Recherches / Tests

J'ai comparé plusieurs types de visuels Power BI (carte, graphique combiné, nuage de points) pour identifier ceux qui rendaient les tendances les plus lisibles.

### Solution

J'ai réparti l'analyse sur 4 pages distinctes, chacune dédiée à un angle précis (vue globale, prix, géographie, tendances), afin de garder chaque page lisible et centrée sur un objectif clair.

### Ce que j'ai appris

Cette difficulté m'a permis d'apprendre à structurer un rapport BI de façon claire en séparant les différents axes d'analyse plutôt que de tout regrouper sur une seule page.

---

# 10. Améliorations possibles

Dans une prochaine version, je pourrais :

- automatiser l'actualisation des données via un pipeline de scraping planifié ;
- ajouter des indicateurs supplémentaires (type de bien, nombre de pièces) ;
- publier le rapport sur Power BI Service pour un accès en ligne partagé ;
- ajouter des prévisions de prix basées sur l'historique des annonces.

### Conclusion

Ces améliorations permettraient de rendre le suivi du marché immobilier plus automatisé, plus riche en indicateurs et plus facilement accessible aux utilisateurs finaux.

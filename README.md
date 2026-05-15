# Breif — Tableau de Bord Power BI du Marché Immobilier

## Description

**Breif** est un rapport Power BI interactif dédié à l'analyse du marché immobilier. Il permet d'explorer les annonces immobilières sous différents angles : vue globale, analyse des prix, répartition géographique et tendances temporelles.

- **Créé depuis** : Power BI Cloud
- **Version de la release** : 2026.04
- **Version Power BI Desktop** : 2.153.777.0
- **Thème visuel** : Bloom

---

## Structure du Rapport

Le rapport est composé de **4 pages** :

### Page 1 — Vue Globale du Marché
Vue d'ensemble synthétique du marché immobilier.

| Visuel | Description |
|--------|-------------|
| 📊 Histogramme (columnChart) | Nombre d'annonces par ville |
| 📈 Graphique en courbes (lineChart) | Évolution du volume des annonces dans le temps (`scraped_at`) |
| 🃏 Carte KPI | Nombre d'annonces total |
| 🃏 Carte KPI | Prix moyen en MAD |
| 🃏 Carte KPI | Prix moyen au m² |
| 🔲 Tableau (tableEx) | Détail par ville |
| 🎚️ Filtre (slicer) | Prix en MAD (`prix_mad`) |
| 🎚️ Filtre (slicer) | Surface en m² (`surface_m2`) |

---

### Page 2 — Analyse des Prix
Analyse approfondie de la distribution et des corrélations de prix.

| Visuel | Description |
|--------|-------------|
| 📊 Graphique combiné (lineStackedColumnComboChart) | Distribution des prix (par tranches de `prix_mad`) |
| 🔵 Nuage de points (scatterChart) | Corrélation entre la surface (`surface_m2`) et le prix (`prix_mad`) |
| 🃏 Carte KPI | Nombre d'annonces |
| 🃏 Carte KPI | Prix maximum |
| 🃏 Carte KPI | Prix par m² |
| 🔲 Tableau (tableEx) | Détail par ville |
| 🎚️ Filtre | Surface (`surface_m2`) |
| 🎚️ Filtre | Prix (`prix_mad`) |

---

### Page 3 — Analyse Géographique
Visualisation spatiale et répartition des annonces par localisation.

| Visuel | Description |
|--------|-------------|
| 🗺️ Carte (map) | Carte géographique du volume d'annonces par ville |
| 🥧 Graphique circulaire (pieChart) | Répartition des annonces par ville |
| 🃏 Carte KPI | Nombre de villes distinctes |
| 🃏 Carte KPI | Prix moyen au m² |
| 🃏 Carte KPI | Nombre d'annonces |
| 🔲 Tableau (tableEx) | Détail par ville |
| 🎚️ Filtre | Surface (`surface_m2`) |
| 🎚️ Filtre | Prix (`prix_mad`) |

---

### Page 4 — Analyse des Tendances
Évolution temporelle et comportement hebdomadaire du marché.

| Visuel | Description |
|--------|-------------|
| 📊 Graphique combiné | Activité par jour de la semaine (`jour_semaine`) — volume vs prix |
| 📊 Graphique combiné | Évolution du volume d'annonces vs prix moyen dans le temps (`scraped_at`) |
| 🃏 Carte KPI | Nombre d'annonces |
| 🃏 Carte KPI | Prix de vente moyen |
| 🃏 Carte KPI | Prix moyen au m² |
| 🔲 Tableau (tableEx) | Détail par ville |
| 🎚️ Filtre | Surface (`surface_m2`) |
| 🎚️ Filtre | Prix (`prix_mad`) |

---

## Champs et Mesures

### Colonnes identifiées dans le modèle de données

| Champ | Type | Description |
|-------|------|-------------|
| `id` | Identifiant | Identifiant unique de l'annonce |
| `ville` | Texte | Ville de l'annonce |
| `prix_mad` | Numérique | Prix de vente en Dirhams marocains (MAD) |
| `prix_par_m2` | Numérique | Prix au mètre carré |
| `surface_m2` | Numérique | Surface du bien en m² |
| `scraped_at` | Date/Heure | Date de collecte de l'annonce |
| `jour_semaine` | Texte | Jour de la semaine de l'annonce |

### Mesures calculées

| Mesure | Description |
|--------|-------------|
| `Total_Annonces` | Nombre total d'annonces (agrégation de `id`) |

---

## Filtres Interactifs

Tous les filtres sont disponibles sur chaque page et permettent de croiser les données :

- **Prix (MAD)** — Plage de prix pour filtrer les annonces
- **Surface (m²)** — Plage de surface pour affiner la sélection

---

## Prérequis Techniques

- **Power BI Desktop** version 2.153.777.0 ou supérieure
- **Power BI Service** (Cloud) — le fichier a été créé depuis le service cloud
- Connexion aux données source nécessaire pour le rafraîchissement

---

## Utilisation

1. Ouvrir le fichier `breif_de_power_bi.pbix` dans Power BI Desktop.
2. Actualiser la source de données si nécessaire (les données sont issues d'un scraping web d'annonces immobilières).
3. Utiliser les slicers **Prix** et **Surface** pour affiner l'analyse.
4. Naviguer entre les 4 pages pour explorer les différentes dimensions du marché.

---

## Remarques

- Les données semblent provenir d'un scraping d'annonces immobilières marocaines (champs en français, prix en MAD, villes marocaines).
- La colonne `scraped_at` indique une collecte automatisée de données.
- Le champ `jour_semaine` permet une analyse de l'activité des annonces par jour de la semaine.

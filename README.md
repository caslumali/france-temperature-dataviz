# Temperature Variability in France (2004–2023)

> Climate data visualization project analysing 20 years of temperature trends across France using TerraClimate rasters, R, and animated visualizations.
>
> Developed as part of the SIGMA Master's program (UE 902-2 Data Visualization), Université Toulouse 2 Jean Jaurès / Agro Toulouse.

**Visualizations produced:**
- Animated map of mean annual temperatures (GIF)
- Ridgeline plot of monthly temperature distributions
- Climate anomaly maps (departure from 20-year mean)
- Seasonal trend analysis with linear regressions
- Regional temperature facet plots with slope annotations
- Max vs. Min temperature scatter plots comparing two decades

**Tech stack:** R · ggplot2 · terra · ggridges · magick · parallel processing

---
*The detailed documentation below is in French, as originally written for the course.*
---

# **Variabilité des Températures en France (2004-2023)**

Ce projet est une analyse complète des **températures climatiques en France** sur les 20 dernières années, réalisée dans le cadre de l'UE902_2 *Visualisation de Données* du **Master SIGMA** (Université Toulouse 2 Jean Jaurès / ENSAT-INP).

## **Résumé du Projet**

- **Sources de Données** :
  - [TerraClimate](https://developers.google.com/earth-engine/datasets/catalog/IDAHO_EPSCOR_TERRACLIMATE) : Données climatiques mensuelles (2004-2023).
  - [ADMIN EXPRESS](https://geoservices.ign.fr/adminexpress) : Shapefile administratif de la France.

- **Objectifs** :
  1. **Explorer** les tendances climatiques en France à travers des visualisations interactives.
  2. **Analyser** les écarts saisonniers, spatiaux et temporels.
  3. **Identifier** les impacts régionaux du réchauffement climatique.

---

## **Visualisations**

1. **Carte Animée des Températures Moyennes** :
   - Évolution annuelle des températures moyennes en France.
   - Révélation des variations régionales et topographiques.

2. **Ridgeline Plot** :
   - Distribution des températures mensuelles sur 20 ans.
   - Visualisation des transitions saisonnières et de la variabilité intermensuelle.

3. **Carte des Anomalies Climatiques** :
   - Comparaison des températures annuelles à une moyenne de référence (2004-2023).
   - Identification des zones affectées par des anomalies positives ou négatives.

4. **Analyse des Tendances Saisonnières** :
   - Évolution des températures moyennes pour chaque saison (hiver, printemps, été, automne).
   - Régressions linéaires illustrant les tendances sur 20 ans.

5. **Scatter Plot des Températures Maximales vs Minimales** :
   - Relation entre les températures maximales et minimales moyennes par région.
   - Comparaison des deux décennies (2004-2013 vs 2014-2023).

6. **Évolution des Températures Régionales (Facettes)** :
   - Tendances des températures moyennes par région avec des annotations des pentes des régressions linéaires.

---

## **Structure du Projet**

```
📂 UE902_2_DataViz
├── 📂 data_brut/            # Données brutes (raster et shapefiles)
│   ├── admin/               # Shapefile des régions administratives
│   ├── TerraClimate_Max/    # Données raster des températures maximales
│   ├── TerraClimate_Mean/   # Données raster des températures moyennes
│   └── TerraClimate_Min/    # Données raster des températures minimales
├── 📂 data_final/           # Données traitées (rasters et shapefiles consolidés)
│   ├── france_dissolved.*   # Shapefile consolidé de la France
│   ├── TerraClimate_*.tif   # Rasters synthétisés (moyennes, anomalies)
├── 📂 scripts/              # Scripts d’analyse et de visualisation
│   ├── UE902_2_LucasLima.qmd   # Rapport principal (Quarto)
│   ├── temp_anomalies/      # Graphiques des anomalies de température
│   ├── temp_images/         # Images intermédiaires des températures
│   └── results/             # Résultats finaux (graphiques et GIFs)
├── 📂 docs/                 # Documents finaux
│   └── UE902_2_LucasLima.html   # Rapport HTML interactif
├── 📄 styles.css            # Feuille de style Quarto
├── 📄 0_projet.Rproj        # Projet RStudio
└── 📄 README.md             # Ce fichier
```

---

## **Instructions d'Utilisation**

### 1. **Installation des Packages**
Cloner ce dépôt et installer les dépendances suivantes dans R :

```r
install.packages(c("terra", "ggplot2", "dplyr", "tidyr", "ggridges", 
                   "future", "parallel", "magick", "stringr", "gtools"))
```

### 2. **Exécution du Script**
- Lancer le script principal `UE902_2_LucasLima.qmd` dans **RStudio**.
- La page HTML interactive sera générée automatiquement.

### 3. **Visualisation**
Les graphiques et animations seront sauvegardés dans le dossier `scripts/results/`.

---

## **Détails Techniques**

1. **Prétraitement des Données** :
   - Découpage des rasters climatiques au contour de la France.
   - Calcul des moyennes annuelles et des anomalies.

2. **Méthodes de Visualisation** :
   - Utilisation des bibliothèques `ggplot2` et `ggridges`.
   - Génération d'animations GIF avec `magick`.

3. **Optimisation** :
   - Traitement parallèle pour accélérer les calculs (packages `future` et `parallel`).
   - Gestion efficace de la mémoire grâce au garbage collector.

---

## **Auteurs**

- **Lucas Lima**  
  Étudiant en M2 SIGMA, Université Toulouse 2 Jean Jaurès / ENSAT-INP.

---

# Sources de données / Data sources

Analyse géospatiale SSR / Haïti 2024

Les fichiers bruts ne sont pas inclus dans ce dépôt. Ils se téléchargent directement depuis le Humanitarian Data Exchange (HDX) via les liens ci-dessous.

Raw data files are not included in this repository. Download them from the Humanitarian Data Exchange (HDX) using the links below.

---

## Français

### Données utilisées

| Source | Dataset | Lien HDX | Fichiers | Usage |
|--------|---------|----------|----------|-------|
| OCHA COD-AB | Haiti Administrative Boundaries | https://data.humdata.org/dataset/cod-ab-hti | `hti_admin_boundaries_adm2.shp`, `hti_admin_boundaries_adm1.shp` | Limites communales pour l'analyse ; limites départementales pour l'inset |
| UNFPA | Haiti Population Statistics 2024 | https://data.humdata.org/dataset/cod-ps-hti | `hti_admpop_adm2_2024.csv` | Population par sexe et tranche d'âge à l'échelle communale |
| HOT OSM | Haiti Health Facilities | https://data.humdata.org/dataset/hotosm_hti_health_facilities | `health_facilities_points.shp` | Points d'infrastructure pour le comptage par polygone |

### Limites administratives

| Champ | Valeur |
|-------|--------|
| Source | OCHA COD-AB |
| Dataset | Haiti Administrative Boundaries |
| Lien HDX | https://data.humdata.org/dataset/cod-ab-hti |
| Fichier principal | `hti_admin_boundaries_adm2.shp` |
| Fichier secondaire | `hti_admin_boundaries_adm1.shp` |
| Niveaux utilisés | Admin 2, communes ; Admin 1, départements |
| Champ de jointure | `ADM2_PCODE` |

La couche Admin 2 est la couche polygone principale. Les données population y ont été jointes sur `ADM2_PCODE`. La couche Admin 1 couvre l'inset départemental dans la mise en page finale.

### Données population

| Champ | Valeur |
|-------|--------|
| Source | UNFPA |
| Dataset | Haiti Population Statistics 2024 |
| Lien HDX | https://data.humdata.org/dataset/cod-ps-hti |
| Fichier utilisé | `hti_admpop_adm2_2024.csv` |
| Niveau | Admin 2, communes |
| Champ de jointure | `ADM2_PCODE` |

Le tableau fournit des estimations de population 2024 désagrégées par sexe et tranche d'âge. La population féminine 15-49 ans a été calculée en additionnant les sept tranches quinquennales féminines du fichier source. Cette variable agrégée est le proxy principal pour la demande potentielle en services SSR.

### Infrastructures de santé

| Champ | Valeur |
|-------|--------|
| Source | HOT OSM |
| Dataset | Haiti Health Facilities |
| Lien HDX | https://data.humdata.org/dataset/hotosm_hti_health_facilities |
| Fichier utilisé | `health_facilities_points.shp` |
| Géométrie | Points |
| Snapshot | Mai 2026 |

Les points d'infrastructure ont été comptés par commune avec l'outil QGIS **Count Points in Polygon**. Ce comptage a produit le ratio de couverture à l'échelle communale.

### Pourquoi les données brutes ne sont pas dans ce dépôt

Les fichiers source sont maintenus sur HDX par leurs fournisseurs d'origine. Les télécharger directement garantit d'obtenir la version à jour.

---

## English

### Datasets used

| Source | Dataset | HDX link | Files used | Use in analysis |
|--------|---------|----------|------------|-----------------|
| OCHA COD-AB | Haiti Administrative Boundaries | https://data.humdata.org/dataset/cod-ab-hti | `hti_admin_boundaries_adm2.shp`, `hti_admin_boundaries_adm1.shp` | Commune boundaries for analysis; department boundaries for map inset |
| UNFPA | Haiti Population Statistics 2024 | https://data.humdata.org/dataset/cod-ps-hti | `hti_admpop_adm2_2024.csv` | Population by sex and age group at commune level |
| HOT OSM | Haiti Health Facilities | https://data.humdata.org/dataset/hotosm_hti_health_facilities | `health_facilities_points.shp` | Health facility points for point-in-polygon counts |

### Administrative boundaries

| Item | Description |
|------|-------------|
| Source | OCHA COD-AB |
| Dataset | Haiti Administrative Boundaries |
| HDX link | https://data.humdata.org/dataset/cod-ab-hti |
| Main file used | `hti_admin_boundaries_adm2.shp` |
| Additional file used | `hti_admin_boundaries_adm1.shp` |
| Levels used | Admin 2 communes; Admin 1 departments |
| Key join field | `ADM2_PCODE` |

The Admin 2 layer was the main polygon layer for the analysis. Population data was joined to it on `ADM2_PCODE`. The Admin 1 layer was used for the department inset in the final map layout.

### Population data

| Item | Description |
|------|-------------|
| Source | UNFPA |
| Dataset | Haiti Population Statistics 2024 |
| HDX link | https://data.humdata.org/dataset/cod-ps-hti |
| File used | `hti_admpop_adm2_2024.csv` |
| Level | Admin 2 communes |
| Join field | `ADM2_PCODE` |

The table provides sex- and age-disaggregated population estimates for 2024. The female population aged 15-49 was calculated by summing seven five-year age bands from the source file. This derived variable is the main proxy for potential demand for SRH services.

### Health facilities

| Item | Description |
|------|-------------|
| Source | HOT OSM |
| Dataset | Haiti Health Facilities |
| HDX link | https://data.humdata.org/dataset/hotosm_hti_health_facilities |
| File used | `health_facilities_points.shp` |
| Geometry | Points |
| Snapshot | May 2026 |

Health facility points were counted within each commune using QGIS **Count Points in Polygon**. The count produced a commune-level infrastructure coverage ratio.

### Raw data policy

Source files are maintained on HDX by their original providers. Downloading directly ensures you get the current version.

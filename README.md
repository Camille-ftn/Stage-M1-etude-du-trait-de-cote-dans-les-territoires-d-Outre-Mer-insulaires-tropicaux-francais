# Apports de l'imagerie spatiale pour l'étude du trait de côte à l'Ermitage (La Réunion)

## Contexte
Étude du potentiel de l'imagerie spatiale (Sentinel-2 via l'outil open-source **Coastsat**) pour analyser l'évolution du trait de côte sur un récif frangeant à l'Ermitage (La Réunion), dans le cadre du SNO DYNALIT. Stage M1 SPE-GGL, encadré par K. Martins (2023-2024). [file:58]

**Objectif** : Extraire la position de la ligne d'eau et la corriger (marée, surcôte atmosphérique, setup d'ondes) pour obtenir le trait de côte.

## Données utilisées
- Images Sentinel-2 (2015-présent, 10m résolution).
- Profils topographiques GPS-RTK (2012-2020, SNO DYNALIT).
- Marégraphe Pointe des Galets (RONIM/SHOM).
- Setup d'ondes : mesures in situ + modèle MARC (Ifremer).

## Méthodologie
1. **Prétraitement** : CoastSat (Google Earth Engine) – masquage nuages, classification U-Net (sable/eau/écume), extraction ligne d'eau (MNDWI + seuil Otsu).
2. **Corrections** : Marée (FES2014), setup (relation linéaire Hs-setup : Y=0.19X+0.36).
3. **Analyse** : Transects (VVF, MNS, Copacabana) – RMSE, tendances érosion/accrétion.

## Résultats clés
- RMSE ~2-4m après correction (vs. in situ).
- Variations trait de côte non expliquées seulement par hydrodynamique → erreurs détection (nuages, co-registration).
- Saisonnalité : recul hiver (houle australe), accretion été.

## Outils & Code
- Python : Pandas, NumPy , Matplotlib.
- QGIS (spatial), CoastSat.

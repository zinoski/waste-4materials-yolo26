# Dataset Waste 4 matériaux — YOLO26

Ce dépôt contient le jeu de données `waste_4materials_roboflow_v2` préparé pour détecter : **carton, plastique, métal et verre**.

## Télécharger et préparer le jeu

L’archive complète `dataset_v2.zip` est suivie avec Git LFS. Après clonage, récupère-la avec `git lfs pull`, puis décompresse-la. Le fichier `data.yaml` se trouve à la racine de l’archive.

```powershell
git lfs pull
Expand-Archive .\dataset_v2.zip -DestinationPath .\dataset
```

Le YAML contient un chemin local ; si tu déplaces le dossier, remplace `path` par son nouvel emplacement.

## Découpage et contrôle

- Entraînement : 14 727 images (70 %)
- Validation : 3 156 images (15 %)
- Test : 3 156 images (15 %)
- Les groupes d’images perceptuellement proches restent dans un seul découpage ; 0 paire candidate ne traverse les jeux après répartition.
- Les noms ne donnent pas les sessions ou vidéos d’origine : le contrôle par groupes vidéo n’est donc pas possible.

Le détail des classes, le tableau image → découpage et les paires similaires sont dans `AUDIT_FR.md`, `image_split.csv` et `near_duplicate_edges.csv` à l’intérieur de l’archive.

## Licence et droits

Aucun fichier de licence ni provenance commerciale n’a été trouvé dans le dossier local source. Le dépôt est privé en attendant la vérification des droits. La copie sur GitHub ne vaut pas autorisation de redistribution ou d’usage commercial.

## Intégrité

Le SHA-256 de l’archive est dans `dataset_v2.zip.sha256`.

## Modèle iPhone

L’export Core ML YOLO26s à huit classes est dans [mobile/](mobile/README_FR.md). Ce modèle provient du dataset SortWaste d’entraînement, pas du dataset v2 quatre matières décrit plus haut.


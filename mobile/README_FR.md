# Modèle YOLO pour iPhone

## Fichier

`waste_yolo26s_sortwaste_8classes_coreml_w8a16_640.mlpackage.zip` est l’export Core ML du meilleur poids du run `sortwaste_yolo26s_v1_retry`.

- Tâche : détection d’objets.
- Taille d’entrée : 640 × 640 pixels, batch 1.
- Compression : poids palettisés sur 8 bits, calcul en précision mixte Core ML.
- Classes, dans l’ordre : PET, HDPE, plastique_souple, emballage_carton_liquide, metal, carton, plastique_rigide, PET_huile.
- Poids d’origine : `C:\dev\yolo\runs\detect\sortwaste_yolo26s_v1_retry\weights\best.pt`.
- Le dataset v2 de quatre matières situé ailleurs dans ce dépôt n’est pas le dataset qui a servi à entraîner ce modèle.

## Téléchargement

Télécharge l’archive depuis GitHub, puis décompresse-la pour obtenir le dossier `.mlpackage`. Le hash SHA-256 est dans le fichier `.sha256` associé.

## Limite avec l’application Ultralytics iPhone

Cette archive est un fichier Core ML prêt à intégrer dans une application iOS. Dans l’application Ultralytics publiée, l’import des modèles personnalisés passe par Ultralytics Platform et un QR code; le simple téléchargement depuis GitHub ne garantit pas que le modèle apparaisse dans le sélecteur de l’application. Une fois importé, l’application peut utiliser le modèle hors ligne. Voir les [instructions officielles de l’application](https://github.com/ultralytics/yolo-ios-app/releases).

L’export a été généré sur Linux avec Ultralytics 8.4.197, PyTorch 2.7.1 CPU et Core ML Tools 9.0; conversion `imgsz=640`, `batch=1`, `quantize=8`, `nms=False`. Le modèle a été converti et ses métadonnées vérifiées, mais il n’a pas été exécuté sur un iPhone : aucune vitesse ni précision iOS n’est revendiquée.

## Licence

Le code et les poids Ultralytics sont publiés par défaut sous AGPL-3.0. Pour un produit commercial fermé, Ultralytics indique qu’une licence Enterprise est nécessaire; l’autre option est de publier le projet concerné sous AGPL-3.0. Vérifie aussi les droits de redistribution du dataset avant toute vente. Voir la [licence Ultralytics](https://www.ultralytics.com/license).

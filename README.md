🔧 Conversion Panoptic → Detection (COCO) — Version modifiée
Ce dépôt contient une version modifiée de la bibliothèque officielle COCO Panoptic et de ses scripts associés pour convertir des annotations du format COCO panoptique vers le format COCO détection.
Cette modification vise principalement à :
adapter le comportement du script à des besoins spécifiques,
faciliter certaines expérimentations,
sans prétendre remplacer la version officielle.


📌 Origine du code
Le script principal de ce dépôt est basé sur la librairie officielle COCO Panoptic développée par l’équipe COCO :
https://cocodataset.org/


👉 Il s’agit d’une modification non officielle de cette bibliothèque :
le cœur du fonctionnement reste identique,
mais certaines parties ont pu être adaptées, commentées ou simplifiées pour des usages expérimentaux.
Pour la version originale et maintenue du projet, référez-vous au dépôt officiel COCO.


🎯 Objectif du script
Le script permet de :
prendre un jeu d’annotations COCO Panoptic (JSON + images de segmentation),
transformer chaque segment panoptique en une annotation individuelle,
produire un fichier COCO Detection compatible avec des frameworks comme :
Mask R-CNN,
Detectron2,
ou tout autre modèle basé sur COCO détection.
Une option --things_only permet de conserver uniquement les objets (“things”) et d’ignorer les régions de fond (“stuff”).


📓 Informations d’exécution
Des détails supplémentaires sur :
l’installation,
l’organisation des fichiers,
et l’exécution pas à pas
sont fournis dans le notebook présent dans ce dépôt.
Il est recommandé de le consulter avant de lancer le script.


🚀 Lancer la conversion (exemple)
Exécution recommandée depuis la racine du dépôt :
!python3 panoptic2detection_coco_format.py \
  --input_json_file './annotations/panoptic_annotations.json' \
  --output_json_file 'panoptic_annotations.json'
Ce qui se passe :
Le fichier panoptic_annotations.json (format panoptique 2017) est lu,
Les segmentations correspondantes sont analysées,
Un nouveau fichier JSON au format COCO détection est généré.

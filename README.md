# 🔧 Conversion Panoptic → Detection (COCO) — Version modifiée

Ce dépôt contient une version modifiée de la bibliothèque officielle **COCO Panoptic** et de ses scripts associés. Son but est de convertir des annotations du format **COCO panoptique** vers le format **COCO détection**.

Cette modification vise principalement à :
* Adapter le comportement du script à des besoins spécifiques.
* Faciliter certaines expérimentations.
* *Elle ne prétend pas remplacer la version officielle.*

---

## 📌 Origine du code

Le script principal de ce dépôt est basé sur la librairie officielle développée par l’équipe COCO : [cocodataset.org](https://cocodataset.org/).

> **⚠️ Avertissement :**
> Il s’agit d’une **modification non officielle** de cette bibliothèque. Bien que le cœur du fonctionnement reste identique, certaines parties ont été adaptées pour des usages expérimentaux.
>
> Pour la version originale et maintenue du projet, veuillez vous référer au **dépôt officiel COCO**.

---

## 🎯 Objectif du script

Ce script permet d'automatiser le flux de travail suivant :

1.  **Entrée :** Prend un jeu d’annotations COCO Panoptic (Fichier JSON + images de segmentation).
2.  **Traitement :** Transforme chaque segment panoptique en une annotation individuelle.
3.  **Sortie :** Produit un fichier JSON au format **COCO Detection**.

Le fichier généré est compatible avec des frameworks tels que :
* Mask R-CNN
* Detectron2
* Tout autre modèle basé sur le format standard COCO détection.

**Option disponible :**
* `--things_only` : Permet de conserver uniquement les objets dénombrables ("things") et d’ignorer les régions de fond ("stuff").

---

## 📓 Informations d’exécution

Des détails techniques supplémentaires concernant l’installation, l’organisation des fichiers et l’exécution pas à pas sont fournis dans le **notebook présent dans ce dépôt**.

> **Note :** Il est fortement recommandé de consulter ce notebook avant de comprendre le script.

---

## 🚀 Lancer la conversion

Voici un exemple d'exécution recommandée depuis la racine du dépôt :

```bash
python3 panoptic2detection_coco_format.py \
  --input_json_file './annotations/panoptic_annotations.json' \
  --output_json_file 'panoptic_annotations.json'

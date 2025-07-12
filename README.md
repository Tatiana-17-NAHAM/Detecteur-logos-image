![Statut](https://img.shields.io/badge/🔥_Projet-Actif-EA4C4C.svg)
# Détecteur-logos-image
Projet d'exploration en vision par ordinateur : traitement d'image, détection locale et visualisation des zones d’intérêt.

## 🧭 Sommaire
- [🎯 Objectifs du projet](#objectifs-du-projet)
- [📂 Contenu](#contenu)
- [🛠️ Technologies](#technologies)
- [📸 Visualisations](#visualisations)
- [📘 Notebook](#notebook)
- [📍 Résultats](#résultats)
- [👩‍💻 Réalisé par](#réalisé-par)

## 🎯 Objectifs du projet

Développer un outil simple en Python pour :

- Analyser les composantes de couleur d'une image
- Appliquer des filtres Sobel pour détecter les contours
- Zoomer et extraire des zones spécifiques
- Sauvegarder les zones extraites dans des fichiers `.png`
- Calculer des statistiques sur les couleurs dominantes

## 📂 Contenu
Ce dépôt comprend :

- L’image principale (logo Adobe) utilisée pour toutes les analyses visuelles :

![Image originale - img3](./img3.png)

- Le notebook Jupyter analyse_img3.ipynb contenant le code étape par étape

- Le fichier README.md avec explications du projet et des résultats

## 🛠️ Technologies
Le projet repose sur les librairies suivantes :

- Python 3.x

- OpenCV (cv2)

- scikit-image (skimage)

- scipy

- matplotlib

## 📸 Visualisations
Dans cette section, vous découvrirez les différentes étapes du traitement appliqué à l’image principale ( logo Adobe) Chaque visualisation est accompagnée d’une courte explication pour interpréter les résultats obtenus lors de l’analyse :

## 🎨 Séparation des composantes de couleur ( RGB)
L’image est décomposée en ses trois canaux principaux : rouge, vert et bleu. Cette étape permet d’analyser visuellement l’intensité de chaque couleur dans le logo Adobe.
![Séparation RGB - logo Adobe](./image%20RGB.png)


-  Dérivées visuelles (bordures)
-   Zoom sur des zones spécifiques
-   Extraction automatique par couleur dominante

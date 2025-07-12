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

📍 On observe que :

- Le canal bleu est extrêmement dominant — il rend le logo très lumineux dans cette composante.

- Le rouge révèle les détails les plus nets dans le logo original.

- Le vert, quant à lui, est plus diffus dans cette image.

## 📐 Dérivées visuelles (bordures)
Cette phase utilise les filtres de Sobel sur l'image en monochrome afin d'identifier les contours.  Ces dérivées servent à détecter les variations de luminosité, pratiques pour identifier les contours d'un logo ou ses formes géométriques :

![Dérivées visuelles - Sobel](./image%20dvs.png)

Sobel Horizontal : met en évidence les lignes verticales (contours gauche-droite)

Sobel Vertical : révèle les lignes horizontales (contours haut-bas)

📍 Dans le cas du logo Adobe, ces dérivées exposent les traits du “A” central et les limites du cadre avec précision.

## 🔍  Zoom sur des zones spécifiques
Cette phase consiste à isoler des éléments spécifiques de l'image (tels qu'un logo ou un détail graphique) et à les agrandir pour faciliter leur analyse.  Chaque zone est extraite en fonction de ses coordonnées dans l'image, puis interpolée afin d'obtenir une image claire :

![Zone zoomée - image Adobe](./image%20zoom.png)
📍 Dans le cas du logo Adobe, les zones zoomées révèlent les formes et contrastes internes avec plus de précision ce qui facilite la détection de logo ou l’analyse de texture locale.

## 🎯 Extraction automatique par couleur dominante
Cette étape utilise des seuils sur les composantes de couleur (rouge, vert, bleu) pour créer un masque visuel. Elle permet d’isoler automatiquement les zones qui présentent une forte intensité dans une couleur précise — ici, le rouge.

📍 Critères utilisés :

Rouge > 150

Vert < 100

Bleu < 100

![Masque rouge - logo Adobe](././image%20zrd.png)

📌 Le masque ainsi généré met en valeur les régions rouges intenses du logo, ce qui facilite leur repérage sans intervention manuelle.
Cette méthode est utile dans des projets de reconnaissance visuelle, d’analyse thermique ou de segmentation d’image basée sur les couleurs dominantes.

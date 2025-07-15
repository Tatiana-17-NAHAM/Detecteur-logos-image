![Statut](https://img.shields.io/badge/🔥_Projet-Actif-EA4C4C.svg)
![Auteur](https://img.shields.io/badge/Auteur-Tatiana%20SANGUEAL%20NAHAM-blue)

# Détecteur-logos-image
Ce dépôt offre une exploration pratique du traitement visuel d'images en Python, à travers l'examen graduel d'un logo.  Les procédures comprennent : dissociation des éléments RGB, filtrage des contours, extraction spécifique, masquage basé sur la couleur ( colorimétrique) et synthèse statistique.

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

## 📘 Notebook
L’ensemble du traitement visuel a été réalisé dans un notebook Jupyter
📘 Voir le notebook Jupyter : [notebook détecteur](./notebook_detecteur.ipynb)

## 📍 Résultats

## 📊 Statistiques sur les zones extraites

En complément aux visualisations, une étude quantitative a été effectuée sur une zone précise de l'image (extrait [50:100, 50:100]).  Cela permet d'évaluer les valeurs numériques des canaux de couleur (RGB) dans une zone ciblée et d'en déduire des informations pertinentes pour l'identification ou le filtrage.

## 📊 Statistiques sur les zones extraites

Pour compléter les visualisations, une analyse quantitative a été réalisée sur une zone spécifique de l’image (coordonnées `[50:100, 50:100]`).  
Cela permet de mesurer les valeurs numériques des canaux de couleur (RGB) dans une portion localisée.

| Couleur | Min | Max | Moyenne |
|--------|-----|-----|---------|
| 🔵 Bleu | 223 | 255 | **253.36** |
| 🟢 Vert | 0   | 255 | **73.90**  |
| 🔴 Rouge| 0   | 255 | **73.74**  |

👉 Ces statistiques aident à comprendre le poids de chaque couleur dans la zone, à définir des seuils, et à valider les masques colorimétriques appliqués dans les étapes précédentes.


 ## 🔮 Perspectives et évolutions possibles
 Ce projet établit les fondations d'un système de détection visuelle performant, en s'appuyant sur des phases organisées et reproductibles.  Il peut aisément se développer vers des applications plus avancées, comme :

-  🤖 Identification automatique de logos  Incorporation de modèles déjà formés (par exemple : CNN, OpenCV, scikit-learn) pour détecter des logos dans diverses images.
-  🧠 Amélioration par l'intelligence artificielle  Mise en œuvre de réseaux neuronaux pour perfectionner la segmentation, catégoriser les zones identifiées ou repérer des motifs visuels.
-   🖥️ Interface utilisateur interactive  Mise en œuvre avec des outils tels que Streamlit ou Tkinter pour faciliter l'accès au traitement via une interface utilisateur graphique.
- 🗂️ Traitement par lots multi-images  Incorporation de scripts pour gérer automatiquement plusieurs images et identifier les logos ou motifs récurrents.

-  📌 Élargissement vers d'autres formes d'analyse visuelle.  Ajustement du flux de travail pour la thermographie, l'analyse industrielle et le stockage numérique.

## 📍 Conclusion
Ce projet démontre les phases clés du traitement d'image en utilisant Python : de la discrimination des couleurs à la détection des contours, jusqu'à la récupération automatique de régions à l'aide de masques.  Le notebook Jupyter offre une plateforme où toutes les actions sont à la fois visibles et répétables, ce qui constitue une base robuste pour la création d'outils de reconnaissance visuelle destinés à l'analyse de logos, d'objets ou de zones spécifiques d'intérêt.
📌  L'approche adoptée fournit un fondement robuste pour une diversité d'applications :

- Identification automatique de logos.

 - Segmentation d'objets

-  Analyse de couleur en imagerie thermique ou industrielle.

 Le notebook Jupyter permet un traitement qui est réplicable, bien documenté et aisément extensible pour des améliorations futures telles que l'ajout d'algorithmes d'intelligence artificielle ou d'une interface utilisateur.

## 👩‍💻 Auteur
Ce projet a été réalisé par Tatiana SANGUEAL NAHAM, passionnée par l’analyse visuelle, le traitement d’image et les projets intelligents mêlant données et graphisme.

📧 Contact : nsanguealtatiana@oulook.com 🔗 LinkedIn : 🔗 ([https://www.linkedin.com/in/ton-lien-linkedin](https://www.linkedin.com/in/tatiana-sangu%C3%A9al-naham-050170178/))

# TP 3 : CNN - Convolution et Pooling
**Auteur : EL MAHDI BOUDERNA**

Ce dépôt contient l'implémentation pratique des concepts fondamentaux des réseaux de neurones convolutifs (CNN) : la **convolution** et le **pooling**. Ce travail a été réalisé "from scratch" en utilisant Python pour comprendre comment les caractéristiques d'une image sont extraites et compressées.

## 📌 Objectifs du TP
L'objectif est de transformer une image brute en une "carte de caractéristiques" (feature map) en isolant les éléments visuels importants (bords, lignes) et en réduisant la dimension des données pour faciliter la classification future.

## 🛠️ Technologies Utilisées
* **NumPy** : Pour la manipulation des matrices de pixels (l'image est stockée sous forme de tableau NumPy).
* **SciPy** : Pour l'utilisation de l'image de test intégrée "ascent".
* **Matplotlib** : Pour la visualisation des images et des résultats de filtrage.
* **OpenCV (cv2)** : Pour le support du traitement d'image.

## 🚀 Étapes de Réalisation

### 1. Prétraitement et Visualisation
Nous commençons par charger l'image "ascent" de SciPy, une image 2D en niveaux de gris riche en angles et en lignes.
* **Dimensions originales** : 512 x 512 pixels.

### 2. Application de la Convolution
La convolution consiste à scanner chaque pixel et ses voisins, puis à multiplier leurs valeurs par les poids d'un filtre (matrice 3x3).
* **Le Filtre** : Nous utilisons des filtres pour accentuer des caractéristiques spécifiques, comme les lignes verticales très marquées.
* **Calcul** : Pour chaque pixel, on calcule une nouvelle valeur basée sur ses voisins, tout en s'assurant que le résultat reste dans l'intervalle [0, 255]. Pour éviter les erreurs de dépassement (overflow), les calculs sont effectués en nombres flottants avant la conversion finale.



### 3. Max Pooling (2x2)
Après la convolution, le pooling permet de réduire la quantité globale d'informations tout en conservant les caractéristiques détectées.
* **Méthode** : Nous utilisons le "Max Pooling". On parcourt l'image par blocs de 2x2 et on ne conserve que la valeur la plus élevée de chaque groupe.
* **Résultat** : L'image finale est réduite à **256x256** (un quart de la surface d'origine), mais les caractéristiques essentielles sont améliorées et préservées.



## 📊 Résultats
Le processus permet de passer d'une image complexe à une représentation simplifiée où seuls les contours et les formes structurelles (comme les marches d'escalier) sont mis en évidence, ce qui est crucial pour l'entraînement des modèles de Deep Learning.

---
*Projet réalisé par **EL MAHDI BOUDERNA** dans le cadre du module de Deep Learning.*

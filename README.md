# TP 3 : CNN - Convolution et Pooling
**Auteur : EL MAHDI BOUDERNA**

Ce dépôt contient l'implémentation pratique des concepts fondamentaux des réseaux de neurones convolutifs (CNN) : la **convolution** et le **pooling**. [cite_start]Ce travail a été réalisé "from scratch" en utilisant Python pour comprendre comment les caractéristiques d'une image sont extraites et compressées[cite: 1, 2].

## 📌 Objectifs du TP
[cite_start]L'objectif est de transformer une image brute en une "carte de caractéristiques" (feature map) en isolant les éléments visuels importants (bords, lignes) et en réduisant la dimension des données pour faciliter la classification future[cite: 3, 6, 105].

## 🛠️ Technologies Utilisées
* [cite_start]**NumPy** : Pour la manipulation des matrices de pixels (l'image est stockée sous forme de tableau NumPy)[cite: 52].
* [cite_start]**SciPy** : Pour l'utilisation de l'image de test intégrée "ascent"[cite: 38].
* [cite_start]**Matplotlib** : Pour la visualisation des images et des résultats de filtrage[cite: 46].
* [cite_start]**OpenCV (cv2)** : Pour le support du traitement d'image[cite: 42].

## 🚀 Étapes de Réalisation

### 1. Prétraitement et Visualisation
[cite_start]Nous commençons par charger l'image "ascent" de SciPy, une image 2D en niveaux de gris riche en angles et en lignes[cite: 37, 39].
* [cite_start]**Dimensions originales** : 512 x 512 pixels[cite: 90].

### 2. Application de la Convolution
[cite_start]La convolution consiste à scanner chaque pixel et ses voisins, puis à multiplier leurs valeurs par les poids d'un filtre (matrice 3x3)[cite: 7, 8, 57].
* [cite_start]**Le Filtre** : Nous utilisons des filtres pour accentuer des caractéristiques spécifiques, comme les lignes verticales très marquées[cite: 52, 95].
* [cite_start]**Calcul** : Pour chaque pixel, on calcule une nouvelle valeur basée sur ses voisins, tout en s'assurant que le résultat reste dans l'intervalle [0, 255][cite: 62, 85, 86].



### 3. Max Pooling (2x2)
[cite_start]Après la convolution, le pooling permet de réduire la quantité globale d'informations tout en conservant les caractéristiques détectées[cite: 106].
* **Méthode** : Nous utilisons le "Max Pooling". [cite_start]On parcourt l'image par blocs de 2x2 et on ne conserve que la valeur la plus élevée[cite: 107, 108].
* [cite_start]**Résultat** : L'image finale est réduite à **256x256** (un quart de la taille d'origine), mais les caractéristiques essentielles sont améliorées et préservées[cite: 109, 158].



## 📊 Résultats
[cite_start]Le processus permet de passer d'une image complexe à une représentation simplifiée où seuls les contours et les formes structurelles (comme les marches d'escalier) sont mis en évidence, ce qui est crucial pour l'apprentissage profond[cite: 51, 135].

---
*Projet réalisé par **EL MAHDI BOUDERNA** dans le cadre du module de Deep Learning.*

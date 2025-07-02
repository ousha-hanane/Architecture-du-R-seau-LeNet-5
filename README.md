# Classification automatique des caractères Tifinagh avec LeNet-5

## 📌 Description

Ce projet implémente une architecture **LeNet-5** modifiée pour la reconnaissance automatique de caractères manuscrits de l'alphabet **Tifinagh**. Il s'appuie sur la base de données **AMHCD** et utilise **PyTorch** pour la création et l'entraînement du modèle.

## 🧠 Objectif

Développer, entraîner et évaluer un réseau de neurones convolutif (CNN) adapté à la classification de 33 classes de caractères Tifinagh à partir d’images en niveaux de gris.

## 📂 Contenu du dépôt

- `cnn_notbook_tifinagh.ipynb` : Notebook Jupyter contenant le code complet d’entraînement, d’évaluation et de visualisation.
- `TP-CNN-Lenet 5.pdf` : Rapport technique détaillant l’architecture, les étapes de prétraitement, la formulation mathématique et les résultats.
- `README.md` : Ce fichier d'explication.

## 🖼️ Données

- **Nom** : AMHCD (Amazigh Handwritten Character Database)
- **Taille** : 28 182 images (64×64 px, niveaux de gris)
- **Classes** : 33 lettres Tifinagh
- **Prétraitement** :
  - Redimensionnement à 32×32
  - Normalisation (valeurs entre 0 et 1)
  - Encodage des étiquettes (one-hot)
  - Découpage : ensemble d'entraînement, validation, test

## 🏗️ Architecture LeNet-5 (modifiée)

| Couche | Type | Paramètres principaux | Dimension de sortie |
|-------|------|------------------------|----------------------|
| Entrée | Image | 32×32×1 | 32×32×1 |
| C1 | Convolution | 6 filtres 5×5 | 28×28×6 |
| S2 | Moyenne Pooling | 2×2, stride 2 | 14×14×6 |
| C3 | Convolution | 16 filtres 5×5 | 10×10×16 |
| S4 | Moyenne Pooling | 2×2, stride 2 | 5×5×16 |
| C5 | FC (ou conv 5×5×16) | 120 neurones | 120 |
| F6 | FC | 84 neurones | 84 |
| Output | FC + Softmax | 33 neurones | 33 |

## ⚙️ Entraînement

- **Langage** : Python
- **Framework** : PyTorch
- **Optimiseur** : Adam
- **Fonction de perte** : CrossEntropyLoss
- **Époques** : 30
- **Taux de précision final (test)** : **96.14%**
- **Taux de perte final (test)** : **0.1260**

## 📊 Résultats

- **Courbes d’apprentissage** : convergence rapide, sans surapprentissage
- **Matrice de confusion** : précision élevée, quelques confusions visuelles
- **Cartes de caractéristiques** : motifs et bords correctement extraits
- **Généralisation** : bonne stabilité entre les ensembles (train/val/test)


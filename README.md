# Create the README.md file for download

Détection de défauts internes de pommes de terre

## Description
Ce projet met en œuvre un pipeline complet de deep learning pour la détection et
la classification de défauts internes sur des images de tranches de pommes de terre,
en s’appuyant sur un modèle de détection d’objets de type YOLO.

L’objectif est de fournir une solution automatisée pour des applications de
contrôle qualité, en couvrant l’ensemble du processus : préparation des données,
nettoyage des annotations, entraînement du modèle, validation et inférence.

---

## Classes de défauts
Le modèle est capable de détecter et classifier les défauts internes suivants :

- **0** : Verdissement  
- **1** : Endommagement interne  
- **2** : Morsure et Galerie  
---

## Structure du projet

train.ipynb          # Prétraitement des données et entraînement du modèle
inference.py         # Script d’inférence sur un dossier d’images
classes.txt          # Définition des classes de défauts
requirements.txt     # Dépendances Python


---

## Installation

### Création de l’environnement (optionnelle mais recommandée)
python -m venv venv  
source venv/bin/activate      # Linux / macOS  
venv\\Scripts\\activate       # Windows  

### Installation des dépendances
pip install -r requirements.txt

---

## Entraînement du modèle

L’entraînement du modèle est réalisé à l’aide du notebook `train.ipynb`.

jupyter notebook train.ipynb


### Étapes incluses :
- Chargement et vérification du dataset  
- Nettoyage automatique des annotations incorrectes  
- Amélioration colorimétrique des images (espace HSV)  
- Augmentation des données  
- Séparation entraînement / validation  / test
- Entraînement du modèle YOLO v8s  

---

## Inférence

Le script `inference.py` permet d’effectuer une inférence sur un dossier d’images.

Exemple de commande :
python inference.py --model model/my_model.pt --source data/test/images 

Résultats :
- Images annotées avec boîtes englobantes et classes prédites  
- Résultats sauvegardés dans le dossier de sortie  




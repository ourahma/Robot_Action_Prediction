# Deep Learning et NLP pour la Robotique

## Objectif du projet
L’objectif principal est de développer un modèle capable de classifier les commandes en fonction d’une situation décrite en texte. Les actions possibles sont :
- **Tourner à gauche**
- **Tourner à droite**
- **S’arrêter**

## Architecture du projet
### 1. Génération du Dataset
Étant donné qu’aucun dataset public ne correspondait exactement à notre besoin, nous avons généré un dataset contenant des descriptions textuelles de situations et les actions correspondantes. Chaque situation est construite à partir de combinaisons de :
- **Distances** : "à 10 centimètres", "à 20 centimètres", "proche du robot", etc.
- **Positions** : "devant le robot", "à gauche", "à droite", etc.
- **Obstacles détectés** : "un obstacle est détecté", "un mur est détecté", etc.

### 2. Modélisation avec un LSTM
Nous avons utilisé un modèle de Réseau de Neurones Récurrent (LSTM) pour analyser ces descriptions textuelles et prédire la commande correspondante. Le modèle est entraîné avec une représentation vectorielle des phrases, en utilisant **la tokenization** pour l'encodage de la dataset.

### 4. Sauvegarde et Test du Modèle
Après l'entraînement, le modèle est sauvegardé afin de pouvoir être réutilisé pour prédire les actions à partir de nouvelles descriptions textuelles.

Des améliorations futures pourraient inclure :
- L’intégration d’un **modèle plus avancé** (comme BERT) pour améliorer la compréhension du langage.
- L’application sur un **robot physique**, en complément des capteurs classiques.

## Exécution du projet
### Prérequis
Assurez-vous d'avoir installé les bibliothèques suivantes :
```bash
pip install pandas numpy tensorflow scikit-learn
```

### Exécution du modèle

   Exemple input:
   ```
   "Il y a un obstacle à gauche"
   ```

   Output:
   ```
   Command: tourner à droite
   ```

## Auteurs

- GitHub : https://github.com/ourahma/Robot_Action_Prediction
- Contact : marouaourahma@gmail.com
- Linkedin: www.linkedin.com/in/maroua-ourahma-293426235
  

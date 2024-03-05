# Readme: SAE Reconnaissance Faciale
 Paul Montagnac, FA3
---
Cette SAé est un fork du projet de Mr. Cabessa, disponible sur https://github.com/JeremCab/ModelisationMathBUT/tree/main/SAE_FA

Le but de cette SAé est de construire un système de reconnaissance faciale qui fonctionne en temps réel, à l'aide d'une caméra.
![](https://github.com/JeremCab/ModelisationMathBUT/blob/main/SAE_FA/moi.png?raw=true)

---
### Problème rencontré lors de l'utilisation

Pour les tests, les notebook ont été utilisés sur un Macbook Pro, équipé d'un processeur M2 Pro. 

Le programme fonctionne correctement, le problème est le suivant:
- Le programme se 'freeze' lorsqu'on appuie sur Echap pour éteindre la fenêtre de reconnaissance faciale.
- Le seul moyen de le débloquer est d'ouvrir le gestionnaire des tâches et de forcer la fermeture de Python.

Après concertation avec un autre groupe qui a obtenu le même problème, il semblerait que celui-ci soit lié à l'architecture Silicon d'Apple.

Cependant, celui-ci n'est pas dérangeant dans son  fonctionnement global.

---
### 1. Ajout du SVM
La première consigne après avoir vérifié que l'algorithme fonctionne, est d'implémenter un algorithme de classification de notre choix. 

Après plusieurs recherches, le choix s'est porté sur l'utilisation du SVM (Support Vector Machine).

Celui-ci est disponible dans le fichier **2_algo.ipynb**.

---
### 2. Ajout d'un système pour le cas de reconnaissance binaire

Nous avons ajouté un système qui permet lors de l'input d'un nom, de rajouter également un input "admis" ou "non-admis".

Lors de l'exécution de la reconnaissance faciale, celle-ci indique donc le nom du visage ainsi que son status sous la forme **Nom:admis** ou **Nom:non-admis**

![admis.png](admis.png)
---
### 3. Implémentation d'un réseau de neurones (MLP)

Le choix d'un réseau de neurones s'est porté sur le Multi-Layer Perceptron, son implémentation est disponible dans le notebook **"2_algo-MLP.ipynb"**

---
### 4. Implémentation d'un réseau de neurones convolutionnels (CNN)

Une fois que l'implémentation du MLP était correcte, nous avons déterminés l'utilisation du CNN. 

Nous avons pu définir notre modèle et l'entraîner sur le peu de données que nous avions à l'aide de Tensorflow Keras. 

---
### Fonctionnalités supplémentaires
L'implémentation d'une probabilité de prédiction a été également effectuée dans le modèle. Celle-ci s'affiche à côté de notre visage sous la forme suivante, par exemple:
**Paul:admis(0.48)** 

---
### Remarques
Le dataset n'est pas très conséquent, la qualité du modèle et de la conséquence faciale peut donc être biaisée, les tests ayant été effectués sur 30 photos pour 3 visages différents.
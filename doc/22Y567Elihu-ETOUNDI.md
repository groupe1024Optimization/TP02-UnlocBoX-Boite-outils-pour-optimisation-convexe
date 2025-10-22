# Fichier Personnel de Suivi de Projet

## Informations Personnelles
- **Nom** : ETOUNDI  
- **Prénom** : Elihu  
- **Matricule** : 22Y567 

Dans le cadre de ce TP, mon objectif était de comprendre concrètement comment les méthodes de **splitting proximal** permettent de résoudre des problèmes d’optimisation convexe, et d’expérimenter la boîte à outils **UNLocBoX** sous MATLAB/Octave.  
Au-delà de l’aspect théorique, j’ai voulu aller vers une compréhension pratique : comment formuler un problème, choisir les bons solveurs et interpréter les résultats numériques.

---

## 1. Présentation théorique

Avant toute implémentation, j’ai pris le temps de revoir les bases :  
- La distinction entre **fonctions différentiables** et **non-différentiables**, et pourquoi cela conditionne le choix du solveur.  
- Le rôle des **opérateurs proximaux** dans la décomposition des problèmes complexes.  
- Une exploration des principaux **solveurs UNLocBoX** (Forward-Backward, Douglas-Rachford, ADMM…), chacun adapté à une structure de problème spécifique.  

Cette partie m’a permis de mieux comprendre comment une approche mathématique peut se traduire en un outil algorithmique concret.

---

## 2. Mise en pratique

J’ai ensuite formulé un **problème d’optimisation simple** :
\[
\min_x \|Ax - y\|_2^2 + \lambda \|x\|_1
\]
Ce problème illustre bien la combinaison d’un **terme de fidélité** (mesure de l’erreur) et d’une **régularisation L1** (qui favorise la parcimonie).  

À partir de là, j’ai implémenté le modèle avec la fonction `solvep`, tout en explorant les **paramètres du solveur** : le pas de temps `gamma`, la tolérance `tol`, le nombre maximal d’itérations `maxit`, et le choix du solveur `method`.  
J’ai aussi expérimenté l’ajout de **contraintes convexes** à travers des opérateurs de projection.

---

## 3. Applications expérimentées

Pour mieux ancrer ces notions, j’ai exploré plusieurs cas d’application concrets :
- **Débruitage d’images**, où la régularisation L1 aide à préserver les détails tout en éliminant le bruit.  
- **Inpainting**, qui permet de reconstruire des zones manquantes d’une image grâce à la variation totale.  
- **Compressed Sensing**, illustrant la puissance de la parcimonie dans la reconstruction de signaux à partir de peu de mesures.  

Ces exemples m’ont permis de constater la polyvalence et la robustesse d’UNLocBoX dans des contextes très différents.

---

## 4. Résultats et interprétation

Les résultats obtenus montrent une **convergence stable** du solveur, avec une erreur de reconstruction raisonnable.  
Même si le résultat n’est pas parfait (erreur autour de 0.65 dans mon cas), il illustre bien la capacité du modèle à approcher la solution optimale.  

Cette expérience m’a permis de mieux saisir le lien entre les **concepts théoriques d’optimisation** et leur **implémentation pratique**.  
En somme, travailler avec UNLocBoX m’a donné une compréhension plus concrète des méthodes de splitting proximal et de leur intérêt pour les problèmes réels d’optimisation.

---

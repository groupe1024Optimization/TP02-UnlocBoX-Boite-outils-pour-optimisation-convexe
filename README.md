## Université de Yaoundé I — INF 4127 : Optimisation II
# TP02 – UNLocBoX : Boîte à outils pour l’optimisation convexe


## Auteurs

* MVOGO MONDOMAN Franck Stéphane (20Y058)
* ETOUNDI TSANGA Elihu Frédéric (22Y567)
* ABANDA Armand Wilfried (21T2487)

  
## Objectif du TP
Comprendre les notions de splitting proximal et utiliser UNLocBoX pour la résolution de problèmes d’optimisation convexe.

## Contenu du projet
- Présentation Beamer sur UNLocBoX  
- Tutoriel 1 : Auformat pdf  
- Tutoriel 2 : Page web 

## Installation
1. Télécharger UNLocBoX depuis : [https://lts2.epfl.ch/unlocbox/](https://lts2.epfl.ch/unlocbox/)  
2. Extraire le dossier téléchargé  
3. Dans MATLAB ou Octave, exécuter :
   ```matlab
   addpath('chemin/vers/unlocbox');
   init_unlocbox;

## Exemple d’utilisation

```matlab
% Chargement de UNLocBoX
init_unlocbox;

% Données du problème
x = randn(100,1);
A = randn(100);
b = A*x + 0.05*randn(100,1);

% Définition des fonctions
f1.grad = @(x) A'*(A*x - b);
f1.eval = @(x) 0.5*norm(A*x - b)^2;
f1.beta = norm(A)^2;

f2.prox = @(x, T) max(0, x - T) - max(0, -x - T);
f2.eval = @(x) norm(x, 1);

% Paramètres du solveur
param.verbose = 1;
param.maxit = 200;
param.tol = 1e-6;

% Appel du solveur
sol = solvep(x, {f1, f2}, param);

% Affichage des résultats
fprintf('Erreur de reconstruction : %.4f\n', norm(A*sol - b)/norm(b));
```


## Références

* UNLocBoX : [https://lts2.epfl.ch/unlocbox/](https://lts2.epfl.ch/unlocbox/)
* Combettes & Pesquet (2011). *Proximal Splitting Methods in Signal Processing.*

```

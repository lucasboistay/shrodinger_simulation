# TP de Physique Numérique : Dynamique Quantique

La possibilité de décrire l’évolution temporelle d’un système quantique, c’est à dire l’évolution au cours du temps de sa fonction d’onde $\Psi(\vec{r}, t)$, est un des résultats majeurs de la physique quantique. Pour cela, il est nécessaire de résoudre **l’équation de Schrödinger** dépendante du temps :

$$i \hbar \frac{\partial}{\partial t}\Psi(\vec{r},t) = \hat H \Psi(\vec{r},t)$$

où $\hat{H}$ est le hamiltonien du système et où l’on suppose connue la fonction d’onde $\Psi(\vec{r}, t =0)$ à un instant initial. Hormis quelques cas particuliers où des solutions analytiques peuvent êtres trouvées (souvent au prix d’approximations), on a recourt en général à des méthodes d’intégration numériques.

## Installation 

Pour installer le dossier, copier dans la console git 
```sh
git clone https://github.com/Rockinfox91/phys_num_quantique.git
```

puis lancer Jupyter Notebook

# Partie 1 - Etats stationnaires

Dans un premier temps, on pourra considérer uniquement les états stationnaires du problème, ce qui permettra de traiter d’abord la discrétisation spatiale.

## Vérification de la validité du modèle numérique

Le but ici est de modéliser numériquement des états stationnaires avec un potentiel indépendant du temps.

On va alors pour voir par exemple faire l'application numérique avec des potentiels : 

- Nul (qui représente donc un puit de potentiel infini aux limites)
- Harmonique (en x²)

Ce qui nous permet de les comparer aux résultats théorique et de vérifier la validité de la modélisation numérique.

### Puit de potentiel infini

![](/docs/statio/psi_fonction_de_x_puit_infini_n100.png?raw=true)
![](/docs/statio/psi_fonction_de_x_puit_infini_n1000.png?raw=true)

### Potentiel Harmonique

![](/docs/statio/psi_fonction_de_x_harmonique_n100.png?raw=true)
![](/docs/statio/psi_fonction_de_x_harmonique_n1000.png?raw=true)

## Tentative avec d'autres potentiels plus compliqués

Ensuite, on tente des potentiels plus complexes tel que :

- Le double puit de potentiel
- Potentiel périodique
etc...

On peut voir les résultats des rendus dans le dossier document.

# Partie 2 - Évolution temporelle dans le cas d’un puits infini et d’un potentiel harmonique

On étudie dans cette partie l’évolution temporelle de la fonction d’onde $\Psi(x, t)$ d’un état décrit par une fonction d’onde initiale $\Psi(x, 0)$.

On considèrera d’abord le puits infini et le potentiel harmonique, pour lesquelles les solutions analytiques exactes sont connues, afin de vérifier l’évolution temporelle obtenue numériquement.

## Algorithme d'Euler

Ici, on utilise l'algorithme d'Euler explicite pour obtenir l'évolution temporelle de la fonction d'onde. Cet algorithme, bien que simple à utiliser, n'est pas très efficace.

Lors de la partie 1, on utilisait un Hamiltonien à valeurs réelles, ici nous sommes obligés d'utiliser des valeurs complexes.

### Puit de potentiel inifini

#### Etat stationnaire

![](/docs/tempo/psi_fonction_de_x_euler_etat_statio0_m10000_duree_10.jpeg?raw=true)
![](/docs/tempo/psi_fonction_de_x_euler_etat_statio0_m100000_duree_10.jpeg?raw=true)

#### Paquet d'onde gaussien

![](/docs/tempo/psi_fonction_de_x_euler_gaussienne_m10000_duree_1000.jpeg?raw=true)

![](/docs/tempo/psi_fonction_de_x_euler_gaussienne_m10000_duree_2000.jpeg?raw=true)

![](/docs/tempo/psi_fonction_de_x_euler_gaussienne_m100000_duree_10000.jpeg?raw=true)

![](/docs/tempo/anim.gif?raw=true)
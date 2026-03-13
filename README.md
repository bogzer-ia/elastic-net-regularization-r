# Régression Elastic Net en R

Ce projet explore l'utilisation de la méthode de régularisation **Elastic Net** dans le cadre de la régression linéaire. Elastic Net combine les pénalisations **L1 (Lasso)** et **L2 (Ridge)** afin de traiter les problèmes de **multicolinéarité** et de **surapprentissage** dans les modèles comportant un grand nombre de variables explicatives.

## Objectif du projet

L'objectif principal de ce projet est d'étudier le comportement de la méthode Elastic Net dans différentes configurations de données. Plus précisément, l'étude analyse l'influence :

- du nombre de prédicteurs
- de la corrélation entre les variables explicatives
- du paramètre de régularisation α

sur la performance du modèle.

## Méthodologie

L'analyse comprend plusieurs étapes :

- Génération de jeux de données simulés avec différentes structures de corrélation
- Ajustement de modèles Elastic Net à l'aide du package **glmnet**
- Sélection du paramètre de régularisation **λ** par validation croisée
- Comparaison des performances des modèles à l'aide de l'erreur quadratique moyenne (**MSE**)
- Réalisation d'une simulation **Monte Carlo** pour évaluer la robustesse des résultats

## Conception de l'expérience

Deux configurations principales ont été étudiées :

- un modèle avec un faible nombre de prédicteurs (**p = 3**)
- un modèle de grande dimension (**p = 80**)

Différents niveaux de corrélation entre les variables ont également été testés :

- ρ = 0.5
- ρ = 0.8

Les modèles Elastic Net ont été estimés avec différentes valeurs du paramètre **α** :

- α = 0.1 (proche de Ridge)
- α = 0.5 (Elastic Net équilibré)
- α = 0.9 (proche de Lasso)

Le paramètre **λ** est sélectionné automatiquement à l'aide de la validation croisée.

## Résultats principaux

Les résultats montrent que :

- une forte corrélation entre les variables explicatives augmente généralement l'erreur de prédiction
- une valeur élevée de **α** (proche de Lasso) permet de sélectionner moins de variables
- une valeur intermédiaire de **α** offre souvent un bon compromis entre sélection de variables et performance prédictive
- la régularisation améliore la stabilité du modèle lorsque le nombre de variables est élevé

Les simulations Monte Carlo confirment la robustesse de la méthode Elastic Net dans différents contextes de corrélation entre variables.

## Outils utilisés

Ce projet a été réalisé avec **R** et les packages suivants :

- glmnet
- MASS
- ggplot2
- knitr
- kableExtra

## Auteur

Boga

## Référence

Zou, H., & Hastie, T. (2005). *Regularization and Variable Selection via the Elastic Net*. Journal of the Royal Statistical Society Series B.

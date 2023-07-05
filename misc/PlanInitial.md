[toc]

# Introduction

## Définition et mise en concept des techniques de reconnaissance d'images

### Vision par ordinateur et reconnaissance de forme

Introduction aux concepts de classification, segmentation sémantique (multiclasses/multilabels) et détection.

### Les différentes catégories d'apprentissage machine et spécificité de la vision par ordinateur.

Distinction entre apprentissage supervisé, non supervisé et hybride

### Les années 2010 et l'émergence de l'apprentissage profond

Rapide présentation des spécificités du Deep Learning (en terme des descentes de gradients utilisant la "chain rule" et la notion d'architecture agnostique du problème)

### Les algorithmes employés dans le milieu clinique

Recherche brève et historique des techniques de vision par ordinateur déjà employé cliniquement, l'accent étant mis sur l’ophtalmologie

## Introduction l'imagerie ophtalmologique

### Structure anatomique de l'oeil

### Imagerie médicale rétinienne

Introduction aux techniques d'acquisition d'images de la rétine, présentant le fond d’œil, l'OCT (SD-OCT) et ouvrant sur les techniques plus ré

centes (OCT-A, wide field, acquisition vidéo, ...)

### Pathogenèse de la rétinopathie diabétique.

Description des marqueurs de la maladie, son développement et son traitement thérapeutique.

## Éléments de la problématique

### Comment faire face à l'afflux de patients atteints de rétinopathie diabétique?

Détail des chiffres d'incidence et prévalance à la fois du diabète et des maladies oculaires afférentes et synthèse des analyses invoquant la nécessité à la fois de la télémédecine et du diagnostic automatisé, du moins pour le dépistage.

### Quelle approche pour une classification automatisée efficace de la rétinopathie diabétique?

Description des limitations structurelles des approches supervisées, non supervisée, directe ou hybride (via )

### Comment quantifier la généralisation d'un modèle à différentes populations?

Introduction de la problématique liée à la notion de généralisation de modèles, présentation du principe de compromis "biais-variance".  Nécessité de construire des métriques "qui font sens", prenant en compte la diversité des situations (maladies/populations à fortes/faibles prévalances, déséquilibre de classes ) et de tester sur différents échantillons (donc collecte de données pluri-sources).

### Qu'améliorer pour favoriser l'acceptabilité et l'adoption clinique d'une IA?

Mise en avant de la problématique de la boîte noire et de l'inhérente complexité de la compréhension du processus de modélisation d'un réseau de neurones.

Introduction du concept d'interprétabilité et d'explicabilité. Identification des biomarqueurs via une approche supervisée ou modèle hybride intégrant une étape de segmentation.

### Comment quantifier l'incertitude d'une prédiction automatisée?

L'incertitude sert à montrer la variabilité de la prédiction d'un modèle pour une même donnée. C'est une grandeur intuitive qui peut servir d'indicateur de confiance dans une prédiction. Un modèle stochastique est une base pour un échantillonnage de Monte-Carlo de la prédiction dont la variance quantifie l'incertitude.

### L'identification de biomarqueurs de la rétinopathie peut-elle servir à prédire une maladie cardiovasculaire?

## Objectifs de recherche

### Concevoir un protocole de collecte et d'annotations de données adaptées au fond d'oeil

### Proposer une étude comparative des modèles de segmentation de lésions rétiniennes existants

### Analyser les spécificités des bases de données d'images

### Démontrer les limites de la fusion de modèles issues de bases de données diverses

### Proposer une fusion effective de modèles se basant sur l'Alignement des Noyaux Centrés (CKA)



## Plan du mémoire



# Revue de littérature

## Applications des réseaux de neurones pour la vision par ordinateur

Revue de littérature générale sur les grands jalons des architectures de classification d'images. Cette partie sert à expliquer le fonctionnement détaillé de l'apprentissage machine

### Architectures et optimisation de l'apprentissage

### Pré-entraînements et finetuning

### Choix de fonctions de coûts

### Optimisation d'hyperparamètres

#### Protocole expérimental et suivi de résultats

## Segmentation des lésions rétiniennes

Introduction sur la spécificité des approches de segmentation 

### Approche sans apprentissage

### Émergence des modèles neuronaux

#### Réseaux convolutifs

#### Réseaux auto-attentifs

## Classification directe de la rétinopathie diabétique

### Approche statistique globale de la classification

#### Pré-réseau de neurones

#### Ère des réseaux de neurones, des modèles convolutifs vers les modèles auto-attentifs 

#### Métrique d'évaluations

### Interprétabilité des modèles globaux

### Approche hybride ascendante par exploitation de marqueurs locaux de l'image

#### 

# Segmentation sémantique des structures rétiniennes dans l'imagerie de fond d’œil

## Préalable

### Types de biomarqueurs rétinien et pertinence clinique

### Utilité des approches de segmentation

### Mise en place d'un protocole d'annotations de données

## Méthodologie

### Collecte et description statistique des bases de données existantes

### Conception d'une architecture de segmentation multiclasse

### Analyse comparative des performances inter-base de données

### Comparaison de modèles par analyse du critère d'indépendance de Hilbert-Schmidt des caractéristiques multi-couches.

### Fusion multi-modèle guidée par cartes de proximité

## Résultats

### Performance comparée à l'état de l'art relatif à la segmentation sémantique

### Relation entre la distribution statistique des annotations et les performances des modèles

### Amélioration apportée par la fusion multi-modèles

### Performance de classification par comptage de lésions

## Discussion

### Généralisation

### Mise en place de standards d'annotations dans le cadre des protocoles de collecte des données

### De la nécessaire approche globale de classification pour obtenir plus de données et de meilleures performances

#  Interprétabilité d'un modèle de classification par attention concentrée

## Introduction

### Interprétabilité post-hoc des modèles neuronaux

#### Approche par perturbations locales 

#### Approche par occlusion

#### Approche par rétro-propagation des gradients

#### Approche par propagation de la pertinence

### Réseaux auto-attentifs

### Principe de fonctionnement

### Forces et limitations du modèle

### Revue de littérature des améliorations récentes proposées

## Méthodologie

### Ré-échantillonnage des morceaux d'images par foulée adaptative

### Introduction au concept d'Attention Concentré et échantillonnage conditionnel

## Protocole expérimental

### Collecte de données

### Mise en place d'une plateforme de sondage d'expertise clinique pour évaluer la pertinence du modèle

### Évaluation de la généralisation des modèles

### Étude de régime de consommation de données

## Résultats expérimentaux

### Comparaison à l'état de l'art

### Analyse statistique de l'appréciation clinique des méthodes d'interprétabilité 

#  Intégration des marqueurs sémantiques pour un modèle descriptif de la classification de la rétinopathie diabétique

## Motivation

Synthétiser les limites des deux précédents chapitres pour justifier ce nouveau.

## Méthodologie

### Attention sémantique concentrée: une approche descriptive de la classification

### Détermination de l'incertitude par échantillonnage de Monte-Carlo

## Résultats

### Comparaison à l'état de l'art

### Étude du régime de consommation de données

### Analyse des améliorations apportées par l'intégration de la segmentation 



#  Applications de l'IA pour l'ophtalmologie: projets annexes

## Prédiction de conversion de la dégénérescence maculaire liée à l'âge

## Utilisation des marqueurs sémantiques pour l'évaluation de la qualité d'image de fond d’œil

## Modèle génératif pour la prédiction structurelle post-opératoire de la rétine.

## Utilisation de l'imagerie de fond d'oeil pour la détection de maladie cardio-vasculaire 



# Conclusions

## Synthèse des travaux et résultats principaux

## Impact et portée scientifique des solutions proposées

### Limitations et améliorations futures

# Référence

# Annexes

## Éthique de la recherche: éléments de réflexion personnelle sur le processus d'utilisation des données médicales et l'utilisation d'algorithmie à des fins diagnostics

## Communication scientifique et partage pédagogique: un tour d'horizon des outils crées et utilisés lors cette thèse








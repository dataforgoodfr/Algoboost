# Analyse nutritionnelle des algues alimentaires en France

## Présentation
Ce dépôt rassemble un ensemble de travaux visant à compiler, nettoyer, analyser et visualiser les données nutritionnelles des algues alimentaires consommées en France.
L’objectif principal est de comparer les profils nutritionnels des algues avec ceux d’autres groupes d’aliments, en s’appuyant sur des bases de données publiques :

CIQUAL (ANSES) — Table de composition nutritionnelle des aliments

CEVA (Centre d’Étude et de Valorisation des Algues) — Données spécifiques aux macroalgues

Les jeux de données utilisés ont été téléchargés en août 2025.

Le projet comprend :

- la préparation des données (nettoyage, harmonisation, fusion)

- la visualisation des nutriments clés (fibres, protéines, minéraux, vitamines…)

- des analyses multivariées (ACP/PCA) pour situer les algues par rapport à d’autres aliments

- des comparaisons avec les apports nutritionnels de référence (RNP, LSS)


## Méthodologie
### 1. Collecte des données
Les données proviennent exclusivement de sources publiques :
**CIQUAL 2025 :** composition nutritionnelle standardisée des aliments en France, 
téléchargé d'ici : https://ciqual.anses.fr/#/cms/download/node/20

**CEVA :** données spécifiques aux macroalgues (fibres, minéraux, iode, protéines…), téléchargé ici : https://www.ceva-algues.com/document/fiches-de-composition-nutritionnelle-algues-alimentaires/

Les fichiers XML/XLXS/CSV ont été importés puis convertis en DataFrames.

### 2. Nettoyage et harmonisation
Les étapes principales incluent :

normalisation des noms d’aliments et des unités

fusion CIQUAL + CEVA pour obtenir une table complète des algues

gestion des doublons et valeurs manquantes

conversion des nutriments en g/100 g, mg/100 g ou µg/100 g

création d’un MultiIndex pour structurer les nutriments par catégories


### 3. Visualisation des nutriments
Des tableaux et graphiques ont été produits pour analyser la quantité de nutriments présents dans 100 g de chaque algue et les comparer aux valeurs de référence nutritionnelles pour la population. Les nutriments étudiés incluent :
- fibres (pas de LSS)
- protéines (pas de LSS)
- minéraux (calcium, fer)
- vitamines
- iode
- pourcentages des RNP (Références Nutritionnelles pour la Population)
- pourcentages des LSS (Limites Supérieures de Sécurité)

Les fichiers Excel dans le dossier **charts_references_nutritionnelles/** regroupent ces visualisations.

### 4. Analyses multivariées (PCA)
Plusieurs analyses en composantes principales ont été réalisées pour :
- comparer les algues entre elles
- situer les algues par rapport à d’autres groupes d’aliments riches en fibres, protéines, minéraux ou vitamines
- identifier les aliments les plus proches des algues en termes de profil nutritionnel
- explorer les axes de variation dominants dans les nutriments

Les résultats sont disponibles sous forme de notebooks et de fichiers HTML interactifs dans le dossier **ACP_algues/**.

## Objectifs scientifiques
Mieux comprendre la place des algues dans l’alimentation française

Identifier leurs atouts nutritionnels (fibres, iode, minéraux, protéines…)

Comparer les algues à d’autres aliments via ACP

Évaluer leur contribution potentielle aux apports nutritionnels recommandés

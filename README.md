# Projet - Analyse des données : Bourgogne / Franche-Comté

Projet d'analyse des données - Comparaison socio-démographique des anciennes régions Bourgogne et Franche-Comté à l'aide de méthodes de statistique multivariée (ACP, AFC, clustering).

## Le projet

Étude réalisée à partir du jeu de données `rp2012` (package R), issu du recensement des communes françaises de plus de 2000 habitants, filtré sur les communes de Bourgogne et Franche-Comté (195 communes, 60 variables : catégories socio-professionnelles, classes d'âge, logement, éducation...).

L'objectif est d'identifier et de caractériser les différences entre les deux régions, en travaillant sur les variables en proportion pour ne pas biaiser l'analyse par la taille des populations.

### Étapes de l'analyse

* **ACP démographie / chômage / immobilier / éducation** : analyse en composantes principales centrée réduite (Dijon et Besançon exclues car trop excentrées) sur les variables de classes d'âge, diplôme du supérieur, logement HLM, propriété, chômage et agriculture. Identification des axes opposant propriétaires/maisons aux HLM/chômage (axe 1), et jeunes aux personnes âgées (axe 2)
* **AFC (Analyse Factorielle des Correspondances)** entre départements et classe d'âge dominante, validée par un test du χ² (rejet de H0), permettant de préciser les tendances démographiques observées en ACP
* **ACP sur le niveau d'éducation** des deux régions, révélant une tendance de la Franche-Comté vers un niveau de diplôme plus élevé (bac, bac+2, supérieur), et de la Bourgogne vers des diplômes de type CAP/BEP
* **Clustering** (classification ascendante hiérarchique par la méthode de Ward, puis k-means) réalisé séparément pour la Bourgogne et la Franche-Comté (3 groupes chacune), afin de caractériser les profils de communes selon leurs similarités socio-économiques

## Résultats principaux

* La **Bourgogne** se distingue par une population plus âgée et une plus grande stabilité économique entre ses clusters de communes, en partie attribuée à la viticulture
* La **Franche-Comté** montre une population plus jeune, un niveau d'éducation globalement plus élevé, mais une plus grande hétérogénéité socio-économique entre ses communes — expliquée notamment par la présence d'une zone frontalière et une dépendance historique à l'industrie

## Structure du projet

* `Markdown_Gambardello_ANS.Rmd` : script R Markdown avec l'ensemble des analyses
* `Markdown_Gambardello_ANS.pdf` : rapport compilé
* `Sujet projet ANS.pdf` : énoncé du projet
* `Projet ANS.Rproj` : fichier projet RStudio

## Lancer l'analyse

1. Cloner le projet ou télécharger les fichiers
2. Installer les packages nécessaires

```r
install.packages(c("questionr", "ggplot2", "plotly", "dplyr", "patchwork", "FactoMineR", "factoextra"))
```

3. Ouvrir `Markdown_Gambardello_ANS.Rmd` dans RStudio et compiler (Knit)

## Auteur

Clara GAMBARDELLO
Projet Analyse des données (2024/2025)

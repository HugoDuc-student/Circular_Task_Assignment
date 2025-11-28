<h1 align="center">Circular Task</h1>

*28 November 2025, 11:00*
*by Devaux Yann, Duchemin Hugo, Bertrand- -Goarin Malo*

Tools : 
Fichier CSV (001MoDe_R1.csv and 001MoDe_R1.marker.csv).
Application MouseReMoCO
GPT : ChaptGPT, Copilot, Gemini 

# 1. Définition du projet 

Le projet à été défini en suivant la construction d'objectif SMART, la répartition des tâches, un plan de travail. 

L'objectif global est de réaliser une analyse complète et reproductible de la tâche circulaire enregistrée par MouseReMoCo et de livrer les résultats dans un dépôt GitHub public.

**Spécifique :** Reproduire les graphiques et recalculer les statistiques de la tâche de ciblage circulaire (Fitts' Law) en utilisant les fichiers de données brutes fournis et un fichier généré par l'équipe.

**Mesurable :**
Les résultats sont vérifiés par : 
1) La correspondance des graphiques générés avec les résultats attendus. 
2) La concordance des valeurs statistiques recalculées (Rec001 à Rec005) avec celles du fichier .marker.csv. 
3) L'exécution réussie sur un fichier auto-généré. 
4) La présence d'un rapport de 1 à 2 pages et d'une structure de dépôt propre.

**Atteignable :** 
Le temps imparti et la répartition des rôles (manager, code, rapport) rendent l'objectif aisément réalisable si les délais sont respecter et que la communication dans l'équipe est bonne. 

**Réaliste :** L'équipe dispose des compétences et des outils nécessaires (Python, GitHub, MouseReMoCo) pour l'analyse des données de mouvement et la collaboration en ligne.

**Temporelle :** Le projet est encadré par les dates de réunions établies: 13/11 (Organisation), 19/11 (Compréhension/Tâches), 28/11 (Revue/Merge), avec une livraison attendue peu après la réunion finale (non spécifiée, mais implicitement dans un délai court).



## 2. Plan de travail détaillé par rôle

**Hugo (Manager et Code des « Ronds »)**

Responsabilités de Manager (Gestion de Projet):

- Créer le dépôt GitHub à partir du Python-for-HMS-Template.
- Assurer l'accès et les droits de collaboration pour Yann et Malo.
- Superviser l'intégration des contributions, être le seul à fusionner (merge) les pull requests (PRs).
- Gérer les conflits de merge si nécessaire.
- S'assurer que les dates butoirs et les objectifs sont respectés.

Responsabilités de Code (Analyse Circulaire):
- Développer le code principal pour lire et analyser les données de la tâche circulaire.
- Calculer les métriques spécifiques aux « ronds » : rayon effectif ($R_e$), tolérance effective ($T_e$), pourcentage d'erreur, et le nombre de tours (nLaps).
- Vérifier les coordonnées du centre ($C_x, C_y$) et du rayon cible ($R_{task}$) à partir des données d'en-tête.

**Yann (Code des « Vagues » / Analyse de Performance)**

Responsabilités de Code (Analyse de Vitesse et Débit):
- Développer le code pour calculer les métriques de performance et de débit d'information (liées aux « vagues » de mouvement).
- Calculer le temps de mouvement par tour ($MT/lap$).
- Calculer le débit d'information effectif par tour ($ID_e/lap$).
- Calculer le biais ($B_e$).
- Calculer le débit de performance d'information ($IP_e$).
- Intégrer ces calculs avec la partie d'Hugo.

**Malo (Vulgarisation, Rapport et Documentation)**

Responsabilités de Documentation et Rapport:

- Rédiger le Rapport d'analyse (1-2 pages).
- Expliquer les difficultés les plus intéressantes rencontrées (notamment la contrainte numpy/matplotlib) et les solutions apportées.
- Détailler la méthode de vérification des résultats (concordance avec le fichier .marker.csv).
- Expliquer la répartition des tâches et l'organisation de l'équipe (ce plan).
- Rédiger le README général du dépôt (voir brouillon ci-dessous).
- Préparer une vulgarisation scientifique des calculs et des concepts clés (Loi de Fitts, ID, IP) pour le rapport.

**Tâches Communes** 

Exploration de MouseReMoCo. 
*Chaque membre doit jouer avec le logiciel pour comprendre comment les données sont enregistrées (position curseur/cible, temps, événements).*

Lecture et Nettoyage des Données
*Développer une fonction pour lire les fichiers .csv et .marker.csv sans utiliser pandas (nécessite la lecture ligne par ligne avec numpy ou les fonctions os/numpy.loadtxt avec soin pour l'en-tête).*

Génération de Données: 
*Chaque membre du groupe à tester la génèration d'un fichier de données propre pour le test final.*

Vérification Croisée: 
*Réaliser une revue de code et des résultats des coéquipiers avant la fusion.*

| Date | Objectif | Responsable Principal | Livrables/Résultats |
| :--- | :--- | :--- | :--- |
| **13/11** | Organisation du travail, création du dépôt GitHub. | Hugo (Manager) | Dépôt GitHub créé, Rôles attribués, Plan de travail (SMART) défini. |
| **19/11** | Compréhension approfondie de la tâche (MouseReMoCo) et attribution des tâches de codage. | Tous (Malo pour les concepts) | Premières fonctions de lecture de données, branches de travail créées. |
| **28/11** | Revue des tâches, vérification des résultats, fusion finale (Merge). | Hugo (Manager) | Calculs et graphiques vérifiés, Rapport et README finalisés. |



# Limites et difficultés courantes 

*Contrainte Technique : numpy et matplotlib Uniquement*

<u>Difficulté 1:</u> Lecture de Fichiers CSV Non StandardLe fichier .csv contient un en-tête non standard (métadonnées). L'utilisation de pandas aurait rendu cela trivial.

<u>Solution:</u> Il faudra lire l'en-tête (les lignes de commentaires commençant par un caractère spécifique, souvent # ou % si ce n'est pas déjà le cas) pour extraire les paramètres (e.g., $R_{e}, R_{task}, ID$) avant de charger les données brutes (temps, x, y) dans un tableau numpy en spécifiant l'argument skiprows.

<u>Difficulté 2:</u> Représentation Graphique Avancéematplotlib est puissant mais demande plus de code pour des graphiques spécifiques (trajectoires X-Y, vitesse en fonction de l'angle) que des outils orientés statistiques.

<u>Solution:</u> Structurer clairement les fonctions de traçage et utiliser les fonctionnalités de sous-graphiques (plt.subplots()).


*Difficulté Conceptuelle : Interprétation des Données*

<u>Difficulté 3:</u> Détection Précise des Tours (Laps)
Le système compte les tours (nLaps). Le code doit reproduire la logique interne de MouseReMoCo pour déterminer quand un tour est réussi ou complété, souvent basé sur le passage à un angle de 360 degrés ou un critère de franchissement d'un axe.

<u>Solution:</u> Examiner la documentation de la tâche CircularTarget pour trouver la définition exacte d'un « tour ».

<u>Difficulté 4:</u> Synchronisation des Markers
Les temps des markers (.marker.csv) et les temps des données brutes (.csv) doivent être synchronisés pour isoler chaque enregistrement (Rec001 à Rec005). Les temps sont en millisecondes Unix.

<u>Solution:</u> Calculer le temps écoulé depuis le premier événement DoRecord pour aligner les échantillons de données sur les intervalles de 20.000 secondes définis par les markers.


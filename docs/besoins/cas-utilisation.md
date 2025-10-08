---
title: Analyse des besoins - Cas d'utilisation
---

# Cas d'utilisation

## Vue d’ensemble

L'application de gestion d'horaire scolaire permet aux étudiants, professeurs et TGDE d'acceder aux informations pertinentes d'un cours offert tel que la charge de travail, l'horaire, l'éligbilité ainsi que les résultats académiques. L'application permet aussi de personnaliser le profil afin d'obtenir une expérience personnalisée. La plateforme s'intègre avec un service d'authentification propre à l'université de Montréal et récupère des avis étudiants à partir de Discord afin d'améliorer la prise de décision de l'élève ou bien d'aider le professeur à modifier et ajuster le contenu de son cours selon les commentaires. 

## Liste des cas d’utilisation

| ID | Nom | Acteurs principaux | Description |
|----|-----|---------------------|-------------|
| CU01 | Authentification | Étudiant, Professeur, TGDE, Service d'authentification | L'utilisateur se connecte à l'application via un système d'authentification. |
| CU02 | Personalisation du profil | Étudiant (utilisateur principal) | L'utilisateur créer et modifie son profil étudiant. |
| CU03 | Recherche de cours|Étudiant, Professeur, TGDE| L'utilisateur entâme une recherche de cours. |
| CU04 | Filtrer la recherche| Étudiant| L'utilisateur personnalise/filtre sa recherche de cours. |
| CU05 | Consulter info du cours | Étudiant, Professeur, TGDE | L'utilisateur consulte les détails du cours sélectionné |
| CU06 | Vérifier éligibilité au cours| Étudiant, TGDE| L'utilisateur vérifie s'il est éligible à s'inscrire au cours. |
| CU07 | Consulter avis étudiant | Étudiant, Professeur| L'utilisateur consulte les avis étudiants du cours. |
| CU08 | Consulter résultats académiques | Étudiant, TGDE| L'utilisateur consulte ses résultats académiques. |
| CU09 | Comparer charge de travail | Étudiant, Professeur  | L'utilisateur compare des cours.  |
| CU10 | Importer des avis étudiants| Discord | Importe les avis étudiants des cours. |

## Détail

### CU01 - Authentification

**Acteurs** : Étudiant (principal), professeur, TGDE et service d'authentification<br>
**Préconditions** : L'utilisateur possède un identifiant ou une adresse courriel scolaire valide (obtenue via service d'authentification).<br>
**PostConditions** : Le système est connecté selon l'utilisateur. <br>
**Déclencheur** :   Selectionner "Se connecter" <br>
**Dépendances** :   Service d'authentification de l'udem<br>
**But** : L'utilisateur s'authentifie dans la plateforme via ses crédits scolaires. <br>

### Scénario - CU01
1. L'utilisateur ouvre la plateforme de gestion d'horaire.
2. L'utilisateur selectionne "se connecter".
3. Le système redirige vers le service d'authentification de l'udem.
4. L'utilisateur saisit son identifiant et son mot de passe.
5. Le service authentifie l'utilisateur et envoie une confirmation visuelle d'une connexion réussie. 
6. Le système affiche le tableau de bord de l'utilisateur. 

**Scénario alternatif**<br>
2.a L'utilisateur selectionne "J'ai oublié mon mots de passe". <br>
2a.1 Le système redirige l'utilisateur vers le service de récupération de mots de passe de l'udem. <br>
<br>
4a. L'utilisateur saisit le mauvais identifiant ou mot de passe.<br>
4a.1 Le service d'authentification lance un message d'erreur et redemande de saisir les infos. <br>

### CU02 - Personalisation du profil

**Acteurs** : Étudiant (principal), TGDE<br>
**Préconditions** : La connexion au système doit être réussie.<br>
**PostConditions** : Présentation des cours et préférences ajustées à l'étudiant. <br>
**Déclencheur** : L'utilisateur clique sur la pastille de son profil. <br>
**Dépendances** :   <br>
**But** : Ajouter des caractéristiques personnelles à son profil pour une meilleure expérience. <br>

### Scénario - CU02
1. L'utilisateur accède son profil. 
2. Il ajoute/modifie ses informations personnelles. 
3. Il indique ses préférences visuelles pour l'affichage du tableau de bord. 
4. Il sauvegarde ses modifications. 
5. Le système envoie une confirmation visuelle de la mise à jour. 

**Scénario alternatif**<br>
4a. L'utlisateur ne sauvegarde pas ses modifications. <br>
4a.1 Le système envoie un signal visuel qui indique les infos non-enregistrées. 

### CU03 - Recherche de cours

**Acteurs** : Étudiant (principal), professeur, TGDE<br>
**Préconditions** : La connexion au système doit être réussie afin d'avoir l'info de l'étudiant.<br>
**PostConditions** : Résultats de la recherche de cours selon son programme. <br>
**Déclencheur** : L'utilisateur lance la fonction "Consulter des cours". <br>
**Dépendances** :   <br>
**But** : Effectuer une recherche de cours selon le programme de l'étudiant. <br>

### Scénario - CU03

### CU04 - Filtrer la recherche

**Acteurs** : Étudiant (principal), professeur, TGDE<br>
**Préconditions** : <br>
**PostConditions** : Résultats de la recherche de cours. <br>
**Déclencheur** :<br>
**Dépendances** :   <br>
**But** : Filtrer  <br>

### CU05 - Consulter info du cours

**Acteurs** : Étudiant (principal), professeur, TGDE<br>
**Préconditions** : Information du cours <br>
**PostConditions** : Affichage de l'info du cours, des résultats si suivit, de l'éligibilité de l'étudiant, la charge de travail ainsi que les avis étudiants provenant de Discord. <br>
**Déclencheur** : Selectionne un cours après la recherche. <br>
**Dépendances** :   <br>
**But** : Consulter l'horaire d'un cours, sa charge de travail et l'égibilité de l'étudiants ou ses résultats s'il à déjà été suivi.  <br>

### CU06 - Vérifier éligibilité au cours

**Acteurs** : Étudiant(principal), TGDE<br>
**Préconditions** : Résultats scolaires de l'élève. <br>
**PostConditions** : Montre un signal visuel si l'élève est éligible ou non et indique la raison.<br>
**Déclencheur** :<br>
**Dépendances** :   <br>
**But** : Vérifier que l'étudiant est éligible au cours.  <br>

### CU07 - Consulter avis étudiants

**Acteurs** : Étudiant (principal), professeur<br>
**Préconditions** : Doit avoir au moins 5 avis étudiant sur le cours. <br>
**PostConditions** : Affichage agrégée des avis étudiant si seuil minimal atteint, sinon, signal visuel indiquant pas d'avis étudiants.  <br>
**Déclencheur** :<br>
**Dépendances** :   <br>
**But** : Consulter les avis étudiants afin d'éclairer la décision de l'utilisateur.   <br>

### CU08 - Consulter résultats académiques

**Acteurs** : Étudiant (principal), TGDE<br>
**Préconditions** : Résultats scolaires de l'étudiant <br>
**PostConditions** : Affiche résultats scolaire de l'étudiant selon les cours suivit. <br>
**Déclencheur** :<br>
**Dépendances** :   <br>
**But** : Consulter l'horaire d'un cours, sa charge de travail et l'égibilité de l'étudiants ou ses résultats s'il à déjà été suivi.  <br>

### CU09 - Comparer charge de travail des cours

**Acteurs** : Étudiant (principal), professeur<br>
**Préconditions** : Information du cours <br>
**PostConditions** : Affiche la charge de travail totale du cours.  <br>
**Déclencheur** :<br>
**Dépendances** :   <br>
**But** : Comparer les différentes charges de travail des cours afin de prendre une décision éclairée.  <br>

### CU10 - Importer avis étudiants

**Acteurs** : Discord <br>
**Préconditions** : Doit posseder au moins 5 avis étudiants. <br>
**PostConditions** : Montre une vue agrégée des avis étudiants selon le seuil minimal. <br>
**Déclencheur** :Étudiant dépose un avis sur un cours dans Discord. <br>
**Dépendances** :   <br>
**But** : Importer les avis que les étudiants déposent dans Discord.   <br>
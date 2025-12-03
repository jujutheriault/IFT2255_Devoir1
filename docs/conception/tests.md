---
title: Description des tests unitaires
---

# Effets attendus + effets de bord des tests

## Cas d'utilisation : Recherche de cours
Les tests suivant valident les différentes utilisation d'une recherche de cours selon le statut de l'utilisateur. 

### `testSearchCoursesStudent`

**Description du test:**
Ce test simule un étudiant dans un programme IFT (pour le moment, le système agis comme si le programme avait le nom de l'ID des cours donnés mais des améliorations pourront être faites) ainsi qu'une base de données contenant 3 différents cours dont 2 sont des cours d'informatique. Ce test effectue ensuite une recherche de cours.

**Ce qu'on attend:**
On s'attend à ce que la recherche trouve 2 cours. 

**Effet sur le système:** 
On vérifie ainsi que les recherches des étudiants seront bel et bien directement filtrées selon leurs préférences.

### `testSearchCoursesNormalUser`

**Description du test:**
Ce test effectue une recherche sans paramètre par un utilisateur qui n'est pas un étudiant.
Ce qu'on attend:
On s'attend à ce que la liste de tous les cours soit renvoyée puisqu'aucune spécification de filtrage n'a été effectuée.

**Effet sur le système:**
Ce test permet de vérifiée qu'aucune erreur n'arrive si l'utilisateur n'a mis à jour aucun programme dans son dossier. De plus, elle confirme le bon fonctionnement de l'héritage utilisé de la classe User à la classe Etudiant. 

### `testSearchAllCoursesWithQueryParameters`

**Description du test:**
Ce test effectue une recherche en spécifiant le ID "ESP" que figure une seule fois dans notre base de données simulée de cours. 

**Ce qu'on attend:**
On s'attend donc à ce que notre fonction renvoie une liste contenant seulement un cours (ESP3900)

**Effet sur le système:** 
Ce test vérifie que la recherche de cours normal dans la barre de recherche par l'utilisateur fonctionne.  


## Cas d'utilisation : Consulter les détails d'un cours
Les tests suivants valident les principales fonctionnalités de la classe CourseService
### `getAllCourses_returnListClientApi`

**Description du test :**
Il récupère une liste de cours selon les paramètres.

**Ce qu’on attend :**
Une liste contenant 2 éléments.

**Effet sur le système :**
LA réponse de l'API est renvoyée a l'appelant. 

### `getAllCourses_withNullParams_useEmptyMap`

**Description du test :**
Recherche de cours ou aucns paramètres n'est fourni.

**Ce qu’on attend :**
Une liste vide.

**Effet sur le système :**
Le service remplace `NULL` par une map vide pour construire l'URI et le résultat est renvoyé par l'API à l'appelant. 

### `getCourseById_ReturnCourseIfClientApiSucceed`

**Description du test :**
Consulter les détail d'un cours.

**Ce qu’on attend :**
L'instance `Course`retournée par le client HTTP.`

**Effet sur le système :**
La réponse de l'API est encapsulée dans un Optional non vide. 

### `getCourseById_EmptyIfClientApiThrows`

**Description du test :**
Scénario d'erreur lorsque l'API externe ne trouve pas le cours ou échoue.

**Ce qu’on attend :**
Un optional vide.

**Effet sur le système :**
L'exceprion est interceptée dans `CourseService` et non propagée. 

## Cas d'utilisation : Comparer des cours

Les tests suivants valident les principales fonctionnalités de la classe ComparaisonController.

### `testSelectionnerCoursComparer`

**Description du test :**
Il ajoute un cours dans la comparaison.

**Ce qu’on attend :**
Le cours ajouté doit se retrouver à la première position du tableau.

**Effet sur le système :**
Le tableau contient maintenant 1 cours.

### `testDeselectionnerCoursComparer`

**Description du test :**
Il ajoute deux cours, puis en retire un.

**Ce qu’on attend :**
Le cours supprimé disparaît, et l’autre prend sa place.
La deuxième case redevient null.

**Effet sur le système :**
Le tableau se décale automatiquement après la suppression.

### `testComparerCours`

**Description du test :**
Il envoie deux cours à comparer en même temps.

**Ce qu’on attend :**
Les deux cours doivent être ajoutés dans l’ordre : d’abord c1, puis c2.

**Effet sur le système :**
Le tableau contient maintenant 2 cours.

### `testCalculerChargeTotale`

**Description du test :**
Il ajoute deux cours avec 3 et 4 crédits.

**Ce qu’on attend :**
La méthode doit retourner 7.

**Effet sur le système :**
La méthode fait seulement une lecture, pas de modification.

### `testReinitialiserSelection`

**Description du test :**
Il ajoute un cours et réinitialise la sélection.

**Ce qu’on attend :**
Le tableau doit être vide.

**Effet sur le système :**
Le tableau de comparaison est remplacé par un nouveau vide.

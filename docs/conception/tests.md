---
title: Description des tests unitaires
---

# Effets attendus + effets de bord des tests

## Cas d'utilisation : Recherche de cours

## Cas d'utilisation : Consulter les détails d'un cours

## Cas d'utilisation : Comparer des cours

Les tests suivants valident les principales fonctionnalités de la classe ComparaisonController.

1) testSelectionnerCoursComparer

Description du test :
Il ajoute un cours dans la comparaison.

Ce qu’on attend :
Le cours ajouté doit se retrouver à la première position du tableau.

Effet sur le système :
Le tableau contient maintenant 1 cours.

2) testDeselectionnerCoursComparer

Description du test :
Il ajoute deux cours, puis en retire un.

Ce qu’on attend :
Le cours supprimé disparaît, et l’autre prend sa place.
La deuxième case redevient null.

Effet sur le système :
Le tableau se décale automatiquement après la suppression.

3) testComparerCours

Description du test :
Il envoie deux cours à comparer en même temps.

Ce qu’on attend :
Les deux cours doivent être ajoutés dans l’ordre : d’abord c1, puis c2.

Effet sur le système :
Le tableau contient maintenant 2 cours.

4) testCalculerChargeTotale

Description du test :
Il ajoute deux cours avec 3 et 4 crédits.

Ce qu’on attend :
La méthode doit retourner 7.

Effet sur le système :
La méthode fait seulement une lecture, pas de modification.

5) testReinitialiserSelection

Description du test :
Il ajoute un cours et réinitialise la sélection.

Ce qu’on attend :
Le tableau doit être vide.

Effet sur le système :
Le tableau de comparaison est remplacé par un nouveau vide.


6) testCreateUser

Description du test:
le test crée un nouvel utilisateur avec son adresse email.

ce qu'on attend:
l'utilisateur crée son compte avec succès

Effet sur le système:
Un nouvel utilisateur est ajouté dans le système

7) testUpdateUser

Description du test:
le test mets à jour les informations de l'utilisateur.

Effet sur le système:
l'utilisateur voit ses informations modifiées.

8) testDeleteUser

Description du test:
l'utilisateur supprime ses informations de l'application

Effet sur le système:
le système ne reconnaît plus l'utilisateur.
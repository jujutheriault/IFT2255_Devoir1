---
title: Description des tests unitaires
---

# Effets attendus + effets de bord des tests

## Cas d'utilisation : Recherche de cours

## Cas d'utilisation : Consulter les détails d'un cours

## Cas d'utilisation : Comparer des cours

Les tests suivants valident les principales fonctionnalités de la classe ComparaisonController.

1) testSelectionnerCoursComparer

Description : Vérifie qu’un cours sélectionné est correctement ajouté au tableau de comparaison.
Retour attendu : cours[0] = c1.
Effets de bord : taille = 1, première case du tableau modifiée.

2) testDeselectionnerCoursComparer

Description : Vérifie que la suppression d’un cours fonctionne et que le tableau se réorganise correctement.
Retour attendu : cours[0] = c2, cours[1] = null.
Effets de bord : décalage à gauche, taille réduite de 1.

3) testComparerCours

Description : Vérifie l’ajout simultané de plusieurs cours dans la comparaison.
Retour attendu : cours[0] = c1 et cours[1] = c2.
Effets de bord : deux insertions, taille = 2.

4) testCalculerChargeTotale

Description : Vérifie que le total des crédits est bien la somme des crédits des cours ajoutés.
Retour attendu : total = 7.
Effets de bord : aucun (lecture seule).

5) testReinitialiserSelection

Description : Vérifie que la réinitialisation efface bien tout le contenu du tableau.
Retour attendu : cours[0] = null.
Effets de bord : création d’un nouveau tableau vide, taille = 0.

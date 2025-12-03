---
title: Conception - Présentation générale
---

# Conception

Cette section présente les grandes lignes de l’architecture et des choix de conception retenus pour le projet.

## Approche utilisée

L'approche utilisée est basée sur une architecture client-serveur comprenant une séparation en modules selon un concept de Modèle-Vue-Controlleur.Cette approche est renforcée par l'architecture API REST du backend qui est lui aussi séparé en modules spécifiques à une modélisation orientée objet où chaque module correspond à un groupe d'objets pertinents entre eux. 

## Contraintes prises en compte

Pour les contraintes techniques, il y a un découplage total entre le frontend et le backend de l'application. Ceci permet de mieux gérer les problèmes en prenant connaissance plus rapidement de leur provenance. On peut changer le frontend sans toucher au backend. De plus, l'architecture API REST n'est pas dépendant au langage Java et permet une bonne portabilité. Les API REST ont aussi des logiciels de tests dédiés comme Postman qui permet de tester plus facilement l'application et de trouver des erreurs à chaque étape de l'implémentation. L'API REST fait aussi en sorte que le code est réutilisable quasiment partout. La séparation en modules assure aussi un bon fonctionnement de l'application avec une couplage faible et une cohésion élevée. Ceci rend aussi le code réutilisable à plusieurs égards. Ce genre de modélisation permet aussi plus facilement de faire évoluer le logiciel si jamais il devait y avoir un ajout ou une modification spécifique.Les contraintes prises en compte au niveau des exigences sont l'accessibilité et la clarté. La présentation étant exclusivement dans un module en soi. De plus, les données sont centralisées dans le modèle à travers le module de gestion de cours qui permet une recherche de cours,de voir les détails des cours et de les comparer en plus de créer des ensembles de cours et d'estimer leur charge de travail.Ce module est aussi relié à la base de donnée contenant les résultats agrégés. Le module utilisateur permet aux clients de se faire un compte, de le personnaliser et de déposer un avis sur discord s'ils le veulent. La communication par HTTPS assure aussi une sécurité des données sensibles des utilisateurs. 


---
title: Analyse des besoins - Exigences
---

# Exigences

## Exigences fonctionnelles

TODO: Liste des fonctions que le système doit accomplir.

Exemple :

- [ ] EF1 : L’utilisateur peut créer un compte.
- [ ] EF2 : Le système envoie un courriel de confirmation.

## Exigences non fonctionnelles

- [ ] ENF1 : L'application doit être compatible avec Chrome, Firefox et Safari.
- [ ] ENF2 : L'application doit être compatible avec plusieurs langages pour les étudiants internationaux.
- [ ] ENF3 : Signaux visuel si erreur dans une étape.
- [ ] ENF4 : Interface minimale et simple à utiliser.
- [ ] ENF5 : L'application doit protéger les données confidentielles de l'utilisateur. 
- [ ] ENF6 : L'application doit avoir une capacité de stockage adéquate.
- [ ] ENF7 : L'application doit avoir un temps de réponse de moins de 2 secondes. 

## Priorisation

TODO: Identifier les exigences critiques.

## Types d'utilisateurs

> Identifier les différents profils qui interagiront avec le système.

| Type d’utilisateur | Description | Exemples de fonctionnalités accessibles |
|--------------------|-------------|------------------------------------------|
| Utilisateur invité | Accès limité, pas d’authentification | Consultation des ressources |
| Utilisateur authentifié | Compte personnel, fonctions principales | Réservation, historique |
| Administrateur | Droits étendus, gestion des ressources | Création/suppression de ressources, gestion des utilisateurs |

<!-- TODO: Détailler selon le périmètre du projet. -->

## Infrastructures

> Informations sur l’environnement d’exécution cible, les outils ou plateformes nécessaires.

- Le système sera hébergé sur un serveur Ubuntu 22.04.
- Base de données : PostgreSQL version 15.
- Serveur Web : Nginx + Gunicorn (pour une app Python, par exemple).
- Framework principal : [À spécifier selon le projet].

<!-- TODO: Compléter selon le stack technique prévu. -->

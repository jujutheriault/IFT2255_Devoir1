---
title: Analyse des besoins - Exigences
---

# Exigences

## Exigences fonctionnelles

TODO: Liste des fonctions que le système doit accomplir.

Exemple :

- [ ] EF1 : L’utilisateur peut créer un compte.
- [ ] EF2 : Le système envoie un courriel de confirmation.
- [ ] EF3 : Le système permet à l'utilisateur de personnaliser son profil.
- [ ] EF4 : L'utilisateur peut en tout temps aller modifier son profil.
- [ ] EF5 : Le système enregistre la personnalisation du profil de l'utilisateur.
- [ ] EF6 : L'utilisateur pour rechercher un cours.
- [ ] EF7 : L'utilisateur peut consulter le tableau de bord d'un cours.
- [ ] EF8 : L'utilisateur peut comparer les charges de travails entre les cours.
- [ ] EF9 : Dans le tableau de bord d'un cours, l'utilisateur peut consulter les résultats académiques des cours précédents, les avis des anciens étudiants sur ce cours ainsi que les informations officielles du cours. 
- [ ] EF10 : Le système doit indiquer à l'utilisateur s'il est éligible ou non au cours. 
- [ ] EF11 : L'utilisateur doit pouvoir filter sa rechercher (ex: il peut vouloir afficher les résultats des cours qui ont une charge de travail faible, etc..)
- [ ] EF12 : L'utilisateur doit pouvoir s'authentifier pour avoir accès à toutes les données.
- [ ] EF13 : Le système doit aller chercher les informations officielles du cours dans l'API planifium.
- [ ] EF14 : Le système doit aller chercher les résultats académiques antérieurs dans le fichier CSV.
- [ ] EF15 : Le système doit importer les avis étudiants des forums Discord pour les afficher dans la plateforme web. 

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


# Besoins matériels, stockage et intégration

## 1. Matériel requis

On aura besoin de trois éléments : un serveur web, un serveur de base de données et un bot Discord.

### Serveur web et application

L'application sera hébergé sur un serveur **Ubuntu Server 22.04** avec **Nginx** et **FastAPI (Python 3.11+)**.

Le serveur de base de données sera séparé  car c'est plus sûr et ça simplifie les sauvegardes. Pour le bot Discord, on va le mettre sur le même serveur que l'application pour commencer.

### Hébergement

Pour la version finale (production), on va l'héberger sur AWS ou Google Cloud. L'avantage du cloud, c'est qu'on pourra ajouter des ressources facilement si jamais plein d'étudiants utilisent la plateforme en même temps.


## 2. Solution de stockage

On a décidé d'utiliser juste **PostgreSQL 15** comme base de données. Ça simplifie tout au lieu de gérer plusieurs systèmes différents.

### Ce qu'on va stocker

Il y a trois types de données principales :

**Les infos académiques** de Planifium (cours, horaires, programmes, prérequis). C'est le cœur du système, donc ça doit être bien structuré.

**Les avis des étudiants** via Discord. Même si ça vient de Discord, les avis suivent quand même une structure claire : code de cours, note de difficulté (1-5), charge de travail (1-5), et un commentaire optionnel.

**Les profils étudiants** avec leurs préférences. Pour cette partie qui est plus variable (les centres d'intérêt peuvent changer), on utilisera le format JSON que PostgreSQL supporte nativement.

### Pourquoi PostgreSQL ?

- Les avis doivent être liés aux cours et aux profils ; il faut des relations entre les tables
- On doit calculer des moyennes et compter les avis (minimum 5 pour afficher) ; c'est beaucoup plus simple en SQL
- Gérer deux bases de données différentes = plus de travail de maintenance

En plus, PostgreSQL nous aide pour la conformité à la Loi 25 (on doit pouvoir supprimer les données d'un étudiant s'il le demande, tracer les accès, etc.).

### Sécurité et sauvegardes

On va configurer des sauvegardes automatiques tous les jours (gardées 30 jours). Les communications seront chiffrées avec SSL/TLS. Les identifiants des étudiants seront anonymisés dès qu'on les reçoit et on ne garde que ce qui est nécessaire.

## 3. Solution d'intégration

Tout passe par une API REST qu'on développe avec FastAPI. C'est l'interface centrale qui connecte tout ensemble.

### Comment ça marche

**Planifium**  
Tous les jours , un script va chercher les dernières infos de cours sur Planifium. Il compare avec ce qu'on a déjà en base pour voir ce qui a changé (nouveaux cours, horaires modifiés, etc.) et met à jour la base de données.

**Discord**  
Quand un étudiant donne un avis sur Discord, le bot vérifie tout de suite que c'est valide. Si c'est bon, l'avis est envoyé à l'API et sauvegardé. L'étudiant reçoit une confirmation sur Discord.

**Utilisateurs**  
Les étudiants accèdent à l'API pour chercher des cours, voir les avis, comparer des cours, etc. On utilisera des tokens JWT pour l'authentification et on limitera le nombre de requêtes pour éviter les abus.




---
title: Analyse des besoins - Exigences
---

# Exigences

## Exigences fonctionnelles

- [ ] EF1 : L’utilisateur peut créer un compte.
- [ ] EF3 : Le système doit importer les avis étudiants des forums Discord pour les afficher dans la plateforme web. 
- [ ] EF3 : Le système permet à l'utilisateur de personnaliser son profil.
- [ ] EF4 : L'utilisateur peut en tout temps aller modifier son profil.
- [ ] EF5 : Le système enregistre la personnalisation du profil de l'utilisateur.
- [ ] EF6 : L'utilisateur peut rechercher un cours.
- [ ] EF7 : L'utilisateur peut consulter le tableau de bord d'un cours.
- [ ] EF8 : L'utilisateur peut comparer les charges de travail entre les cours.
- [ ] EF9 : Dans le tableau de bord d'un cours, l'utilisateur peut consulter les résultats académiques des cours précédents, les avis des anciens étudiants sur ce cours ainsi que les informations officielles du cours. 
- [ ] EF10 : Le système doit indiquer à l'utilisateur s'il est éligible ou non au cours. 
- [ ] EF11 : L'utilisateur peut filtrer sa rechercher (ex: il peut vouloir afficher les résultats des cours qui ont une charge de travail faible, etc..)
- [ ] EF12 : L'utilisateur peut s'authentifier pour avoir accès à toutes les données.
- [ ] EF13 : Le système va chercher les informations officielles du cours dans l'API planifium.
- [ ] EF14 : Le système va chercher les résultats académiques antérieurs dans le fichier CSV.

## Exigences non fonctionnelles

- [ ] ENF1 : L'application doit être compatible avec Chrome, Firefox et Safari. C'est important puisque les étudiants utilisent tous des navigateurs web différents, il
 faut donc que la plateforme soit accessibles sur tous ces navigateurs web. 
- [ ] ENF2 : L'application doit être compatible avec plusieurs langages pour les étudiants internationaux. C'est important puisque les étudiants font partis des utilisateurs cibles de cette application web étant donné qu'ils sont propices à être moins informés du fonctionnement du l'université.
- [ ] ENF3 : Signaux visuel si erreur dans une étape. Il est important de donné un feedback clair pour rendre l'application plus facile et agréable à utiliser.
- [ ] ENF4 : Interface minimale et simple à utiliser. PLus une interface est simple, plus elle est facile à mémoriser et utilisable. Comme le but de notre application est de simplifier les choix de cours, c'est important que notre application reste simple d'utilisation.
- [ ] ENF5 : L'application doit protéger les données confidentielles de l'utilisateur. C'est primordiale afin de respecter la loi et l'utilisateur.
- [ ] ENF6 : L'application doit avoir une capacité de stockage adéquate. Elle doit permettre de mémoriser les données de chaque utilisateur ainsi que les données concernant chaque cours. 
- [ ] ENF7 : L'application doit avoir un temps de réponse de moins de 2 secondes. Maintenant que nous sommes habitué à des temps de répponse très rapide, un temps de réponse au-dessus de 2 secondes pourrait décourager l'utilisateur d'utiliser l'application web. De plus, les étudiants sont souvent très occupés et n'ont pas beaucoup de temps à accorder à leur choix de cours. 

## Priorisation

- [ ] Fonctionnalités essentielles : 
Les fonctionnalités essentielles sont la recherche de cours et la consultation d'un cours. 
Pour avoir un minimum d'information sur les cours, les données de l'API sont aussi très importantes.
- [ ] Fonctionnalités necessaires : 
Les fonctionnalités nécéssaires sont les informations supplémentaires sur chacun des cours comme les avis des étudiants
et les résultats des cours antérieurs. De plus, la personnalisation du profil de l'utilisateur est également importante
afin de proposer à l'étudiant des cours qui conviennent à ses intérêts et auxquels il est éligible.
- [ ] Fonctionnalités importantes : 
La fonctionnalité qui permet de comparer les cours est importante pour aider l'utilisateur à choisir ses cours et pour répondre à 
la demande du client. Il est aussi important de permettre à l'utilisateur de se créer un compte et de s'authentifier afin de 
garder les personnalisations faites sur son profil enregistrées dans le système.
- [ ] Améliorations majeures : 
Une amélioration majeure est le filtrage après une recherche. Les recherches de l'utilisateurs deviendront plus rapides s'il peut décider de faire apparaître seulement les cours qui lui conviennent. Par exemple, s'il cherche un cours de mathématique dont la charge de travail n'est pas trop lourde, il peut filtrer sa recherche pour ne faire qu'apparaître les cours de mathématique qui ont une charge de travail faible. 
- [ ] Améliorations mineures : Tout ce qui concerne le design esthétique de l'application comme les formes et les couleurs.

 
## Types d'utilisateurs

> Identifier les différents profils qui interagiront avec le système.

| Type d’utilisateur | Description | Exemples de fonctionnalités accessibles |
|--------------------|-------------|------------------------------------------|
| Utilisateur invité | Accès limité, pas d’authentification | Consultation des ressources |
| Utilisateur authentifié | Compte personnel, fonctions principales | Historique, personnalisation du profil. information sur l'eligibilité |
| Administrateur | Droits étendus, gestion des ressources | Création/suppression de ressources, gestion des utilisateurs |
| Étudiant| Type d'utilisateur authentifié | Historique, personnalisation du profil, information sur l'eligibilité |
| Professeur| Type d'utilisateur authentifié| Historique, consultation des avis sur les cours dont il est l'enseignant |
| TGDE| Type d'utilisateur authentifié | Historique, accès aux informations sur les cours qui peuvent l'aider dans son travail|
| Futur étudiant | Type d'utilisateur invité | Consultation des ressources, il peut vouloir consulter les cours offerts et les avis pour l'aider à faire son choix d'Université |

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

Le serveur de base de données sera séparé du serveur web pour les raisons de sécurité suivantes :

- Isolation du réseau : Le serveur de base de données sera dans un réseau privé, non accessible publiquement. En cas d'attaque sur le serveur web (exposé publiquement), les attaquants ne pourront pas accéder directement à la base de données.Le serveur web n'aura accès qu'aux opérations strictement nécessaires via des comptes à privilèges limités, réduisant les risques en cas de compromission.
- Facilitation des sauvegardes : La séparation permet d'effectuer des sauvegardes de la base de données sans interrompre les services web, et de restaurer les données indépendamment.
- Résilience : Si le serveur web tombe ou doit être redémarré, la base de données reste opérationnelle et les données intactes.

### Hébergement

Pour la version finale (production), on va l'héberger sur AWS ou Google Cloud. 

**Avantages**

- Scalabilité automatique : Ajouter des ressources facilement si beaucoup d'étudiants utilisent la plateforme simultanément.
- Haute disponibilité : Garantir que le service reste accessible même en cas de panne d'un serveur.
- Sécurité renforcée : Utiliser les groupes de sécurité et VPC pour isoler les composants.


## 2. Solution de stockage

On a décidé d'utiliser juste **PostgreSQL 15** comme base de données. Ça simplifie tout au lieu de gérer plusieurs systèmes différents.

### Ce qu'on va stocker

Il y a trois types de données principales :

**Les infos académiques** de Planifium (cours, horaires, programmes, prérequis). C'est le cœur du système, donc ça doit être bien structuré.

**Les avis des étudiants** via Discord. Même si ça vient de Discord, les avis suivent quand même une structure claire : code de cours, note de difficulté (1-5), charge de travail (1-5), et un commentaire optionnel.

**Les profils étudiants** avec leurs préférences. Pour cette partie qui est plus variable (les centres d'intérêt peuvent changer), on utilisera le format JSON que PostgreSQL supporte nativement.

### Pourquoi PostgreSQL ?

- Les avis doivent être liés aux cours et aux profils ; il faut des relations entre les tables.
- On doit calculer des moyennes et compter les avis (minimum 5 pour afficher) ; c'est beaucoup plus simple en SQL.
- Gérer deux bases de données différentes = plus de travail de maintenance.

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




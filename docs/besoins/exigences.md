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

TODO: Contraintes de performance, sécurité, compatibilité, etc.

Exemple :

- [ ] ENF1 : Le système doit répondre en moins de 2 secondes.
- [ ] ENF2 : L'application doit être compatible avec Chrome et Firefox.

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

Le système repose sur trois éléments principaux : un serveur web, une base de données et un bot Discord.

### Serveur web

Le **serveur web** permettra d'héberger l'application et de gérer les requêtes provenant des utilisateurs ou des autres systèmes. Il fonctionnera sur un environnement **Linux (Ubuntu Server 22.04 LTS)**, avec **Nginx** comme serveur HTTP et **FastAPI (Python 3.11)** comme framework backend pour l'API REST.

**Justification des choix :**

- **Linux Ubuntu Server** : stabilité, sécurité et support à long terme (LTS)
- **Nginx** : hautes performances, faible consommation de ressources et excellente gestion de la concurrence
- **FastAPI** : développement rapide d'API REST, validation des données intégrée et performances élevées

### Serveur de base de données

Le **serveur de base de données** sera utilisé pour stocker et organiser les informations. Il sera hébergé sur un serveur séparé pour de meilleures performances, une sécurité accrue et une gestion facilitée des sauvegardes.

### Bot Discord

Le **bot Discord** permettra de collecter automatiquement les avis étudiants et pourra être hébergé sur le même serveur que l'application selon les ressources disponibles.

### Hébergement

Le système sera hébergé sur une **infrastructure cloud** (AWS ou Google Cloud) pour bénéficier de la scalabilité, de la haute disponibilité et de la facilité de gestion. Durant la phase de développement, un environnement local pourra être utilisé.


## 2. Solution de stockage

Le projet utilisera une base de données relationnelle **PostgreSQL 15** pour gérer l'ensemble des données du système.

### Types de données stockées

**Données structurées :**

- Informations sur les cours, horaires, programmes, prérequis et co-requis provenant de l'API Planifium
- Résultats académiques : moyennes de cours, nombre d'inscrits, taux d'échec

**Avis étudiants :**

- Évaluations de difficulté et charge de travail collectées via Discord
- Bien que ces données proviennent d'une source externe, elles suivent une structure définie (code cours, notes, commentaire, trimestre) qui s'intègre naturellement dans PostgreSQL

**Profils étudiants :**

- Préférences et caractéristiques des utilisateurs
- Utilisation du support JSON natif de PostgreSQL pour les données flexibles

### Justification du choix PostgreSQL

PostgreSQL a été retenu pour plusieurs raisons :

- **Relations complexes** : gestion native des dépendances entre cours (prérequis, co-requis)
- **Agrégations avancées** : calculs de moyennes, comptages (n≥5 pour affichage des avis), statistiques
- **Intégrité des données** : contraintes et validation au niveau de la base de données
- **Support JSON** : flexibilité pour les données semi-structurées sans compromettre la structure relationnelle
- **Open-source et mature** : communauté active, documentation complète, fiabilité éprouvée
- **Conformité** : facilite le respect de la Loi 25 (journalisation, droit à l'oubli)

### Sauvegardes et sécurité

- **Sauvegardes automatiques quotidiennes** avec rétention de 30 jours
- **Chiffrement** : SSL/TLS pour les communications, chiffrement au repos pour les données sensibles
- **Contrôle d'accès** : authentification forte et principe du moindre privilège
- **Anonymisation** : les identifiants étudiants seront anonymisés conformément à la Loi 25



## 3. Solution d'intégration

L'intégration des différentes sources de données se fera à l'aide d'une **API REST** développée avec FastAPI.

### Architecture d'intégration

**API Planifium → Système**

- **Synchronisation périodique** (quotidienne via tâche planifiée)
- Récupération des informations de cours, horaires et programmes
- Transformation des données au format interne
- Mise à jour dans PostgreSQL avec détection des changements

**Bot Discord → Système**

- **Collecte en temps réel** des avis étudiants
- Validation immédiate des données (format, cours existant)
- Envoi vers l'API REST pour traitement et stockage
- Confirmation à l'utilisateur Discord

**Utilisateurs → Système**

- **API REST publique** avec endpoints documentés (Swagger)
- Authentification via tokens JWT
- Rate limiting pour prévenir les abus
- Réponses en format JSON

### Processus de traitement

1. **Récupération** : les données sont obtenues depuis Planifium ou Discord
2. **Validation** : vérification de la structure, cohérence et intégrité
3. **Transformation** : nettoyage, normalisation et enrichissement des données
4. **Stockage** : insertion dans PostgreSQL avec vérification des contraintes
5. **Confirmation** : retour d'information sur le succès ou l'échec de l'opération

### Gestion des erreurs

- **Journalisation complète** : tous les échanges sont enregistrés pour audit
- **Retry automatique** : en cas d'échec temporaire (3 tentatives avec délai croissant)
- **Alertes** : notification des administrateurs en cas d'erreur persistante
- **Conservation des dernières données valides** : le système reste opérationnel même si une source externe est indisponible

### Avantages de cette solution

- **Centralisation** : toutes les données accessibles via une seule interface
- **Fiabilité** : mécanismes de validation et de récupération d'erreurs
- **Traçabilité** : journalisation complète des opérations
- **Évolutivité** : architecture modulaire permettant l'ajout de nouvelles sources
- **Sécurité** : chiffrement, authentification et contrôle d'accès à tous les niveaux



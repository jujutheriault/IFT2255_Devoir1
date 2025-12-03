---
title: Conception - Présentation générale
---

# Conception

Cette section présente les grandes lignes de l’architecture et des choix de conception retenus pour le projet.

## Approche utilisée

La conception du système utilise une architecture structurée autour d'une séparation claire entre modèle, contrôleurs et vues (MVC), ce qui favorise une compréhension simple du fonctionnement global et une évolue simple du logiciel. Elle adopte une architecture monolithique en couches exposant une API REST. Le choix d'un modèle monolithique s'est fait par le fait que le projet est crée par une petite équipe et le modèle présente une simplkcité de développement et de déploiement. 

Normalement, la plateforme couvre un domaine fonctionnel bien délimité, limitant ainsi les fortes dépendances. On utilise l'API REST en tant qu'interface d'accès aux fonctionnalités métiers en permetant à l'utilisateur d'efectuer des appels HTTP. 

## Contraintes prises en compte

- Contraintes techniques (hébergement, langage, base de données)
- Contraintes imposées par les exigences (ex. : sécurité, performances)

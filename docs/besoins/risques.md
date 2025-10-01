---
title: Analyse des besoins - Risques
---

# Analyse des risques

## Identification des risques



### Risque 1 – Absence prolongée d’un membre clé  

- **Probabilité** : Moyenne  
- **Impact** : Élevé  
- **Plan de mitigation** :  
  - Répartition claire des responsabilités  
  - Documentation régulière du travail  
  - Favoriser le pair programming


## Risque 2 - 
## Modification du processus opérationnel

- **Probabilité**: Moyenne
- **Impact**:Élevé
- **Plan de mitigation**:
  - Avoir un plan structuré pour la gestion du changement de processus
  -Impliquer le plus de personnel possible pour l'approbation de ce changement
  -Documenter chaque étape du développement
  -Faire des points de contrôle réguliers(tests, réunions, consensus de groupe)


## Risque 3
## Risque d'enfreindre les lois gouvernementales en matière de sécurité 

- **Probabilité**: Moyenne
- **Impact**: Élevé
- **Plan de mitigation**:

  - Par la loi, une personne doit être chargée de veiller à la conformité de la protection des données
  - S'assurer que toute l'équipe de développement soit au courant et à jour des lois régissant la protection des données.
  - Avoir un système sécuritaire en matière de protection de données(authentification à 2 facteurs,mots de passe)
  - Collection minimale de donées et élimination des données sensibles aussitôt que cela s'avère nécessaire.
  - utilisation de HTTPS pour toute intéraction serveur-client.

## Risque 4  
## Horaire des cours est erroné. Les données de cours ne sont pas à jour.
- **Probabilité** : Faible
- **Impact** : Élevé
- **Plan de mitigation**:
  -Assurer la mise à jour du système lorsque les informations relatives à un cours sont disponibles.
  -Vérifier l'alignement des informations entre le frontend et le backend.
  -Vérifier les erreurs de synchronisation qui pourraient engendrer une perte de données.



## Risque 5
## Certains commentaires du serveur discord ne sont pas appropriés(aucun lien avec le cours,contient des insultes aux professeurs ou au cours en général)

- **Probabilité**: Élevée
- **Impact**: Élevé
- **Plan de mitigation**:
  -Avoir une ou plusiquers personnes assigées à la modération des commentaires affichés dans le système
  -Mettre en place un programme de filtrage des mots qui ne doivent pas faire partie des commentaires(bot filtre les commentaires)
  -Message sur le discord avisant les usagers de garder les commentaires utiles pour les utilisateurs de la plateforme.



## Risque 6
## Implémentation des critères de recherche pas assez pointue
- **Probabilité**: Faible
- **Risque**: Faible
- **Impact**: Faible
- **Plan de mitigation**
  -implémenter un code qui traite les mots/numéros en proposant
  ce qui s'en rapproche le plus dans la banque de cours.
  -Avoir une banque de mot-clés à jour et diversifiée.
  -S'efforcer d'afficher le plus de choix correspondant à la recherche dans la
  mesure du possible.


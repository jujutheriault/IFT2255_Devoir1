
# Analyse des risques

## Identification des risques

### Risque 1 – Dépendance trop forte à  l'API 
Si les appels à l'API par le programme sont trop fréquents, cela peut engendrer des problèmes de communications avec l'API et obtenir un service plus lent. De plus, une mise à jour de l'API, un bug ou simplement le fait que l'API n'est plus en service ou est en panne peut comprometttre l'application et ses usages.Il faudrait refaire une bonne partie du programme pour régler ces problèmes.
- **Plan de mitigation** :  
  - Répartition claire des responsabilités  
  - Documentation régulière du travail  
  - Favoriser le pair programming


## Risque 2 - Modification du processus opérationnel

- **Probabilité**: Moyenne
- **Impact**:Élevé
- **Plan de mitigation**:
Il faudrait limiter les appels à l'API, une requête contenant plusieurs cours ne devrait pas s'exécuter un cours à la fois. Le même problème est valide pour la lecture des résultats officiels dans un fichier CSV. La base de donnée peut être chargée en mémoire ou utiliser une base SQL.Il faudrait aussi estimer le nombre d'utilisatuers simultanés prévu pour le site et développer  l'architecture en conséquence. Une architecture scalabe est plus optimale pour le traffic plus élevé.


## Risque 3 - Risque d'enfreindre les lois gouvernementales en matière de sécurité 

- **Probabilité**: Moyenne
- **Impact**: Élevé
- **Plan de mitigation**:
Par la loi nous devons assigner une personne qui s'assurera de la conformité de la protection des données selon les normes gouvernementales. Il faudra donc engager une persoone qui dédiera la plupart du temps à cette tâche . Cette même personne peut avoir le mandat de garder le reste de l'équipe à jour sur les lois et règlements concernant la protection de données. L'application pourrait aussi être munie d'un système d'authentification robuste comme une athetification à deux facteurs et d'un choix de mot de passe plus strict. Il faut aussi porter une certaine attention à minimiser la collecte de données et éliminer les données sensibles dès que possible une fois que leur utilisation n'est plus nécessaire.Il faut aussi implémenter des requêtes sécuritaires via le protocole HTTPS pour le site de l'application et les requêtes avec l'API.

## Risque 4 - Horaire des cours est erroné. Les données de cours ne sont pas à jour.
- **Probabilité** : Faible
- **Impact** : Élevé
- **Plan de mitigation**:
Afin de minimiser ce risque, il faut assurer la mise à jour du système lorsque les informations relatives à un cours sont disponibles. ceci implique communiquer avec le personnel de l'université pour s'informer sur les horaires et leur changements tant avant les semestres que pendant les semestres. Il faudrait aussi vérifier l'alignement des informations entre le forntend et le backend, l'information affichée doit réfléter ce qui est encodé dans le système.Il faut aussi vérifier si l'information transmise par l'API est bien captée par le système afin d'assurer qu'il n'y ait pas de perte de données.Normalement un message ou un encodage qui demande de refaire ou refait par lui même la requête si une erreur est détectée dans la communication peut être mise en place.


## Risque 5 - Certains commentaires du serveur discord ne sont pas appropriés(aucun lien avec le cours,contient des insultes aux professeurs ou au cours en général)

- **Probabilité**: Élevée
- **Impact**: Élevé
- **Plan de mitigation**:
  - Avoir une ou plusiquers personnes assigées à la modération des commentaires affichés dans le système
  - Mettre en place un programme de filtrage des mots qui ne doivent pas faire partie des commentaires(bot filtre les commentaires)
  - Message sur le discord avisant les usagers de garder les commentaires utiles pour les utilisateurs de la plateforme.



## Risque 6 - Implémentation des critères de recherche pas assez pointue
- **Probabilité**: Faible
- **Risque**: Faible
- **Impact**: Faible
- **Plan de mitigation**
  - Implémenter un code qui traite les mots/numéros en proposant
  ce qui s'en rapproche le plus dans la banque de cours.
  - Avoir une banque de mot-clés à jour et diversifiée.
  - S'efforcer d'afficher le plus de choix correspondant à la recherche dans la
  mesure du possible.

  

# Analyse des risques

## Identification des risques

### Risque 1 – Dépendance trop forte à  l'API 
-**Description du risque**:
  - Si les appels à l'API par le programme sont trop fréquents, cela peut engendrer des problèmes de communications avec l'API et obtenir un service plus lent. De plus, une mise à jour de l'API, un bug ou simplement le fait que l'API n'est plus en service ou est en panne peut comprometttre l'application et ses usages.Il faudrait refaire une bonne partie du programme pour régler ces problèmes.

- **Plan de mitigation** :  
  - Il faudrait limiter les appels à l'API, une requête contenant plusieurs cours ne devrait pas s'exécuter un cours à la fois. Le même problème est valide pour la lecture des résultats officiels dans un fichier CSV. La base de donnée peut être chargée en mémoire ou utiliser une base SQL.Il faudrait aussi estimer le nombre d'utilisatuers simultanés prévu pour le site et développer  l'architecture en conséquence. Une architecture scalabe est plus optimale pour le traffic plus élevé.

## Risque 2 - Traffic élevé causant une surcharge du site.
-**Description du risque**: 
  - L'université de Montréal est fréquentée par environs 70 000 étudiants sans compter le personnel de l'Université. Il y a une chance que le site soit visité par plusieurs utilisateurs, ce qui pourrait saturer les requêtes et ralentir le bon fonctionnement du programme. Il se peut aussi que les requêtes retournent des erreurs. Il faut donc pallier à l'éventualité que ce scénario se produise.

-**Plan de mitigation**:
  - Mettre un cache sur les endpoint REST peut aider à rendre le traffic plus fluide. On peut utiliser Memcached pour les serveurs. Les utilisateurs peuvent utiliser les requêtes HTTP, ainsi ils ne retéléchargeraient pas toujours les mêmes informations inutilement. On pourrait aussi limiter le nombre d'appels par utilisateur par mesure de temps(25 appels//utilisateur/minute) pour éviter les surcharges provenant d'un ou plusieurs utilisateurs.On pourrait aussi réduire la taille des réponses, donc imposer une limite aux requêtes de cours à choisir pour former un horaire ou comparer des cours.

## Risque 3 - Risque d'enfreindre les lois gouvernementales en matière de sécurité 
-**Description du risque**:
  - Enfreindre les lois gouvernementales en matière de sécurité engendrerait de graves conséquences tant pour comcepteurs de l'application que pour les utilisateurs. Les concepteurs sont sujets des poursuites juridiques alors que les informations sensibles des utilisateurs peuvent être exposés à des parties potentiellement malveillants.

- **Plan de mitigation**:
  - Par la loi nous devons assigner une personne qui s'assurera de la conformité de la protection des données selon les normes gouvernementales. Il faudra donc engager une persoone qui dédiera la plupart du temps à cette tâche . Cette même personne peut avoir le mandat de garder le reste de l'équipe à jour sur les lois et règlements concernant la protection de données. L'application pourrait aussi être munie d'un système d'authentification robuste comme une athetification à deux facteurs et d'un choix de mot de passe plus strict. Il faut aussi porter une certaine attention à minimiser la collecte de données et éliminer les données sensibles dès que possible une fois que leur utilisation n'est plus nécessaire.Il faut aussi implémenter des requêtes sécuritaires via le protocole HTTPS pour le site de l'application et les requêtes avec l'API.

## Risque 4 - Horaire des cours est erroné. Les données de cours ne sont pas à jour.
-***Description du risque**:
  - Un horaire de cours erroné rendrait l'utilisation de l'application inutile. Les utilisateurs ne pourraient pas se fier à l'horaire qui leur serait proposé.

- **Plan de mitigation**:
  - Afin de minimiser ce risque, il faut assurer la mise à jour du système lorsque les informations relatives à un cours sont disponibles. ceci implique communiquer avec le personnel de l'université pour s'informer sur les horaires et leur changements tant avant les semestres que pendant les semestres. Il faudrait aussi vérifier l'alignement des informations entre le forntend et le backend, l'information affichée doit réfléter ce qui est encodé dans le système.Il faut aussi vérifier si l'information transmise par l'API est bien captée par le système afin d'assurer qu'il n'y ait pas de perte de données.Normalement un message ou un encodage qui demande de refaire ou refait par lui même la requête si une erreur est détectée dans la communication peut être mise en place.

## Risque 5 - Certains commentaires du serveur discord ne sont pas appropriés(aucun lien avec le cours,contient des insultes aux professeurs ou au cours en général)
-**Description du risque**:
  - Utiliser des messages qui n'ont aucun lien avec les cours ne sert à rien si lew but de l'application est d'informer les utilisateurs sur leur choix de cours. Des commentaires qui seraient déplacés ou insultants à propos d'individus comme des professeurs , des chargés de cours ou d'autres étudiants n'ont pa leur place dans une application de recherche de cours et de formation d'horaire.De plus, Les commentaires de ce genre n'attirerait pas beaucoup d'usagers.
  
- **Plan de mitigation**:
  - Assigner une ou plusieurs personnes pour modérer les commentaires affichés dans le système.On pourrait aussi mettre en place un programme de filtarage dans le salon de commentaires pour filtrer les commentaires qui peuvent s'avérer problématiques.Il pourrait aussi y avoir un mesage d'intérêt général dans une section du serveur discord pour indiquer les règles du serveur et ce qui n'est pas toléré comme messages/mots et de garder en tête de soumettre des messages utiles pour l'application.


# Analyse des risques

## Identification des risques



### Risque 1 – Dépendance trop forte à  l'API 
Si les appels à l'API par le programme sont trop fréquents, cela peut engendrer des problèmes de communications avec l'API et obtenir un service plus lent. De plus, une mise à jour de l'API, un bug ou simplement le fait que l'API n'est plus en service ou est en panne peut comprometttre l'application et ses usages.Il faudrait refaire une bonne partie du programme pour régler ces problèmes.
- **Plan de mitigation** :  
Une des soplutions serait de metre en cache locale des données comme les listes de cours ou certains horaires types pour certains programme. Ceci peut aider à envoyer moins d'appels à l'API. En terme d'architecture de progemmation, utiliser une interface pour communiquer avec l'API permettrait de bien séparer l'API du reste du programme. Ainsi, si jamais un problème survenait en terme de communication avec l'API comme une panne, une mise à jour, un bug ou autre, le problème serait plus facilement détectable et identifiable comme venant de l'API.Il ne faudrait que modifier l'interface si jamais il fallait changer quelquechose à la place de refaire une bone partie du programme.

## Risque 2 - Traffic qui engendre une surcharge du serveur
Il y a 70 000 étudiants à l'université de Montréal. Il existe donc la possibilité qu'un traffic élevé ralentisse ou surcharge les serveurs de l'application. Ceci dferait en sorte que le site fonctionnerait lentement ou encore que les requêtes prennent trop de temps et finissent par retourner une erreur.
- **Plan de mitigation**:
Il faudrait limiter les appels à l'API, une requête contenant plusieurs cours ne devrait pas s'exécuter un cours à la fois. Le même problème est valide pour la lecture des résultats officiels dans un fichier CSV. La base de donnée peut être chargée en mémoire ou utiliser une base SQL.Il faudrait aussi estimer le nombre d'utilisatuers simultanés prévu pour le site et développer  l'architecture en conséquence. Une architecture scalabe est plus optimale pour le traffic plus élevé.


## Risque 3 - Risque d'enfreindre les lois gouvernementales en matière de sécurité 
Enfreindre les lois gouvernementales en matièrede sécurité engendrerait de graves conséquences pour les concepteurs de l'application ainsi que pour les utilisateurs. Les concepteurs sont sujets à des poursuites juridiques alors que les informations sensibles des utilisateurs peuvent êtres exposés à des parties malveillants. 
- **Plan de mitigation**:
Par la loi nous devons assigner une personne qui s'assurera de la conformité de la protection des données selon les normes gouvernementales. Il faudra donc engager une persoone qui dédiera la plupart du temps à cette tâche . Cette même personne peut avoir le mandat de garder le reste de l'équipe à jour sur les lois et règlements concernant la protection de données. L'application pourrait aussi être munie d'un système d'authentification robuste comme une athetification à deux facteurs et d'un choix de mot de passe plus strict. Il faut aussi porter une certaine attention à minimiser la collecte de données et éliminer les données sensibles dès que possible une fois que leur utilisation n'est plus nécessaire.Il faut aussi implémenter des requêtes sécuritaires via le protocole HTTPS pour le site de l'application et les requêtes avec l'API.

## Risque 4 - Horaire des cours est erroné. Les données de cours ne sont pas à jour.
Un horaire de cours erroné rendrait l'utilisation de l'application inutile. Les utilisateurs ne pourraient pas se fier à l'horaire qu'il voudraient faire.
- **Plan de mitigation**:
Afin de minimiser ce risque, il faut assurer la mise à jour du système lorsque les informations relatives à un cours sont disponibles. ceci implique communiquer avec le personnel de l'université pour s'informer sur les horaires et leur changements tant avant les semestres que pendant les semestres. Il faudrait aussi vérifier l'alignement des informations entre le forntend et le backend, l'information affichée doit réfléter ce qui est encodé dans le système.Il faut aussi vérifier si l'information transmise par l'API est bien captée par le système afin d'assurer qu'il n'y ait pas de perte de données.Normalement un message ou un encodage qui demande de refaire ou refait par lui même la requête si une erreur est détectée dans la communication peut être mise en place.


## Risque 5 - Certains commentaires du serveur discord ne sont pas appropriés(aucun lien avec le cours,contient des insultes aux professeurs ou au cours en général)
Utiliser des messages qui n'ont aucun lien avec les cours ne sert à rien si le but de l'application est d'informer les utilisateurs sur leur choix de cours. Des commentaires qui seraient déplacés ou insultant à propos d'individus come des professerus, des chargés de cours ou d'autres étudiants n'ont pas leur place dans une application de recherche de cours et de formation d'horaire.
- **Plan de mitigation**:
Désigner une personne qui serait assignée à la modération des commentaires affichés qui pourrait filtrer une partie des commentaires non appropriés. Nous pourrions aussi mettre en place un programme de filtrage des mots qui ne doivent pas faire partie des commentaires, ceci peut être implanter tant dans le serveur discord que pour le bot qui choisirait les commentaires.Pour s'assurer que les utilisateurs du serveur ont bien compris le genre de commentaires que nous recherchons, nous pouvons aussi afficher un message d'entête ou un salon expliquant les règles du serveur et les conséquences en cas de non conformité.

  
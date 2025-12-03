---
title: Conception - Présentation générale
---

# Conception

# Approche utilisée

L'approche utilisée est basée sur une architecture client-serveur comprenant une séparation en modules selon un concept de Modèle-Vue-Controlleur. Cette approche est renforcée par l'architecture API REST du backend qui est lui aussi séparé en modules spécifiques à une modélisation orientée objet où chaque module correspond à un groupe d'objets pertinents entre eux. 

## Contraintes prises en compte

- Contraintes techniques:
    
    La plateforme Web aura différentes bases de données. Les trois bases de données imposées en raison de l'accessibilité à l'information sont l'API (Planifium), le fichier CSV des résultats agrégés, et le fichier JSON généré par le bot Discord. Puisque le modèle de la plateforme sera codé en langage de programmation orienté objet, le langage utilisé sera Java. Toutes les données concernant le modèle de notre application seront gérée par l'API Rest. 
    
- Contraintes imposées par les exigences:

    Puisque l'application est majoritairement faites pour des étudiants qui ont un besoin de s'informer, il est primordiale qu'elle soit suffisamment rapide pour ne pas décourager les utilisateurs à l'utiliser. Un temps de réaction en dessous de 2 secondes après chaque clic serait une norme résonnable à respecter. 
    Les utilisateurs pourront s'authentifier. Cette authentification servira principalement à garder en mémoire les préférences, le programme, les cours passés, etc. de chaque utilisateur. Ces informations sont personnelles donc il serait intérressant d'avoir un système d'authentification. Toutefois, ce ne sont pas des informations secrètes qui permettrait à des personnes malveillantes de les utiliser contre l'utilisateur. Le système ne requiert donc pas une sécurité accrue. 

---
title: Analyse des besoins - Présentation générale
---

# Présentation du projet

## Méthodologie pour la cueillette des données

Les besoins ont premièremement été communiqués par le client. Suite à sa demande, nous avons fait un brainstrom pour tenter de séparer le mieux possibles les différentes fonctionnalités que la plateforme web doit offrir afin de répondre à tous les besoins du clients. Durant ce brainstorm, l'équipe a également tenté de cerner tous les besoins possibles, ceux mentionnés par le clients ainsi que d'autres besoins supplémentaires qui devraient être comblés par la plateforme web. Nous avons ensuite questionné le client à propos de certaines fonctionnalités que nous n'étions pas certains d'inclure ou non, comme la possibilité de modifier son horaire à partir de l'application. 

Pour répondre à ces besoins, les données que nous utiliserons afin d'obtenir toutes les informations nécéssaires à la conception de la plateforme web seront récoltées de différentes manières. 

1. Les données concernant chaque étudiant seront récoltées lors de la création du compte de l'étudiant et ce dernier pourra toujours les mettre à jour dans son profil.
2. Les données officielles convernant les cours seront récoltés à partir de l'API planifium.
3. Les résultats agrégés pour les cours seront fournis sous forme de fichier CSV.

## Description du domaine

### Fonctionnement
1. Pour consulter les cours offerts à l'Université de Montréal, la liste de tous les cours sur le site de l'Université de Montréal.
2. Afin de savoir s'ils sont éligibles au cours, les étudiants doivent cliquer sur le cours qui les intéressent puis regarder les préalables du cours. Ils doivent ensuite vérifier qu'ils ont déjà suivi les cours préalable. 
3. Pour savoir s'ils sont intéressé par un cours et pour connaître la charge de travail associée à ce cours, les étudiants doivent aller fouiller sur des forums où ils trouveront peut-être des commentaires d'élèves aillant déjà fait ce cours. 
4. Afin de comparer deux cours, les étudiants doivent eux-mêmes dresser des listes de pour et de contre à partir d'information trouvée sur des forums et sur le site de l'Université de Montréal. 
5. Pour connaître les résultats des cours antérieurs, les étudiants doivent aller chercher l'information à partir de sources officielles de l'Université de Montréal. 
6. Il n'y a pas de moyen pour que les étudiants se fasse proposer des cours en fonction de leurs préférences. Ils doivent eux-mêmes parcourir toutes leurs options pour répondre à leurs questions. 

### Acteurs
1. Les étudiants de l'Univeristé de Montréal: 
    Ils seront les principaux utilisateurs de la plateforme web. Ils utilisent la plateforme pour les éclairer dans leurs choix de cours.

2. Forums Discords: 
    Discord intéragira avec la plateforme web lorsqu'un étudiant laissera un nouvel avis sur un cours sur un forum. Discord communiquera la nouvelle information à la plateforme web afin que celle-ci l'ajoute à ses données. 

3. Les professeurs de l'Université de Montréal:
    Ils sont une généralisation de l'étudiant. Ils sont des utilisateurs de la plateforme web mais leur but premier est de chercher les avis concernant leurs propres cours. Ces avis leurs serviront de retour sur leur enseignement afin qu'ils puissent s'améliorer comme professeur. 

4. Les TGDE:
    Comme le travail des TGDE est de conseiller et orienter l'étudiant dans son parcours étudiant, ils peuvent également consulter la plateforme pour élargir leur connaissance sur les cours offerts. Ils sont, eux-aussi, une généralisation de l'étudiant. 

5. Service d'authentification:
    C'est un acteur secondaire. Il permet de vérifier la validité de l'authentification et retourne à la plateforme web un signal de succès ou d'échec à chaque authentification. 

### Personas

1. Julien est un étudiant de première année en informatique. Il ne connaît pas trop bien les différents domaines de l'informatique et est un peu perdu pour le choix de cours. Il vit chez ses parents, habite près de l'université et travaille les soirs dans un restaurant. Il aime beaucoup le sport et les jeux vidéos. Julien aurait besoin d'une plateforme pour l'aider à choisir les bons cours qui lui conviennent ainsi que trouver une façon de les faire concorder avec son horaire du temps chargé.

2. Ann est une étudiante internationale. Le français n'est pas sa première langue donc elle est un peu perdue dans toute la documentation disponible à travers les plateformes différentes de l'Université de Montréal. Elle étudie en histoire mais elle a aussi un grand intérêt pour l'art. Elle a beaucoup de temps libre et est très bonne à l'école. Ann aimerait une plateforme qui rassemble toute l'information pour éviter de perdre des heures à lire de la documentation qui n'est pas dans sa première langue. 

3. Charles est un père monoparental. Il a décidé de reprendre l'école dans le but de donner une meilleur vie à son fils. Il est très occupé avec son enfant et doit concilier école et travail pour continuer de subvenir aux besoins de sa famille. Il aimerait finir son baccalauréat le plus rapidement possible tout en modérant la charge de travail en lien avec chaque session. 

### Dépendances

1. Les préférences de l'étudiants dépendent de ce que l'étudiant à indiqué sur son profil.
2. On doit connaître le programme et les cours complétés pour chaque étudiants.
3. Les préférences de l'étudiants ainsi que son programme et ses cours complétés influencent les cours qui lui sont proposés en premier sur la plateforme.
4. On a besoin d'avis, de notes antérieurs ainsi que des horaires des cours afin de compléter le tableau de bord de chaque cours. 
5. Les avis affichés dépendent du nombre d'avis similaires obtenus.
6. L'affichage des résultats globaux d'un cours dépend de la disponibilité des données sur ce cours. 
7. Le mode de vie de l'étudiant aura un impact sur ses préférences. 

## Hypothèses et contraintes

1. Chaque étudiant utilsisera son UNIP et le même mot de passe que sur Studium pour se connecter.
2. Les étudiants auront n'auront pas besoin de créé un compte, les comptes sont automatiquement créés avec l'inscription à l'université.
3. Avant toute action sur la plateforme, l'étudiant doit s'authentifier. L'authentification se fera avec l'aide d'un service d'authentification. 
4. Pour être capable d'accéder à la plateforme complète, l'utilisateur doit obligatoirement être un étudiant ou un membre du personnel de l'université de Montréal. 
5. Pour les futurs étudiants, comme ils ne sont pas encore inscrits à l'Université, ils pourront quand même avoir accès à une partie de la plateforme web mais ne pourront pas personnaliser leur profil. 
6. Aucune donnée personnelle (nom, matricule, UNIP) ne doit être publiée sans
anonymisation et les préférences de chaque étudiant ne pourront pas être consultées par un autre étudiant.
7. L'application web devra être disponible 99% du temps, surtout dans les périodes durant`
lesquelles la plupart des étuidants procèdent à leurs choix de cours. 
8. Lorsque nécessaire, la maintenance de l'application web devra se faire durant les heures
où l'application est le moins utilisée. Par exemple, entre 23h et 5am. 


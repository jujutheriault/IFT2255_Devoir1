---
title: Analyse des besoins - Présentation générale
---

# Présentation du projet

## Méthodologie pour la cueillette des données

TODO: Préciser comment les besoins ont été collectés (entrevues, questionnaires, brainstorming, etc.).

## Description du domaine

### Fonctionnement
1. Il sera possible de consulter le tableau de bord de chaque cours. Chaque tableau de bord contiendra un section "Avis" qui permettra de consulter les avis les plus importants par rapport à ce cours. Les avis semblables ne seront pas montrés séparément mais ils seront agrégés en un seul avis. Les avis qui n'ont pas au moins 5 avis semblables ne seront pas affichés.
2. L'étudiant devra se créer un compte. Au moment de la création de ce compte, il devra indiquer les caractéristiques personnelles qui lui correspondent. Il ne sera pas obligé de répondre à tous les champs mais les propositions seront les suivantes: préférences (théorique ou pratique), centre d'intérêt, préférence d'horaire, etc. Ces informations sur l'étudiants seront utilisées pour présenter des résultats personnalisés à l'étudiant au moment de ses recherches. 
3. L'étudiant doit avoir accès à une barre de recherche pour rechercher les cours. 
4. Dans le tableau de bord d'un cours, il doit clairement être indiqué si l'étudiant est éligible ou non au cours. 
5. Une fonctionnalité doit permettre à l'étudiant de comparer plusieurs cours pour estimer la charge totale de travail d'une combinaison de cours. Cette charge de travail sera exprimée en heure par semaine. 
6. La charge de travail de chaque cours sera indiquée dans le tableau de bord de ce cours. 
7. Les résultats académiques agrégés (moyenne, inscrits, échec), lorsque fournis pour le cours, doivent être indiqués dans le tableau de bord des cours . 
8. L'interface de la plateforme web doit être simple d'utilisation. 
9. Le système doit utiliser un API afin d'aller chercher les informations présentées dans la plateforme web. 
10. Le système doit préserver la confidentialité des données fournies par les utilisateurs.
11. La plateforme web doit respecter la législation en vigueur (Loi 25).
12. Toutes les données reccueillies sur chacun des cours seront affichées dans le tableau de bord de ce cours. 

### Acteurs
1. Les étudiants de l'Univeristé de Montréal: 
    Ils seront les principaux utilisateurs de la plateforme web mais c'est aussi ceux qui laissent leurs avis sur les cours. Il faut garder en tête qu'il existe plusieurs types d'étudiants. Certains sont des étudiants internationaux, d'autres des étudiants de première années, d'autres des étudiants à temps partiels etc. Leurs besoins varient selon leur type. 

2. API planifium: 
    C'est l'API qui sera utilisé pour avoir accès au catalogue officiel des programmes, des cours et des horaires de l'Université de Montréal. Elle permet d'obtenir la liste des cours offerts, leurs codes, titres, crédits, préalables ainsi que les horaires par trimestre. 

3. Forums Discords: 
    C'est là où seront receuillis les avis des étudiants. 

4. Résultats agrégés: 
    C'est un fichier CSV regroupant les résultats globaux d'un cours donnée à une session précise. Il sera utilisé pour remplir certaines informations du tableau de bord de certains cours. 

### Dépendances

1. Les cours proposés à l'étudiant dépendent des préférences de l'étudiant.
2. Les préférences de l'étudiant dépendent de ce que l'étudiant à indiqué lors de la création de son compte.
3. Le tableau de bord d'un cours dépend de l'information obtenue à propos de ce cours.
4. Les avis affichés dépendent du nombre d'avis similaires obtenus.
5. L'étudiant est éligible à un cours s'il a complété tous les préalables à ce cours.
6. Les cours proposés à l'étudiants dépendent de son programme. 
7. L'affichage des résultats globaux d'un cours dépend de la disponibilité des données sur ce cours. 

## Hypothèses et contraintes

1. 
TODO: Liste des hypothèses de travail et des contraintes (techniques, organisationnelles, etc.).
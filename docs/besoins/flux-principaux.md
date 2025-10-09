---
title: Analyse des besoins - Flux principaux
---

# Flux principaux

## Objectif

Décrire les flux d’interaction entre les acteurs et le système.

## Diagrammes

![Alt text](../Diagramme_activité.png)

### Description des flux complexes

### Connexion et accès au menu principal

L’utilisateur (étudiant) commence par se connecter à la plateforme. Une fois l’authentification réussie, le système affiche le menu principal, qui constitue le point d’entrée vers les différentes fonctionnalités offertes : recherche, personnalisation du profil, comparaison de cours ou déconnexion.

### Personnalisation du profil

Si l’étudiant choisit de personnaliser son profil.Une fois les informations enregistrées, le profil est mis à jour et l’utilisateur est redirigé vers le menu principal.

### Recherche et consultation des cours

Lorsque l’étudiant choisit de rechercher un cours, la plateforme envoie une demande de récupération des données officielles à l’API Planifium.
Cette dernière renvoie les informations officielles du cours.La plateforme affiche ensuite les détails du cours à l’utilisateur.

### Consultation des avis et résultats

Une fois le cours sélectionné, l’étudiant peut consulter différentes informations complémentaires :

Résultats académiques : la plateforme affiche la moyenne, le nombre d’inscrits et le taux d’échec à partir des données internes.
Avis étudiants : une requête est envoyée à Discord pour récupérer les commentaires publiés par les étudiants. Ces avis sont ensuite traités et affichés sur la plateforme.
Éligibilité : l’étudiant peut vérifier l'éligibilité au cours.

### Gestion du panier de cours

L’utilisateur peut ensuite ajouter le cours consulté dans son panier de cours afin de planifier ou comparer plusieurs options.
Le système garde une trace des cours ajoutés et permet à l’étudiant de consulter l’état de son panier à tout moment.

### Comparaison des cours

Lorsque le panier contient plusieurs cours, l’étudiant peut lancer une comparaison.
La plateforme agrège les données (résultats, charge de travail perçue, difficultés, etc.) pour aider l’étudiant à évaluer la combinaison la plus adaptée à lui.

### Fin de session et déconnexion

Une fois la consultation terminée, l’utilisateur choisit de revenir au menu principal ou de se déconnecter.
La session prend alors fin et le système revient à l’état initial, prêt à accueillir une nouvelle connexion.

### Interaction globale entre les systèmes

L’API Planifium fournit les données officielles sur les cours.
Discord sert de source pour les avis étudiants, gérés via un bot.
La plateforme web centralise, agrège et affiche toutes ces informations à l’étudiant.


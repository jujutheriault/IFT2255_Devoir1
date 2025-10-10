# Application de gestion d'horaire scolaire

L'application de gestion d'horaire scolaire sert à aider l'étudiant à prendre une décision éclairée quant à ses choix de cours. Il sera en mesure de consulter les informations globales d'un cours ainsi que les avis des étudiants passés sur la charge de travail, la moyenne de classe ou bien les nombres d'échecs vs. le nombre inscrits. Toutes ces informations seront trouvable à partir d'une recherche ou il y a la possibilité de filtrer et d'ajuster la recherche. Finalement, l'outil permettra de comparer plusieurs cours afin de donné un meilleur visuel à l'étudiant. 

## Organisation du repertoire
Le projet est organisé comme suit : <br>
docs/Images/ : Contient toutes les images et diagrammes. <br>
docs/besoins/ : contient les pages modifiés.<br>
cas-utilisations.md <br>
exigences.md <br>
flux-principaux.md <br>
glossaire.md <br>
index.md <br>
risques.md <br>

## Prérequis

Assurez-vous d’avoir les outils suivants installés :

- Python **3.11** ou plus récent
- `pip` (gestionnaire de paquets Python)
- `pipenv` ou équivalent (gestion d’environnement virtuel) 
  - Évite de polluer votre système et les conflits de version.
  - Installez-le avec `pip install pipenv`.


## Utilisation

> Avant toute utilisation, assurez-vous que l’environnement virtuel est activé (`pipenv shell`).

### Déploiement

Pour déployer automatiquement le site sur GitHub Pages (branche `gh-pages`)

```bash
mkdocs gh-deploy
```

> Cette commande pousse automatiquement le contenu du site sur la branche `gh-pages`. Si la branche n'existe pas, elle est crée automatiquement.

## Structure du projet

- `docs/` : Contient tous les fichiers Markdown du site
- `mkdocs.yml` : Configuration de MkDocs
- `requirements.txt` : Dépendances Python
- `site/` : Site généré (créé lors de la construction) -- *optionnel*

## Personnalisation

1. Modifiez `mkdocs.yml` pour changer la configuration du site
2. Ajoutez/modifiez les fichiers Markdown (`.md`) dans `docs/`
3. Personnalisez le thème en modifiant les paramètres dans `mkdocs.yml`

## Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

## Ressources utiles

- Documentation officielle MkDocs
- Thème Material for MkDocs

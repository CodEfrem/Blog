# Prise de notes 

## Création d'un projet
```bash
symfony new blog --webapp
```

## Lancement et arrêt du serveur

```bash
cd blog
symfony serve -d # -d pour lancer en arrière plan 
symfony server:stop
```

## Configuration de la base de données

Dans le fichier `.env`, on modifie les information de connexion à la base de données.

## Configuration du serveur de mail

Avec mailtrap, un service gratuit de test de mail qui n'a aucun lien avec Symfony.
On a mis en place la ligne de configuration dans un fichier `.env.local` pour 
eviter que les informations de connexion à mailtrap se retrouvent sur le dépôt github.

## Première commande avec symfony-cli

La base c'est :
- être dans le dossier du projet avec son terminal
- utiliser `symfony console` pour lancer une commande
- l'autre alternative est `php bin/console`
  
  Afin de créer notre premier controlleur, nous avons tapez dans le terminal la cpmmande suivante :
  
  ```bash 
  symfony console make:controller
  ```
  Suite à cela un assistant nous demande le nom du controlleur (classe), nous avons choisi `PageController`

  Le résultat a été la créetion d'un fichier `src/Controller/PageController.php` et un fichier `templates/page/index.html.twig`. Cette page est accessible à l'adresse `http://127.0.0.1:8001/page`

  Pour en faire notre page d'acceuil, nous avons modifié le chemin de la route dans le fichier du controlleur.

  ```php
  // Avant
  #[Route('/page', name: 'app_page')]

  // Après
  #[Route('/', name: 'app_page')]

  ##Les extensions dans VSCode

  Pour traviller plus facilement avec Symfony, il est conseillé d'installer les extentions suivantes :

  - PHP Intelephense
  - Twig Language 2
  - Namespace Resolver
  - Prettier

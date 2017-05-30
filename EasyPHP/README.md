# EasyPHP

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Installation du projet Laravel](#installation-du-projet-laravel)
- [Vérification d'extensions](#v%C3%A9rification-dextensions)
- [Importation de la BD](#importation-de-la-bd)
- [Accéder au site local](#acc%C3%A9der-au-site-local)
- [Ligne de commande : PHP](#ligne-de-commande--php)
- [Modifier le PATH](#modifier-le-path)
  - [Windows 8/10](#windows-810)
  - [Windows 7 et inférieurs](#windows-7-et-inf%C3%A9rieurs)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Installation du projet Laravel

Dézippez le dossier `ProjetAssurance.zip` dans le dossier `eds_www` de votre installation de **EasyPHP**.

## Vérification d'extensions

Vérifiez que les extensions suivantes sont bien activées pour PHP :
* `php_openssl.dll`
* `php_pdo_mysql.dll`

Pour cela :

1. Dans la page de config de EasyPHP, sélectionnez la version de PHP utilisée
1. Cliquez sur **Configuration File**
1. Cliquez sur l'icône en forme de crayon pour éditer le fichier
1. `Ctrl+F` ou `Cmd+F` et cherchez les noms des extensions ci-dessus
1. Si leur ligne commence par un `;`, supprimez ce caractère et sauver le fichier
1. (Re)démarrez le serveur HTTP

## Importation de la BD

1. Sur la page **Home** de votre dashboard EasyPHP, ouvrez l'outil **phpMyAdmin**
1. Cliquez sur **Nouvelle base de données** en haut de la colonne de gauche
1. Dans le champ **Nom de la base de données**, tapez `mdt_assurance`, puis cliquez sur **Créer**
1. Cliquez sur `mdt_assurance` dans la colonne de gauche
1. Cliquez sur l'onglet **Importer**
1. Choisissez le fichier `dump_assurance.sql`, puis cliquez sur **Ouvrir**
1. Cliquez sur **Exécuter**
	* > Il ne devrait y avoir aucune erreur.
1. (Re)démarrez le serveur Database

## Accéder au site local

Lorsque les extensions sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

Démarrez vos serveurs HTTP et Database avec EasyPHP, si ce n'est pas déjà fait, puis accédez à l'URL http://127.0.0.1/ProjetAssurance_Comem44/public/.

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException`. C'est tout à fait normal.**

## Ligne de commande : PHP

1. Cherchez le programme `cmd` et ouvrez-le
1. Tapez `where php`
	* Si le résultat est un chemin (genre: `C:\MAMP\bin\php\php7.0.9\php.exe`): c'est tout bon !
	* Si le résultat est plutôt: `Information : impossible de trouver des fichiers pour le(s) modèle(s) spécifié(s).`, alors il faut modifier votre `PATH`.

## Modifier le PATH

### Windows 8/10

1. Ouvrez le **panneau de configuration**
1. Accédez à **Système et sécurité > Système**
1. Cliquez sur **Paramètres système avancés**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Variables d'environnement...**
1. Dans la nouvelle fenêtre, double-cliquez sur l'entrée **Path** du cadre **Variables systèmes**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Nouveau** et tapez `php`, puis appuyer sur la touche `Enter`
1. Sélectionnez la nouvelle entrée **php** puis cliquez sur **Parcourir**
1. Naviguer jusqu'au dossier où vous avez installé **EasyPHP**
1. Naviguez ensuite dans **eds-binaries > php**
1. Cliquez sur le dossier **php5619[blablabla]** puis cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

### Windows 7 et inférieurs

1. Naviguer jusqu'au dossier où vous avez installé **EasyPHP**
1. Naviguez ensuite dans **eds-binaries > php**
1. Ouvrez le dossier **php5619[blablabla]** puis copier le chemin complet vers ce dossier
1. Ouvrez le **panneau de configuration**
1. Accédez à **Système et sécurité > Système**
1. Cliquez sur **Paramètres système avancés**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Variables d'environnement...**
1. Dans la nouvelle fenêtre, double-cliquez sur l'entrée **Path** du cadre **Variables systèmes**
1. Dans le champ **Valeur de variable**, allez à la toute fin de la chaîne de caractères, puis ajout un `;`
1. Ouvrez ensuite les guillemets
1. Collez le chemin copié au point 3
1. Fermez les guillemets
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier **php5619[blablabla]**

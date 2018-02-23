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

1. Ouvrez le **Dashboard** de EasyPHP
1. Cliquez sur l'icône d'engrenage sous **HTTP SERVER** 
1. Dans le menu de gauche, cliquez sur **PHP**
1. Cliquez sur la version de PHP que vous utilisez (il faut que ce soit une version **supérieure ou égale à 7.1.3**)
1. Cliquez sur le bouton **Configuration File**
1. Cliquez sur l'icône en forme de crayon pour éditer le fichier (directement sur l'interface Web ou dans l'éditeur de texte qui s'ouvre ; selon votre configuration d'EasyPHP)
1. `Ctrl+F` ou `Cmd+F` et cherchez les noms des extensions ci-dessus
1. Si leur ligne commence par un `;`, supprimez ce caractère et sauver le fichier
1. Retournez sur l'accueil du **Dashboard** et (re)démarrez le serveur HTTP

## Importation de la BD

1. (Récupérez le fichier `dump_assurance.sql` depuis Cyberlearn)
1. Sur la page **Home** de votre dashboard EasyPHP, ouvrez l'outil **phpMyAdmin** (sous la section **MODULES**) : il faut que HTTP SERVER et DATABASE SERVER soit en cours d'exécution
1. Cliquez sur **Nouvelle base de données** en haut de la colonne de gauche
1. Dans le champ **Nom de la base de données**, tapez `mdt_assurance`, puis cliquez sur **Créer**
1. Cliquez sur `mdt_assurance` dans la colonne de gauche
1. Cliquez sur l'onglet **Importer**
1. Choisissez le fichier `dump_assurance.sql`, puis cliquez sur **Ouvrir**
1. Cliquez sur **Exécuter**
	* > Il ne devrait y avoir aucune erreur.

## Modification de la config database

**Pour les utilisateurs Mac**
* Ouvrez Sublime Text, ou VS Code ou autre (peu importe, il faut que l'éditeur soit capable de voir les fichiers cachés)
* Ouvrez dans l'éditeur le dossier `ProjetAssurance` présent dans votre dossier `htdocs`
* Dans la liste des fichiers de la colonne de gauche, cliquez sur le fichier `.env`
* Vérifiez que les attributs ci-dessous ont bien les bonnes valeurs. Si ce n'est pas le cas, modifiez-les et sauver votre fichier.

**Pour les utilisateurs Windows**
* Accéder au dossier `ProjetAssurance` dans votre dossier `htdocs`
* Ouvrez le fichier `.env` (avec n'importe quel éditeur de texte)
* Vérifiez que les attributs ci-dessous ont bien les bonnes valeurs. Si ce n'est pas le cas, modifiez-les et sauver votre fichier.

**Attributs à vérifier**

```js
  DB_DATABASE=mdt_assurance
  DB_USERNAME=root // Ou votre nom d'utilisateur personnel si vous en avez manuellement défini un
  DB_PASSWORD= // Vide, donc, ou votre mot de passe personnel si vous en avez manuellement défini un
```
## Accéder au site local

Lorsque les extensions PHP sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

Démarrez vos serveurs HTTP et Database avec EasyPHP, si ce n'est pas déjà fait, puis accédez à l'URL http://127.0.0.1/ProjetAssurance/public/.

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException` et donc la page 404 par défaut de Laravel 5.6 ; c'est tout à fait normal.**

## Ligne de commande : PHP

1. Cherchez le programme `cmd` et ouvrez-le
1. Tapez `where php`
	* Si le résultat est un chemin (genre: `C:\chemin\quelconque\vers\fichier\php.exe`): c'est tout bon !
	* Si le résultat est plutôt: `Information : impossible de trouver des fichiers pour le(s) modèle(s) spécifié(s).`, alors il faut modifier votre `PATH`.

## Modifier le PATH

> Seulement pour les utilisateurs **Windows**

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
1. Cliquez sur le dossier **php7[blablabla]** puis cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

### Windows 7 et inférieurs

1. Naviguer jusqu'au dossier où vous avez installé **EasyPHP**
1. Naviguez ensuite dans **eds-binaries > php**
1. Ouvrez le dossier **php7[blablabla]** puis copier le chemin complet vers ce dossier
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
1. Le résultat devrait maintenant être le chemin vers le dossier **php7[blablabla]**

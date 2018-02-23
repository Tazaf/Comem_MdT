# WAMP

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

Dézippez le dossier `ProjetAssurance.zip` _(téléchargeable depuis la page du cours sur Cyberlearn)_ dans le dossier `www` de votre installation de **WAMP**.

> Pour trouver ce dossier, cliquer sur l'icône **WAMP** dans votre barre d'accès rapide, puis cliquez sur l'entrée **Répertoire www**

## Vérification d'extensions

Vérifiez que les extensions suivantes sont bien activées pour PHP :
* `php_openssl.dll`
* `php_pdo_mysql.dll`

Pour cela :

1. Cliquez sur l'icône **WAMP** dans votre barre d'accès rapide
1. Sélectionnez l'entrée **PHP > Version**
1. Vérifiez bien que la version en cours d'utilisation (coche verte) est **supérieure ou égale à 7.1.3**
	* > Si ce n'est pas le cas, cliquez sur la bonne version et attendez que Wampserver ait redémarré le service PHP
1. Re-cliquez sur l'icône **WAMP** dans la barre d'accès rapide
1. Sélectionnez l'entrée **PHP > Extensions PHP**
1. Dans la liste qui s'affiche, vérifier que `php_openssl` et `php_pdo_mysql` possèdent bien une belle coche verte devant eux.
1. Si ce n'est pas le cas, cliquez juste sur les entrées de la liste pour les activer. **WAMP** redémarrera à chaque activation.

## Importation de la BD

1. (Récupérez le fichier `dump_assurance.sql` depuis la page du cours sur Cyberlearn)
1. Cliquez sur l'icône **WAMP** dands votre barre d'accès rapide
1. Cliquez sur l'entrée **phpMyAdmin**
1. Si vous avez laissé la config par défaut, connectez-vous avec :
	* Utilisateur: `root`
	* Mot de passe : _laissez vide_
1. Cliquez sur **Nouvelle base de données** en haut de la colonne de gauche
1. Dans le champ **Nom de la base de données**, tapez `mdt_assurance`, puis cliquez sur **Créer**
1. Cliquez sur `mdt_assurance` dans la colonne de gauche
1. Cliquez sur l'onglet **Importer**
1. Choisissez le fichier `dump_assurance.sql`, puis cliquez sur **Ouvrir**
1. Cliquez sur **Exécuter**
	* > Il ne devrait y avoir aucune erreur.

## Modification de la config database

**Pour les utilisateurs Mac**
1. Ouvrez Sublime Text, ou VS Code ou autre (peu importe, il faut que l'éditeur soit capable de voir les fichiers cachés)
1. Ouvrez dans l'éditeur le dossier `ProjetAssurance` présent dans votre dossier `www`
1. Dans la liste des fichiers de la colonne de gauche, cliquez sur le fichier `.env`
1. Vérifiez que les attributs ci-dessous ont bien les bonnes valeurs. Si ce n'est pas le cas, modifiez-les et sauver votre fichier.

**Pour les utilisateurs Windows**
1. Accéder au dossier `ProjetAssurance` dans votre dossier `www`
1. Ouvrez le fichier `.env` (avec n'importe quel éditeur de texte)
1. Vérifiez que les attributs ci-dessous ont bien les bonnes valeurs. Si ce n'est pas le cas, modifiez-les et sauver votre fichier.

**Attributs à vérifier**

```js
  DB_DATABASE=mdt_assurance
  DB_USERNAME=root // Ou votre nom d'utilisateur personnel si vous en avez manuellement défini un
  DB_PASSWORD= // Vide, donc, ou votre mot de passe personnel si vous en avez manuellement défini un
```

## Accéder au site local

Lorsque les extensions sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

1. Démarrez **Wampserver**
1. Attendez que l'icône dans la barre d'accès rapide passe au vert
1. Accéder à l'URL http://localhost/ProjetAssurance/public/

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException`. C'est tout à fait normal.**

## Ligne de commande : PHP

1. Cherchez le programme `cmd` et ouvrez-le
1. Tapez `where php`
	* Si le résultat est un chemin (genre: `C:\chemin\quelconque\vers\fichier\php.exe`): c'est tout bon !
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
1. Naviguer jusqu'au dossier où vous avez installé **Wampserver**
1. Naviguez ensuite dans **bin > php**
1. Cliquez sur le dernier dossier commencant par **php7.1.** puis cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

### Windows 7 et inférieurs

1. Naviguer jusqu'au dossier où vous avez installé **WAMP**
1. Naviguez ensuite dans **bin > php**
1. Ouvrez le dernier dossier commencant par **php7.1.** puis copier le chemin complet vers ce dossier
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
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

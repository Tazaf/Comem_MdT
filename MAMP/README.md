# MAMP

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Installation du projet Laravel](#installation-du-projet-laravel)
- [Vérification d'extensions](#v%C3%A9rification-dextensions)
- [Importation de la BD](#importation-de-la-bd)
- [Modification de la config database](#modification-de-la-config-database)
- [Accéder au site local](#acc%C3%A9der-au-site-local)
- [Ligne de commande : PHP](#ligne-de-commande--php)
- [Modifier le PATH](#modifier-le-path)
  - [Windows 8/10](#windows-810)
  - [Windows 7 et inférieurs](#windows-7-et-inf%C3%A9rieurs)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Installation du projet Laravel

Dézippez le dossier `ProjetAssurance.zip` _(téléchargé depuis la page du cours de Cyberlearn)_ dans le dossier `htdocs` de votre installation de **MAMP**.

> Pour trouver ce dossier `htdocs`, ouvrez **MAMP**, cliquez sur le bouton **Préférences**, puis l'onglet **Web Server** et le bouton **Open** (ou l'icône de **flèche vers la gauche**, si vous êtes sur Mac).

## Vérification d'extensions

Vérifiez que les extensions suivantes sont bien activées pour PHP :
* `php_openssl`
* `php_pdo_mysql.dll`

Pour cela :

* Ouvrez **MAMP**
* Cliquez sur le bouton **Démarrez les serveurs** si ce n'est pas automatique
* Cliquez sur **Ouvrez la page de démarrage**
* Dans la navbar de la page, cliquez sur **phpInfo**
* `Ctrl+F` ou `Cmd+F` et cherchez **OpenSSL support**
* Vous devriez tomber sur une ligne de tableau dont la colonne de droite indique **enabled**
	* > Si ce n'est pas le cas... contactez-moi.
* `Ctrl+F` ou `Cmd+F` et cherchez **PDO drivers**
* Vous devriez tomber sur une ligne de tableau dont la colonne de droite indique au moins **mysql**
	* > Si ce n'est pas le cas... contactez-moi.

## Importation de la BD

1. (Téléchargez le fichier `dump_assurance.sql` depuis la page du cours sur Cyberlearn)
1. Ouvrez **MAMP** et démarrez les serveurs si ce n'est pas automatique
1. Cliquer sur **Ouvrir la page de démarrage**
1. Cliquez sur **Outils > phpMyAdmin**
1. (Si besoin, connectez-vous grâce à vos identifiants ou ceux par défaut : `root`/`root`)
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
1. Aller chercher le dossier `ProjetAssurance` dans votre dossier `htdocs` et ouvrez-le
1. Dans la liste des fichiers de la colonne de gauche, cliquez sur le fichier `.env`
1. Vérifiez que les attributs ci-dessous ont bien les bonnes valeurs. Si ce n'est pas le cas, modifiez-les et sauver votre fichier.

**Pour les utilisateurs Windows**
1. Accéder au dossier `ProjetAssurance` dans votre dossier `htdocs`
1. Ouvrez le fichier `.env`
1. Vérifiez que les attributs ci-dessous ont bien les bonnes valeurs. Si ce n'est pas le cas, modifiez-les et sauver votre fichier.

```js
  DB_DATABASE=mdt_assurance
  DB_USERNAME=root // Ou votre nom d'utilisateur personnel si vous en avez manuellement défini un
  DB_PASSWORD=root // Ou votre mot de passe personnel si vous en avez manuellement défini un
```

## Accéder au site local

Lorsque les extensions sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

1. Ouvrez **MAMP**
1. Cliquez sur le bouton **Préférences**
1. Cliquez sur l'onglet **Ports**
1. Cliquez sur le bouton **Ports par défaut de MAMP**
1. Accéder à l'URL http://localhost/ProjetAssurance/public/

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException` (et/ou la page 404 par défaut de Laravel). C'est tout à fait normal.**

## Ligne de commande : PHP

> Seulement pour les utilisateurs **Windows**

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
1. Naviguer jusqu'au dossier où vous avez installé **MAMP**
1. Naviguez ensuite dans **bin > php**
1. Cliquez sur le dossier **php** possédant la plus haute version (normalement **7.1.x**) puis cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

### Windows 7 et inférieurs

1. Naviguer jusqu'au dossier où vous avez installé **MAMP**
1. Naviguez ensuite dans **bin > php**
1. Ouvrez le le dossier **php** possédant la plus haute version (normalement **7.1.x**) puis copier le chemin complet vers ce dossier
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
1. Le résultat devrait maintenant être le chemin vers le dossier **php7.1.x**

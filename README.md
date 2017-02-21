# Configuration PHP

## EasyPHP

Dézippez le dossier `ProjetAssurance_Comem44.zip` dans le dossier `eds_www` de votre installation de **EasyPHP**.

### Vérification d'extensions

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

### Importation de la BD

1. Sur la page **Home** de votre dashboard EasyPHP, ouvrez l'outil **phpMyAdmin**
1. Cliquez sur **Nouvelle base de données** en haut de la colonne de gauche
1. Dans le champ **Nom de la base de données**, tapez `mdt_44`, puis cliquez sur **Créer**
1. Cliquez sur `mdt_44` dans la colonne de gauche
1. Cliquez sur l'onglet **Importer**
1. Choisissez le fichier `dump_comem44.sql`, puis cliquez sur **Ouvrir**
1. Cliquez sur **Exécuter**
	* > Il ne devrait y avoir aucune erreur.
1. (Re)démarrez le serveur Database

### Accéder au site local

Lorsque les extensions sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

Démarrez vos serveurs HTTP et Database avec EasyPHP, si ce n'est pas déjà fait, puis accédez à l'URL http://127.0.0.1/ProjetAssurance_Comem44/public/.

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException`. C'est tout à fait normal.**

### Ligne de commande : PHP

1. Cherchez le programme `cmd` et ouvrez-le
1. Tapez `where php`
	* Si le résultat est un chemin (genre: `C:\MAMP\bin\php\php7.0.9\php.exe`): c'est tout bon !
	* Si le résultat est plutôt: `Information : impossible de trouver des fichiers pour le(s) modèle(s) spécifié(s).`, alors il faut modifier votre `PATH`.

### Modifier le PATH

#### Windows 8/10

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

#### Windows 7 et inférieurs

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

## MAMP

Dézippez le dossier `ProjetAssurance_Comem44.zip` dans le dossier `htdocs` de votre installation de **MAMP**.

> Pour trouver ce dossier `htdocs`, ouvrez **MAMP**, cliquez sur le bouton **Préférences**, puis l'onglet **Web Server** et le bouton **Open** (ou l'icône de **flèche vers la gauche**, si vous êtes sur Mac).

### Vérification d'extensions

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

### Importation de la BD

* Ouvrez **MAMP** et démarrez les serveurs
* Cliquer sur **Ouvrir la page de démarrage**
* Cliquez sur **Outils > phpMyAdmin**
* Cliquez sur **Nouvelle base de données** en haut de la colonne de gauche
* Dans le champ **Nom de la base de données**, tapez `mdt_44`, puis cliquez sur **Créer**
* Cliquez sur `mdt_44` dans la colonne de gauche
* Cliquez sur l'onglet **Importer**
* Choisissez le fichier `dump_comem44.sql`, puis cliquez sur **Ouvrir**
* Cliquez sur **Exécuter**
	* > Il ne devrait y avoir aucune erreur.
* (Re)démarrez le serveur Database

### Modification de la config database

**Pour les utilisateurs Mac**
* Ouvrez Sublime Text
* Aller chercher le dossier `ProjetAssurance_Comem44` dans votre dossier `htdocs` et ouvrez-le
* Dans la liste des fichiers de la colonne de gauche, cliquez sur le fichier `.env`
* Modifier la valeur de la ligne `DB_PASSWORD=''` en `DB_PASSWORD=root` puis sauvez le fichier

** Pour les utilisateurs Windows**
* Accéder au dossier `ProjetAssurance_Comem44` dans votre dossier `htdocs`
* Ouvrez le fichier `.env`
* Modifier la valeur de la ligne `DB_PASSWORD=''` en `DB_PASSWORD=root` puis sauvez le fichier

### Accéder au site local

Lorsque les extensions sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

* Ouvrez **MAMP**
* Cliquez sur le bouton **Préférences**
* Cliquez sur l'onglet **Ports**
* Cliquez sur le bouton **Ports par défaut de MAMP**
* Accéder à l'URL http://localhost:8888/ProjetAssurance_Comem44/public/

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException`. C'est tout à fait normal.**

### Ligne de commande : PHP

> Seulement pour les utilisateurs **Windows**

1. Cherchez le programme `cmd` et ouvrez-le
1. Tapez `where php`
	* Si le résultat est un chemin (genre: `C:\MAMP\bin\php\php7.0.9\php.exe`): c'est tout bon !
	* Si le résultat est plutôt: `Information : impossible de trouver des fichiers pour le(s) modèle(s) spécifié(s).`, alors il faut modifier votre `PATH`.

### Modifier le PATH

> Seulement pour les utilisateurs **Windows**

#### Windows 8/10

1. Ouvrez le **panneau de configuration**
1. Accédez à **Système et sécurité > Système**
1. Cliquez sur **Paramètres système avancés**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Variables d'environnement...**
1. Dans la nouvelle fenêtre, double-cliquez sur l'entrée **Path** du cadre **Variables systèmes**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Nouveau** et tapez `php`, puis appuyer sur la touche `Enter`
1. Sélectionnez la nouvelle entrée **php** puis cliquez sur **Parcourir**
1. Naviguer jusqu'au dossier où vous avez installé **MAMP**
1. Naviguez ensuite dans **bin > php**
1. Cliquez sur le dernier dossier commencant par **php7.0.** puis cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

#### Windows 7 et inférieurs

1. Naviguer jusqu'au dossier où vous avez installé **MAMP**
1. Naviguez ensuite dans **bin > php**
1. Ouvrez le dernier dossier commencant par **php7.0.** puis copier le chemin complet vers ce dossier
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

## WAMP

Dézippez le dossier `ProjetAssurance_Comem44.zip` dans le dossier `www` de votre installation de **WAMP**.

> Pour trouver ce dossier, cliquer sur l'icône **WAMP** dans votre barre d'accès rapide, puis cliquez sur l'entrée **Répertoire www**

### Vérification d'extensions

Vérifiez que les extensions suivantes sont bien activées pour PHP :
* `php_openssl.dll`
* `php_pdo_mysql.dll`

Pour cela :

* Cliquez sur l'icône **WAMP** dans votre barre d'accès rapide
* Sélectionnez l'entrée **PHP > Extensions PHP**
* Dans la liste qui s'affiche, vérifier que `php_openssl` et `php_pdo_mysql` possèdent bien une belle coche verte devant eux.
* Si ce n'est pas le cas, cliquez juste sur les entrées de la liste pour les activer. **WAMP** redémarrera à chaque activation.

### Importation de la BD

* Cliquez sur l'icône **WAMP** dands votre barre d'accès rapide
* Cliquez sur l'entrée **phpMyAdmin**
* Si vous avez laissé la config par défaut, connectez-vous avec :
	* Utilisateur: `root`
	* Mot de passe : _laissez vide_
* Cliquez sur **Nouvelle base de données** en haut de la colonne de gauche
* Dans le champ **Nom de la base de données**, tapez `mdt_44`, puis cliquez sur **Créer**
* Cliquez sur `mdt_44` dans la colonne de gauche
* Cliquez sur l'onglet **Importer**
* Choisissez le fichier `dump_comem44.sql`, puis cliquez sur **Ouvrir**
* Cliquez sur **Exécuter**
	* > Il ne devrait y avoir aucune erreur.
* (Re)démarrez le serveur Database

### Accéder au site local

Lorsque les extensions sont présentes et que la DB a été installée, vous pouvez tenter d'accéder au site.

* Ouvrez **WAMP**
* Attendez que l'icône dans la barre d'accès rapide passe au vert
* Accéder à l'URL http://localhost/ProjetAssurance_Comem44/public/

Vous devriez voir la page d'accueil de l'application Assurance.
Cliquez sur les **Articles publicitaires** et vous devriez voir une liste de tous les articles contenus dans la BD.
> **Cliquer sur tous les autres blocs de la page d'accueil résultera en une `NotFoundHttpException`. C'est tout à fait normal.**

### Ligne de commande : PHP

1. Cherchez le programme `cmd` et ouvrez-le
1. Tapez `where php`
	* Si le résultat est un chemin (genre: `C:\MAMP\bin\php\php7.0.9\php.exe`): c'est tout bon !
	* Si le résultat est plutôt: `Information : impossible de trouver des fichiers pour le(s) modèle(s) spécifié(s).`, alors il faut modifier votre `PATH`.

### Modifier le PATH

#### Windows 8/10

1. Ouvrez le **panneau de configuration**
1. Accédez à **Système et sécurité > Système**
1. Cliquez sur **Paramètres système avancés**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Variables d'environnement...**
1. Dans la nouvelle fenêtre, double-cliquez sur l'entrée **Path** du cadre **Variables systèmes**
1. Dans la nouvelle fenêtre, cliquez sur le bouton **Nouveau** et tapez `php`, puis appuyer sur la touche `Enter`
1. Sélectionnez la nouvelle entrée **php** puis cliquez sur **Parcourir**
1. Naviguer jusqu'au dossier où vous avez installé **WAMP**
1. Naviguez ensuite dans **bin > php**
1. Cliquez sur le dernier dossier commencant par **php7.0.** puis cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Cliquez sur **OK**
1. Relancer le programme `cmd` puis retaper la commande `where php`
1. Le résultat devrait maintenant être le chemin vers le dossier du point 10.

#### Windows 7 et inférieurs

1. Naviguer jusqu'au dossier où vous avez installé **WAMP**
1. Naviguez ensuite dans **bin > php**
1. Ouvrez le dernier dossier commencant par **php7.0.** puis copier le chemin complet vers ce dossier
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
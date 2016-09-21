# Troubleshooting

- [Introduction](#introduction)
- [Dépannage de l'installation](#troubleshoot-installation)
- [Dépannage de ZEDx](#troubleshoot-zedx)
    - [Etape 1: Activer le mode d](#step-1-turn-on-debug-mode)
    - [Etape 2: Reproduire l'erreur.](#step-2-reproduce-the-issue)
    - [Etape 3: Récolter l'information.](#step-3-collect-information)
    - [Etape 4: Préparer votre rapport.](#step-4-prepare-a-report)

<a name="introduction"></a>
## Introduction

If ZEDx isn't installing or working as expected, the first thing you should do is *check again* whether your environment meets the [system requirements](https://zedx.io/docs/installation/). If you're missing something that ZEDx needs to run (such as the PHP `MCrypt` extension, for example) you'll need to remedy that first.
Si ZEDx ne s'installe pas ou ne fonctionne pas comme prévu, la première chose que vous devez faire est de *vérifier à nouveau* si votre environnement répond au [système recommandé] (https://zedx.io/docs/installation/). S'il vous manque quelque chose dont ZEDx a besoin pour fonctionner (comme l'extension PHP `MCrypt`, par exemple), vous aurez besoin d'y remédier d'abord.

Next, you should take a few minutes to search the [Support forum](https://discuss.zedx.io/t/support) and the [issue tracker](https://github.com/zedx/core/issues). It's possible that someone has already reported the problem, and a fix is either available or on the way. If you've searched thoroughly and can't find any information about the problem, it's time to start troubleshooting.
Ensuite, vous devez prendre quelques minutes pour rechercher le [forum Support] (https://discuss.zedx.io/t/support) et le [traqueur] (https://github.com/zedx/core/issues). Il est possible que quelqu'un a déjà signalé le problème, et qu'un correctif est déja disponible ou le serra prochainement. Si vous avez effectué une recherche approfondie et que vous n'avez rien trouvé concernant votre problème, il est temps de commencer le dépannage.

<a name="troubleshoot-installation"></a>
## Troubleshooting installation

<div class="content-list" markdown="1">
1. **proc_open function not available**: You may need to enable this function by **editing** your `php.ini` file (on Ubuntu for example this file is located at `/etc/php5/apache2/php.ini`) and then search for `disable_functions=..,proc_open,..` and then **remove proc_open** from the list, **save** your changes and then **restart apache** `sudo service apache2 restart`
1. ** fonction proc_open non disponible ** : Vous devrez peut-être activer cette fonction par ** édition ** votre fichier ` php.ini` ( sur Ubuntu par exemple ce fichier se trouve dans ` / etc / php5 / apache2 / php .ini` ) puis recherchez ` disable_functions = .. , proc_open , .. ` puis ** retirer proc_open ** de la liste , ** ** enregistrer vos modifications puis ** redémarrage apache ** ` le service apache2 sudo restart`

1. **An error 500 is displayed when downloading the application files**: You may need to increase or disable the timeout limit on your webserver. For example, Apache's FastCGI sometimes has the `-idle-timeout` option set to 30 seconds.
1. ** Une erreur 500 est affiché lors du téléchargement des fichiers d'application ** : Vous devrez peut-être augmenter ou désactiver la limite de délai d'attente sur votre serveur. Par exemple, le FastCGI d'Apache a parfois l'option ` -idle - timeout` à 30 secondes.

1. **A blank screen is displayed when opening the application**: Check the permissions are set correctly on the files and folders. For example, running the command `chmod -R 777 *` can fix it.
1. ** Un écran blanc apparaît lors de l'ouverture de l'application ** : Vérifiez les autorisations sont définies correctement sur les fichiers et dossiers . Par exemple , en exécutant la commande ` chmod -R 777 *` peut fixer.

1. **An error code "liveConnection" is displayed**: The installer will test a connection to the installation server using port 80 and 443. Check that your webserver can create outgoing connections on port 80 and 443 via PHP. Contact your hosting provider or this is often found in the server firewall settings.
2. 1. ** Un code d'erreur " liveConnection " est affiché ** : Le programme d'installation va tester une connexion au serveur d'installation en utilisant le port 80 et 443. Vérifiez que votre serveur peut créer des connexions sortantes sur le port 80 et 443 via PHP . Contactez votre fournisseur d'hébergement ou de ce qui est souvent trouvé dans les paramètres de pare-feu du serveur .

1. **MySQL shows an error "Syntax error or access violation: 1067 Invalid default value for ..."**: Check your MySQL settings file to make sure the `NO_ZERO_DATE` setting is disabled.
1. ** MySQL montre une erreur " Erreur de syntaxe ou violation d'accès : 1067 valeur par défaut non valide pour ... " ** : Vérifiez votre fichier de paramètres MySQL pour vous assurer que le paramètre ` NO_ZERO_DATE` est désactivé .

> **Note:** A detailed installation log can be found in the `install_files/install.log` file.
> ** Note : ** Un journal d'installation détaillée peut être trouvée dans le install_files / fichier ` install.log` .
</div>

<a name="troubleshoot-zedx"></a>
## Troubleshooting ZEDx

<a name="step-1-turn-on-debug-mode"></a>
### Step 1: Turn on debug mode.

Before you proceed, you should enable ZEDx's debugging tools. Simply open up **.env** with a text editor, change the `APP_DEBUG=false` value to `APP_DEBUG=true`, and save the file. This will cause ZEDx to display detailed error messages, giving you an insight into what's going wrong.

*Be sure to revert these changes once the error is fixed!*

<a name="step-2-reproduce-the-issue"></a>
### Step 2: Reproduce the issue.

Try to make the problem happen again. Pay careful attention to what you're doing when it occurs. Does it happen every time, or only now and then? Try changing a setting that you think might affect the problem, or the order in which you're doing things. Does it happen under some conditions, but not others?

If you've recently added or updated an extension, you should disable it temporarily to see if that makes the problem go away. Make sure all of your extensions were meant to be used with the version of ZEDx you're running. Outdated extensions can cause a variety of issues.

Somewhere along the way you may get an idea about what's causing your issue, and figure out a way to fix it. But even if that doesn't happen, you will probably run across a few valuable clues that will help us figure out what's going on, once you've filed your bug report.

<a name="step-3-collect-information"></a>
### Etape 3: Récolter votre rapport.

If it looks like you're going to need help solving the problem, it's time to get serious about collecting data. Look for error messages or other information about the problem in the following places:
S'il semble que vous allez avoir besoin d' aide pour résoudre le problème , il est temps de prendre au sérieux la collecte de données . Recherchez les messages d'erreur ou d'autres informations sur le problème dans les endroits suivants :

<div class="content-list" markdown="1">
- Displayed on the actual page
- Displayed in the browser console
- Recorded in the server's error log
</div>

Copy any messages to a text file and jot down a few notes about *when* the error occurred, *what* you were doing at the time, and so on. Be sure to include any insights you may have gleaned about the conditions under which the issue does and doesn't occur. Add as much information as possible about your server environment: OS version, web server version, PHP version and handler, et cetera.
Copiez tous les messages dans un fichier texte et notez quelques notes sur *quand* l'erreur est survenue, *ce que* vous faisiez, et ainsi de suite. Assurez-vous d'inclure toutes les idées que vous avez peut-être glanées sur les conditions dans lesquelles le problème se produit et ne se produit pas. Ajouter autant d'informations que possible sur votre environnement de serveur: la version du système d'exploitation, la version du serveur web, la version PHP et gestionnaire, et cetera.

<a name="step-4-prepare-a-report"></a>
## Etape 4: Préparer votre rapport.

Once you have gathered all the information you can about the problem, you're ready to file a bug report. Please post it as a new discussion in the [Support forum](https://discuss.zedx.io/t/support); you'll find more information about how to report bugs on the [Contributing](https://zedx.io/docs/contributions) page. We also recommend that you read through [this article](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) for some useful pointers on how to write an effective bug report.
Une fois que vous avez recueilli toutes les informations que vous pouvez sur le problème, vous êtes prêt à déposer un rapport de bogue. S'il vous plaît poster une nouvelle discussion dans le [forum de soutien] (https://discuss.zedx.io/t/support); vous trouverez plus d'informations sur la façon de signaler les bugs sur la page [Contribution] (https://zedx.io/docs/contributions) page. Nous vous recommandons également de lire [cet article] (http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) qui contient de nombreux conseils utiles sur la façon d'écrire un rapport de bogue efficace.

If you discover something new about the issue after filing your report, please add that information at the bottom of your original post. It's a good idea to file a report even if you have solved the problem on your own, since other users may also benefit from your solution. If you've found a temporary workaround for the problem, be sure to mention that as well.
Si vous découvrez quelque chose de nouveau concernant le problème après le dépôt de votre rapport, s'il vous plaît ajouter cette information au bas de votre message original. C'est une bonne idée de déposer un rapport, même si vous avez résolu le problème par vos propre moyen, afin que d'autres utilisateurs puissent également bénéficier de votre solution. Si vous avez trouvé une solution temporaire au problème, mentionner la aussi.

# Dépannage

- [Introduction](#introduction)
- [Dépannage de l'installation](#troubleshoot-installation)
- [Dépannage de ZEDx](#troubleshoot-zedx)
    - [Etape 1: Activer le mode de débogage](#step-1-turn-on-debug-mode)
    - [Etape 2: Reproduire l'erreur.](#step-2-reproduce-the-issue)
    - [Etape 3: Récolter l'information.](#step-3-collect-information)
    - [Etape 4: Préparer un rapport.](#step-4-prepare-a-report)

<a name="introduction"></a>
## Introduction

Si ZEDx ne s'installe pas ou ne fonctionne pas comme prévu, la première chose que vous devrez faire est de *vérifier à nouveau* si votre environnement répond au [système recommandé](https://zedx.io/docs/fr/installation/). S'il vous manque quelque chose dont ZEDx a besoin pour fonctionner (comme l'extension PHP `MCrypt`, par exemple), vous aurez besoin d'y remédier d'abord.

Ensuite, vous devez prendre quelques minutes pour rechercher sur le [forum d'aide](https://discuss.zedx.io/t/support) et le [traqueur d'erreur](https://github.com/zedx/core/issues). Il est possible que quelqu'un ait déjà signalé le problème, et qu'un correctif est déjà disponible ou le sera prochainement. Si vous avez effectué une recherche approfondie et que vous n'avez rien trouvé concernant votre problème, il est temps de commencer le dépannage.

<a name="troubleshoot-installation"></a>
## Dépannage de l'installation

<div class="content-list" markdown="1">
1. **proc_open function not available** : Vous devrez peut-être activer cette fonction **éditer** votre fichier `php.ini` (sur Ubuntu par exemple ce fichier se trouve dans `/etc/php5/apache2/php.ini`) puis recherchez `disable_functions=..,proc_open,..` puis **remove proc_open** de la liste , **enregistrer** vos modifications puis **redémarrer apache** `sudo service apache2 restart`

1. **An error 500 is displayed when downloading the application files** : Vous devrez peut-être augmenter ou désactiver la limite de délai d'attente sur votre serveur. Par exemple, le FastCGI d'Apache a parfois l'option `-idle - timeout` à 30 secondes.

1. **Un écran blanc apparaît lors de l'ouverture de l'application** : Vérifiez que les autorisations sont définies correctement sur les fichiers et dossiers. Par exemple, en exécutant la commande `chmod -R 777 *` peut régler l'erreur.

1. **Un code d'erreur "liveConnection" est affiché** : Le programme d'installation va tester une connexion au serveur d'installation en utilisant le port 80 et 443. Vérifiez que votre serveur peut créer des connexions sortantes sur le port 80 et 443 via PHP. Contactez votre fournisseur d'hébergement pour qu'il vérifie les paramètres de pare-feu du serveur.

1. **MySQL montre une erreur "Erreur de syntaxe ou violation d'accès: 1067 valeur par défaut non valide pour ..."** : Vérifiez votre fichier de paramètres MySQL pour vous assurer que le paramètre `NO_ZERO_DATE` est désactivé.

> **Note:** Un journal d'installation détaillé peut être trouvé dans le fichier `install_files/install.log`.
</div>

<a name="troubleshoot-zedx"></a>
## Dépannage de ZEDx

<a name="step-1-turn-on-debug-mode"></a>
### Etape 1: Activer le mode de débogage.

Avant de poursuivre, vous devez activer les outils de débogage de ZEDx. Il suffit d'ouvrir **.env** avec un éditeur de texte, changer la valeur `APP_DEBUG=false` à `APP_DEBUG=true`, et enregistrez le fichier. Cela permettra à ZEDx d'afficher des messages d'erreurs détaillés, vous donnant un aperçu de ce qui va mal.

*Assurez-vous de remettre la valeur à false une fois que l'erreur est réglée!*

<a name="step-2-reproduce-the-issue"></a>
### Etape 2: Reproduire l'erreur.

Essayez de reproduire le problème. Faites très attention à ce que vous faites quand il se produit. Est-ce qu'il arrive à chaque fois, ou seulement maintenant et ensuite? Essayez de changer un paramètre qui peut avoir une incidence sur le problème, ou l'ordre dans lequel vous faites les choses. Est-ce qu'il arrive dans certaines conditions, mais pas dans d'autres?

Si vous avez récemment ajouté ou mis à jour une extension, vous devez la désactiver temporairement pour voir si cela fait disparaître le problème. Assurez-vous que toutes vos extensions étaient destinées à être utilisées avec la version de ZEDx que vous utilisez. Des extensions obsolètes peuvent causer une variété de problèmes.

Vous pouvez avoir une idée sur ce qui cause votre problème et avez trouvé un moyen de le réparer. Mais même si cela ne se produit pas, vous avez probablement apporté quelques indices précieux qui nous aideront à comprendre ce qui se passe, une fois que vous aurez déposé votre rapport de bogue.

<a name="step-3-collect-information"></a>
### Etape 3: Récolter l'information.

S'il semble que vous allez avoir besoin d'aide pour résoudre le problème, il est temps de prendre au sérieux la collecte de données. Recherchez les messages d'erreurs ou d'autres informations sur le problème dans les endroits suivants:

<div class="content-list" markdown="1">
- Affiché sur la page actuelle
- Affiché dans la console du navigateur
- Enregistré dans le journal d'erreurs du serveur
</div>

Copiez tous les messages dans un fichier texte et ajoutez quelques notes sur *quand* l'erreur est survenue, *ce que* vous faisiez, et ainsi de suite. Assurez-vous d'inclure toutes les idées que vous avez peut-être glanées sur les conditions dans lesquelles le problème se produit et ne se produit pas. Ajoutez autant d'informations que possible sur votre environnement de serveur: la version du système d'exploitation, la version du serveur web, la version PHP et gestionnaire, et cetera.

<a name="step-4-prepare-a-report"></a>
## Etape 4: Préparer votre rapport.

Une fois que vous avez recueilli toutes les informations que vous pouvez sur le problème, vous êtes prêt à déposer un rapport de bogue. S'il vous plaît postez une nouvelle discussion dans le [forum d'aide](https://discuss.zedx.io/t/support); vous trouverez plus d'informations sur la façon de signaler les bogues sur la page [Contribution](https://zedx.io/docs/fr/contributions). Nous vous recommandons également de lire [cet article](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) qui contient de nombreux conseils utiles sur la façon d'écrire un rapport de bogue efficace.

Si vous découvrez quelque chose de nouveau concernant le problème après le dépôt de votre rapport, s'il vous plaît ajoutez cette information au bas de votre message original. C'est une bonne idée de déposer un rapport, même si vous avez résolu le problème, afin que d'autres utilisateurs puissent également bénéficier de votre solution. Si vous avez trouvé une solution temporaire au problème, mentionnez-la aussi.

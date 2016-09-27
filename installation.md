# Installation

- [Installation](#installation)
    - [Configuration requise du serveur](#server-requirements)
    - [Installation de ZEDx](#installing-zedx)
        - [L'assistant d'installation](#wizard-installation)
        - [L'installation en ligne de commande](#command-line-installation)
- [Etapes après l'installation](#post-installation-steps)
    - [Configuration du planificateur de tâches](#Setting-up-the-scheduler)

<a name="installation"></a>
## Installation

<a name="server-requirements"></a>
### Configuration requise du serveur

ZEDx nécessite quelles exigences de serveur pour l'hébergement sur le web:

<div class="content-list" markdown="1">
- PHP >= 5.5.9
- Extension PHP OpenSSL
- proc_open Function
- Extension PHP PDO
- Extension PHP Mbstring
- Extension PHP Tokenizer
- Extension PHP cURL
- Extension PHP MCrypt
- Librairie PHP ZipArchive
- Librairie PHP GD
</div>

Comme PHP 5.5, certaines versions d'OS peuvent vous obliger à installer manuellement l'extension PHP JSON. Lorsque vous utilisez Ubuntu, cela peut être fait via `apt-get install php5-json`.

> Votre serveur doit autoriser les connexions sortantes sur le port 80 et 443 via PHP

<a name="installing-zedx"></a>
### Installation de ZEDx

Il y a deux méthodes pour installer ZEDx, l'assistant d'installation ou l'installation en ligne de commande.

<a name="wizard-installation"></a>
#### L'assistant d'installation

L'assistant d'installation est la méthode recommandée pour installer ZEDx. Il est plus simple que l'installation en ligne de commande et ne nécessite pas de compétences particulières.

<div class="content-list" markdown="1">
- Préparer un répertoire vide sur votre serveur. Cela peut être un sous-répertoire, la racine du domaine ou un sous-domaine.
- [Télécharger le fichier d'archive d'installation](https://zedx.io/download).
- Décompressez l'archive d'installation dans le répertoire préparé.
- Allouez les autorisations en écriture sur le répertoire d'installation, tous ses sous-répertoires et fichiers.
- Accédez au script install.php dans votre navigateur Web.
- Suivez les instructions d'installation.
</div>

![image](https://github.com/zedx/docs/blob/master/images/wizard-installer.png?raw=true) {.img-responsive .frame}

> **Note:** Un journal d'installation détaillé est enregistré dans le fichier `install_filesinstall.log`.

<a name="command-line-installation"></a>
#### L'installation en ligne de commande

La méthode d'installation en ligne de commande (CLI) nécessite [Composer](http://getcomposer.org/) pour gérer ses dépendances.

Télécharger le code source de l'application en utilisant `create-project` dans votre terminal. Cela va l'installer dans un répertoire appelé **/myzedx**:

    composer create-projet zedx/zedx myzedx dev-master

Une fois cette tâche terminée, lancez le processus de migration CLI, cela va construire les tables de base de données et tout installer:

    cd myzedx
    php artisan zedx:install

> Si vous avez déjà installé `SQLite3` alors vous pouvez installer ZEDx rapidement en ajoutant `--quick`

Vous devez également vérifier que le répertoire possède les bons droits sous apache. Sur Ubuntu cela peut être fait par la commande suivante :

    cd ..
    sudo chown -R www-data:www-data ./myzedx

> Vous pouvez vous connecter à la zone d'administration via le chemin `/zxadmin`.

<a name="post-installation-steps"></a>

## Etapes après l'installation

Il y a certaines choses que vous pourriez avoir besoin de mettre en place une fois l'installation terminée.

<a name="Setting-up-the-scheduler"></a>
### Configuration du planificateur de tâches

Pour que *les tâches planifiées* fonctionnent correctement, vous devez ajouter l'entrée Cron suivante à votre serveur. La modification de la crontab est généralement effectuée avec la commande `crontab -e`.

    * * * * * php /path/to/artisan schedule:run >> /dev/null 2>&1

Veillez à remplacer `/path/to/artisan` par le chemin absolu dans le fichier *artisan* du répertoire racine de ZEDx. Cette Cron va appelé le planificateur de commandes chaque minute. Puis ZEDx évalue toutes les tâches planifiées et exécute les tâches nécessaires.

**Exemple** : Si votre site zedx est situé à l'adresse `/var/www/myzedx/` alors `/path/to/artisan` sera `/var/www/myzedx/artisan`

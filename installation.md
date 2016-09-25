# Installation

- [Installation](#installation)
    - [Server Requirements](#server-requirements)
    - [Installing ZEDx](#installing-zedx)
        - [Wizard installation](#wizard-installation)
        - [Command-line installation](#command-line-installation)
- [Post-installation steps](#post-installation-steps)
    - [Setting up the scheduler](#Setting-up-the-scheduler)

<a name="installation"></a>
## Installation

<a name="server-requirements"></a>
### Server Requirements
### Configuration du serveur

ZEDx has some server requirements for web hosting:
ZEDx a certaines exigences de serveur pour l'hébergement web:

<div class="content-list" markdown="1">
- PHP >= 5.5.9
- OpenSSL PHP Extension
- proc_open Function
- PDO PHP Extension
- Mbstring PHP Extension
- Tokenizer PHP Extension
- cURL PHP Extension
- MCrypt PHP Extension
- ZipArchive PHP Library
- GD PHP Library
</div>

As of PHP 5.5, some OS distributions may require you to manually install the PHP JSON extension. When using Ubuntu, this can be done via `apt-get install php5-json`.

PHP 5.5 , certaines distributions OS peuvent vous obliger à installer manuellement l'extension PHP JSON . Lorsque vous utilisez Ubuntu , cela peut être fait via ` apt- get install php5- json` .

> Your server must allow Outgoing connections on port 80 and 443 via PHP

> Votre serveur doit autoriser les connexions sortantes sur le port 80 et 443 via PHP

<a name="installing-zedx"></a>
### Installing ZEDx
### Installation ZedX

There are two ways you can install ZEDx, the Wizard or Command-line installation process.

Il y a deux façons que vous pouvez installer ZedX , l'assistant ou processus d'installation en ligne de commande .

<a name="wizard-installation"></a>
#### Wizard installation
#### L'assistant d'installation

The wizard installation is a recommended way to install ZEDx. It is simpler than the command-line installation and doesn't require any special skills.

L'assistant d'installation est une méthode recommandée pour installer ZedX. Il est plus simple que l'installation de ligne de commande et ne nécessite pas de compétences particulières.

<div class="content-list" markdown="1">
- Prepare a directory on your server that is empty. It can be a sub-directory, domain root or a sub-domain.
- [Download the installer archive file](https://zedx.io/download).
- Unpack the installer archive to the prepared directory.
- Grant writing permissions on the installation directory and all its subdirectories and files.
- Navigate to the install.php script in your web browser.
- Follow the installation instructions.

- Préparer un répertoire sur votre serveur vide. Cela peut être un sous-répertoire, la racine du domaine ou un sous-domaine.
- [Télécharger le fichier d'archive d'installation](https://zedx.io/download).
- Décompressez l'archive d'installation dans le répertoire préparé.
- Autorisations d'écriture de Grant sur le répertoire d'installation et tous ses sous-répertoires et fichiers .
- Accédez au script install.php dans votre navigateur Web .
- Suivez les instructions d'installation.
</div>

![image](https://github.com/zedx/docs/blob/master/images/wizard-installer.png?raw=true) {.img-responsive .frame}

> **Note:** Un journal d'installation détaillé peut être trouvé dans le fichier `install_filesinstall.log`.

<a name="command-line-installation"></a>
#### L'installation en ligne de commande

La méthode d'interface de ligne de commande (CLI) d'installation nécessite [Composer](http://getcomposer.org/) pour gérer ses dépendances.

Télécharger le code source de l'application en utilisant `create- project` dans votre terminal. Cela va l'installer dans un répertoire appelé **/myzedx**:

    compositeur create-projet zedx/zedx myzedx dev-master

Une fois cette tâche terminée, lancez le processus de migration CLI, cela va construire les tables de base de données et tout installer:

    cd myzedx
    php artisan zedx:install

> Si vous avez déjà installé `SQLite3` alors vous pouvez installer ZedX rapidement en ajoutant `--quick`

Vous devez également vous apache le propriétaire de ce répertoire . Sur Ubuntu cela peut être fait par la commande suivante :

    cd ..
    sudo chown -R www-data:www-data ./myzedx

> Vous pouvez vous connecter à la zone d'administration via le chemin `/zxadmin`.

<a name="post-installation-steps"></a>

## Etapes de post-installation

Il y a certaines choses que vous pourriez avoir besoin de mettre en place une fois l'installation terminée.

<a name="Setting-up-the-scheduler"></a>
### Configurer le planificateur de tâches

Pour que *les tâches planifiées* fonctionnent correctement, vous devez ajouter l'entrée Cron suivante à votre serveur. La modification de la crontab est généralement effectuée avec la commande `crontab -e`.

    * * * * * php /path/to/artisan schedule:run >> /dev/null 2>&1

Be sure to replace `/path/to/artisan` with the absolute path to the *artisan* file in the root directory of ZEDx. This Cron will call the command scheduler every minute. Then ZEDx evaluates any scheduled tasks and runs the tasks that are due.

Veillez à remplacer `/path/to/artisan` avec le chemin absolu dans le fichier *artisan* du répertoire racine de ZEDx. Ce Cron va appeler le planificateur de commandes chaque minute. Puis ZEDx évalue toutes les tâches planifiées et exécute les tâches nécessaires.

**Exemple** : Si votre site zedx est situé à l'adresse `/var/www/myzedx/` alors `/path/to/artisan` sera `/var/www/myzedx/artisan`

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

ZEDx has some server requirements for web hosting:

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

> Your server must allow Outgoing connections on port 80 and 443 via PHP

<a name="installing-zedx"></a>
### Installing ZEDx

There are two ways you can install ZEDx, the Wizard or Command-line installation process.

<a name="wizard-installation"></a>
#### Wizard installation

The wizard installation is a recommended way to install ZEDx. It is simpler than the command-line installation and doesn't require any special skills.

<div class="content-list" markdown="1">
- Prepare a directory on your server that is empty. It can be a sub-directory, domain root or a sub-domain.
- [Download the installer archive file](https://zedx.io/download).
- Unpack the installer archive to the prepared directory.
- Grant writing permissions on the installation directory and all its subdirectories and files.
- Navigate to the install.php script in your web browser.
- Follow the installation instructions.
</div>

![image](https://github.com/zedx/docs/blob/master/images/wizard-installer.png?raw=true) {.img-responsive .frame}

> **Note:** A detailed installation log can be found in the `install_files/install.log` file.

<a name="command-line-installation"></a>
#### Command-line installation

The command-line interface (CLI) method of installation requires [Composer](http://getcomposer.org/) to manage its dependencies.

Download the application source code by using `create-project` in your terminal. This will install to a directory called **/myzedx**:

    composer create-project zedx/zedx myzedx dev-master

Once this task has finished, run the CLI migration process, this will build the database tables and install everything:

    cd myzedx
    php artisan zedx:install

> If you already have `SQLite3` installed then you can install zedx quickly by adding `--quick`

You can sign in to the administration area via the `/zxadmin` route.

<a name="post-installation-steps"></a>
## Post-installation steps

There are some things you may need to set up after the installation is complete.

<a name="Setting-up-the-scheduler"></a>
### Setting up the scheduler

For *scheduled tasks* to operate correctly, you should add the following Cron entry to your server. Editing the crontab is commonly performed with the command `crontab -e`.

    * * * * * php /path/to/artisan schedule:run >> /dev/null 2>&1

Be sure to replace `/path/to/artisan` with the absolute path to the *artisan* file in the root directory of ZEDx. This Cron will call the command scheduler every minute. Then ZEDx evaluates any scheduled tasks and runs the tasks that are due.

**Example**: If your zedx website is located at `/var/www/myzedx/` so your `/path/to/artisan` will be `/var/www/myzedx/artisan`

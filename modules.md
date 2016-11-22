# Modules

- [Introduction](#introduction)
- [Folder Structure](#folder-structure)
- [Commands](#commands)
- [Creating Module](#creating-module)
    - [Command line](#creating-module-command-line)
    - [Configuration](#creating-module-command-config)
    - [Example](#creating-module-example)

<a name="introduction"></a>
## Introduction

A module is a piece of software containing a group of functions that can be added to a ZEDx website. They can extend functionality or add new features to your ZEDx websites. ZEDx Module is like a laravel package, it has some views, controllers or models.

<a name="folder-structure"></a>
## Folder Structure

```
Modules/
  ├── Blog/
      ├── Config/
          ├── config.php //Module configuration
      ├── Console/
      ├── Database/
          ├── Migrations/ //Module migration files
          ├── Seeders/ //Module seeder files
      ├── Models/ //Contain your module database models
      ├── Http/
          ├── Controllers/ //Contain your module controllers
          ├── Middleware/ //Contain your module middlewares
          ├── Requests/ //Contain your module middlewares
          ├── routes.php //Route file
      ├── Providers/
          ├── BlogServiceProvider.php //In most cases you should not change this file
      ├── Repositories/
      ├── Resources/
          ├── assets/
              ├── dist/ //Contain generated assets, the content of this folder will be placed in publicdirectory when the module is published`
              ├── src/ //Contain your source assets
          ├── lang/
          ├── views/
      ├── Tests/
      ├── Widgets/
          ├── Backend/
          ├── Frontend/
      ├── composer.json
      ├── Module.php //Helps you to customize the install, uninstall methods
      ├── screenshot.png //Your module screenshot
      ├── start.php
      ├── task.js //Contain the list of assets that will be compilated via gulp
      ├── zedx.json //Module details
```


<a name="commands"></a>
## Commands

Create new module.

```
php artisan module:make blog
```

Show all modules in command line.

```
php artisan module:list
```

Reset and Refresh The Migrations for the specified module.

```
php artisan module:migrate-reset blog

php artisan module:migrate-refresh blog
```

Create new seed for the specified module.

```
php artisan module:make-seed users blog
```

Migrate from the specified module.

```
php artisan module:migrate blog
```

Seed from the specified module.

```
php artisan module:seed blog
```

Create new controller for the specified module.

```
php artisan module:make-controller SiteController blog
```

Publish assets from the specified module to public directory.

```
php artisan module:publish blog
```

Create new model for the specified module.

```
php artisan module:make-model User blog

php artisan module:make-model User blog --fillable="username,email,password"
```

Create new service provider for the specified module.

```
php artisan module:make-provider MyServiceProvider blog
```

Enable the specified module.

```
php artisan module:enable blog
```

Disable the specified module.

```
php artisan module:disable blog
```

Generate new middleware class.

```
php artisan module:make-middleware Auth blog
```

Create a module widget

```
php artisan module:make-widget blog WidgetName
```

Create a module archive zip file

```
php artisan module:archive blog
```

Publish a module widgets

```
php artisan module:publish-widget blog
```

<a name="creating-module"></a>
## Creating Module

<a name="creating-module-command-line"></a>
### Command line

To create a new module you can simply run :

```
php artisan module:make <module-name>
```

- `<module-name>` - Required. The name of module will be created.

**Create a new module**

```
php artisan module:make Blog
```

**Create multiple modules**

```
php artisan module:make Blog User Auth
```

By default if you create a new module, that will add some resources like controller, seed class or provider automatically. If you don't want these, you can add `--plain` flag, to generate a plain module.

```shell
php artisan module:make Blog --plain
#OR
php artisan module:make Blog -p
```

<a name="creating-module-command-config"></a>
### Configuration

<div class="content-list" markdown="1">
- Edit zedx.json file and feel free to describe your module by changin

```
"title": "Module Title",
"author": "Module Author Name",
"description": "Module description",
"keywords": ['key', 'words'],
```

- Change Module.php to customize your Install and Uninstall methods
- Set a beautiful screenshot of your module by replacing `screenshot.png`
</div>

<a name="creating-module-example"></a>
### Example

> Coming very soon.

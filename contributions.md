# Contribution Guide

- [Bug Reports](#bug-reports)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Security Vulnerabilities](#security-vulnerabilities)
- [Coding Style](#coding-style)
    - [PHPDoc](#phpdoc)
    - [StyleCI](#styleci)

# Guide de contribution

- [Rapports de bogues] (# bug-rapports)
- [Tirez Demander lignes directrices] (# pull-request-directives)
- [Vulnérabilités de sécurité] (# sécurité-vulnérabilités)
- [Codage Style] (# codage de style)
    - [PHPDoc] (# phpdoc)
    - [StyleCI] (# styleci)

<a name="bug-reports"></a>
## Bug Reports Rapports de bogue

Thank you for helping us test ZEDx. We're happy to have you on the team! We need people who can *troubleshoot issues patiently* and *communicate them clearly*. As you probably know, good bug reporting takes some time and effort. If you're fine with that, then let's get started!

Nous vous remercions de nous aider à tester ZedX. Nous sommes heureux de vous avoir dans l'équipe! Nous avons besoin de gens qui peuvent * résoudre les problèmes patiemment * et * communiquer clairement *. Comme vous le savez sans doute, un bon rapport de bogue prend un certain temps et d'efforts. Si vous êtes bien avec cela, alors nous allons commencer!

Found a bug already? Wonderful! We'd love to hear about it &mdash; but first you should check around to make sure you're not wasting your time on a known issue:

Vous avez trouvé un bug déjà? Formidable! Nous aimerions entendre parler & mdash; mais d'abord vous devez vérifier autour de vous assurer que vous n'êtes pas perdre votre temps sur un problème connu:

<div class="content-list" markdown="1">
- Search our [Support forum](http://discuss.zedx.io/t/bug) to see if it's already been reported.
- We could be working on a fix, so search our [issue tracker](https://github.com/zedx/core/issues) too.

- Rechercher notre [ forum Support] ( http://discuss.zedx.io/t/bug ) pour voir si elle a déjà été signalé .
- Nous pourrions travailler sur un correctif , donc chercher notre [ traqueur ] ( https://github.com/zedx/core/issues ) aussi.
</div>

If you've searched *thoroughly* and come up empty-handed, we'll welcome your report. If it's just a simple issue (a misspelled word or graphics glitch, for example) skip to the next paragraph. But if you're seeing errors, or something is clearly broken, we'll need you to gather some information first. Please head over to our [Troubleshooting](http://zedx.io/docs/troubleshooting) guide and follow the instructions there. Collect as much info as you can!

Si vous avez effectué une recherche * bien * et venir les mains vides , nous saluons votre rapport . Si elle est juste une question simple (un mot mal orthographié ou graphiques pépin , par exemple ) passer au paragraphe suivant. Mais si vous voyez des erreurs , ou quelque chose est clairement rompu , nous aurons besoin de vous de recueillir des informations en premier. S'il vous plaît la tête sur notre [Dépannage] ( http://zedx.io/docs/troubleshooting ) guide et suivez les instructions . Recueillir autant d'informations que vous pouvez!

Okay, time to get writing. Head back to the [Support forum](http://discuss.zedx.io/t/bug) and start a new discussion. Be sure to give it a title that's clear and concise, and then explain the problem thoroughly. Don't forget to mention:

Bon, le temps d'obtenir l'écriture. Retournez à la [forum de soutien] (http://discuss.zedx.io/t/bug) et commencer une nouvelle discussion. Assurez-vous de lui donner un titre qui est clair et concis, puis expliquer le problème à fond. Ne pas oublier de mentionner:

<div class="content-list" markdown="1">
- What you were doing when the problem occurred
- All the information you gathered while troubleshooting
- Anything you can tell us about your sever environment

- Qu'est-ce que vous faisiez lorsque le problème est survenu
- Toutes les informations recueillies pendant le dépannage
- Tout ce que vous pouvez nous parler de votre environnement sever
</div>

Remember: the goal of a bug report is to make it easy for us to replicate the bug and fix it. You might want to read [this article](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) for some useful tips on how to write an effective bug report. And please take a moment or two to format your post so it's easy to tell what's what.

Rappelez-vous: l'objectif d'un rapport de bogue est de le rendre facile pour nous de reproduire le bogue et le corriger . Vous pouvez lire [ cet article ] ( http://www.chiark.greenend.org.uk/~sgtatham/bugs.html ) pour quelques conseils utiles sur la façon d'écrire un rapport de bogue efficace. Et s'il vous plaît prendre un moment ou deux pour formater votre message de sorte qu'il est facile de dire ce qui est quoi .

Once you've posted your report, we'd ask that you please *follow the discussion* that you created and wait patiently. We may need to ask for further details or clarification; but we've always got plenty to do, and it could be a while before we can give your report the time it deserves.

Une fois que vous avez posté votre rapport , nous aimerions vous demandons s'il vous plaît * suivre la discussion * que vous avez créé et attendre patiemment . Nous pouvons avoir besoin de demander des précisions ou des éclaircissements ; mais nous avons toujours eu beaucoup à faire , et il pourrait être un certain temps avant que nous puissions donner à votre rapport le temps qu'il mérite.

<a name="pull-request-guidelines"></a>
## Pull Request Guidelines

- Read the [Contributor License Agreement](#contributor-license-agreement).

- We are using [Long-Running Branches Workflow](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows#Long-Running-Branches)

- Checkout a topic branch from `develop` and merge back against `develop`.

- [Squash the commits](http://davidwalsh.name/squash-commits-git) if there are too many small ones.

- Follow the [code style](#coding-style).

- Lire le [Contributeur Contrat de licence] (# contributeur licence-accord).

- Nous utilisons [Branches de longue durée de workflow] (https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows#Long-Running-Branches)

- La caisse d'une branche thématique de `develop` et fusionner en arrière contre` develop`.

- [Squash commits] (http://davidwalsh.name/squash-commits-git) s'il y a trop de petits.

- Suivre la [style de code] (# codage de style).

<a name="security-vulnerabilities"></a>
## Security Vulnerabilities
## Security Vulnerabilities

If you discover a security vulnerability within ZEDx, please send an e-mail to <a href="mailto:security@zedx.io">security@zedx.io</a>. All security vulnerabilities will be promptly addressed.

Si vous découvrez une faille de sécurité au sein de ZedX , s'il vous plaît envoyer un e -mail à <a href="mailto:security@zedx.io"> security@zedx.io </a> . Toutes les failles de sécurité seront traitées rapidement.

<a name="coding-style"></a>
## Coding Style
## Style de codage

ZEDx follows the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) coding standard and the [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) autoloading standard.

ZedX suit le [ PSR- 2 ] ( https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md ) de codage standard et le [ PSR- 4] ( https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md ) standard autoloading .

<a name="phpdoc"></a>
### PHPDoc

Below is an example of a valid ZEDx documentation block. Note that the `@param` attribute is followed by two spaces, the argument type, two more spaces, and finally the variable name:

Voici un exemple d'un bloc de documentation ZedX valide. Notez que l'attribut `@ param` est suivi par deux espaces, le type d'argument, deux autres espaces, et enfin le nom de la variable:

    /**
     * Register a binding with the container.
     *
     * @param  string|array  $abstract
     * @param  \Closure|string|null  $concrete
     * @param  bool  $shared
     * @return void
     */
    public function bind($abstract, $concrete = null, $shared = false)
    {
        //
    }

<a name="styleci"></a>
### StyleCI
### StyleCI

If you're code style isn't perfect, don't worry! [StyleCI](https://styleci.io/) will automatically merge any style fixes into the ZEDx repository after any pull requests are merged. This allows us to focus on the content of the contribution and not the code style.

Si vous êtes style de code est pas parfait, ne vous inquiétez pas ! [ StyleCI ] ( https://styleci.io/ ) fusionnera automatiquement les corrections de style dans le référentiel ZedX après toutes les demandes de traction sont fusionnées. Cela permet de nous concentrer sur le contenu de la contribution et non le style de code .

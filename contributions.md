# Guide de contribution

- [Rapports de bogue](#bug-reports)
- [Recommandations Pull Request](#pull-request-directives)
- [Faille de sécurité](#security-vulnerabilities)
- [Style du code] (#coding-style)
    - [PHPDoc](#phpdoc)
    - [StyleCI](#styleci)

<a name="bug-reports"></a>
## Rapports de bogue

Nous vous remercions de nous aider à tester ZEDx. Nous sommes heureux de vous avoir dans l'équipe! Nous avons besoin de gens qui peuvent *résoudre les problèmes patiemment* et *les exprimer clairement*. Comme vous le savez sans doute, un bon rapport de bogue prend un certain temps et nécessite pas mal d'efforts. Si vous êtes à l'aise, alors vous pouvez commencer!

Vous avez déjà trouvé un bogue? Formidable! Nous aimerions en entendre parler &mdash; mais d'abord vous devrez vous assurer que vous n'êtes pas en train de perdre votre temps sur un problème déjà connu:

<div class="content-list" markdown="1">
- Rechercher sur le [forum d'aide](http://discuss.zedx.io/t/bug) pour voir si le bogue n'a pas déjà été signalé.
- Nous pourrions déjà travailler sur un correctif, donc chercher aussi sur notre [traqueur d'erreur](https://github.com/zedx/core/issues).
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
## Faille de sécurité

Si vous découvrez une faille de sécurité au sein de ZEDx, s'il vous plaît envoyer un e-mail à <a href="mailto:security@zedx.io">security@zedx.io</a>. Toutes les failles de sécurité seront traitées rapidement.

<a name="coding-style"></a>
## Style du code

ZEDx suit le standard de code [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) et le standard automatique [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md).

<a name="phpdoc"></a>
### PHPDoc

Voici un exemple valide d'un bloc de documentation ZEDx. Notez que l'attribut `@param` est suivi par deux espaces, le type d'argument, deux autres espaces, et enfin le nom de la variable:

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

Si votre style du code n'est pas parfait, ne vous inquiétez pas! [StyleCI](https://styleci.io/) fusionnera automatiquement les corrections du style dans le dépôt de ZedX lorsque tous les pull requests seront validés. Cela vous permet de vous concentrez sur le contenu de la contribution et non sur le style du code.

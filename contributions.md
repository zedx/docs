# Guide de contribution

- [Rapports de bogue](#bug-reports)
- [Recommandations Pull Request](#pull-request-guidelines)
- [Faille de sécurité](#security-vulnerabilities)
- [Style du code](#coding-style)
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

Si vous avez effectué une recherche *approfondie* et n'avez rien trouvé, votre rapport est le bienvenu. Si c'est juste une petite erreur (un mot mal orthographié ou une anomalie graphique, par exemple) passer au paragraphe suivant. Par contre, si vous voyez des erreurs, ou quelque chose qui est clairement cassé nous aurons besoin d'abord d'informations. S'il vous plaît, rendez-vous sur notre guide [Dépannage](http://zedx.io/docs/troubleshooting) et suivez ses instructions. Recueillez autant d'informations que vous pouvez!

Parfait, il est temps de passer à l'écriture. Retournez sur le [forum de soutien](http://discuss.zedx.io/t/bug) et commencez une nouvelle discussion. Assurez-vous de lui donner un titre clair et concis, ensuite expliquez en détail le problème. Ne pas oublier de mentionner:

<div class="content-list" markdown="1">
- Qu'est-ce que vous faisiez lorsque le problème est survenu
- Toutes les informations recueillies pendant le dépannage
- Tout ce que vous pouvez nous dire de votre environnement serveur
</div>

Rappelez-vous: l'objectif d'un rapport de bogue est que nous puissions reproduire le bogue et le corriger. Vous pouvez lire [cet article](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) qui énumère quelques conseils utiles sur la façon d'écrire un rapport de bogue efficace. Et s'il vous plaît , prenez votre temps pour rédiger votre message de sorte qu'il soit facile de comprendre de quoi il s'agit.

Une fois que vous avez posté votre rapport, nous vous demandons s'il vous plaît de *suivre la discussion* que vous avez créée et t'attendre patiemment. Nous pouvons avoir besoin de vous demander des précisions ou des éclaircissements; mais nous avons toujours beaucoup à faire, et il peut se passer un certain temps avant que nous puissions consacrer le temps nécessaire à votre rapport.

<a name="pull-request-guidelines"></a>
## Recommandations Pull Request

- Lisez le [Guide de contribution](#contributeur licence-accord).

- Nous utilisons [Long-Running Branches Workflow](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows#Long-Running-Branches)

- Sélectionnez un sujet de la branche `develop` et fusionner en arrière contre `develop`.

- [Regroupez les commits](http://davidwalsh.name/squash-commits-git) s'ils sont trop petits.

- Respectez le [style du code](#coding-style).

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

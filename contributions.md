# Contribution Guide

- [Bug Reports](#bug-reports)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Security Vulnerabilities](#security-vulnerabilities)
- [Coding Style](#coding-style)
    - [PHPDoc](#phpdoc)
    - [StyleCI](#styleci)

<a name="bug-reports"></a>
## Bug Reports

Thank you for helping us test ZEDx. We're happy to have you on the team! We need people who can *troubleshoot issues patiently* and *communicate them clearly*. As you probably know, good bug reporting takes some time and effort. If you're fine with that, then let's get started!

Found a bug already? Wonderful! We'd love to hear about it &mdash; but first you should check around to make sure you're not wasting your time on a known issue:

<div class="content-list" markdown="1">
- Search our [Support forum](http://discuss.zedx.io/t/bug) to see if it's already been reported.
- We could be working on a fix, so search our [issue tracker](https://github.com/zedx/core/issues) too.
</div>

If you've searched *thoroughly* and come up empty-handed, we'll welcome your report. If it's just a simple issue (a misspelled word or graphics glitch, for example) skip to the next paragraph. But if you're seeing errors, or something is clearly broken, we'll need you to gather some information first. Please head over to our [Troubleshooting](http://zedx.io/docs/troubleshooting) guide and follow the instructions there. Collect as much info as you can!

Okay, time to get writing. Head back to the [Support forum](http://discuss.zedx.io/t/bug) and start a new discussion. Be sure to give it a title that's clear and concise, and then explain the problem thoroughly. Don't forget to mention:

<div class="content-list" markdown="1">
- What you were doing when the problem occurred
- All the information you gathered while troubleshooting
- Anything you can tell us about your sever environment
</div>

Remember: the goal of a bug report is to make it easy for us to replicate the bug and fix it. You might want to read [this article](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) for some useful tips on how to write an effective bug report. And please take a moment or two to format your post so it's easy to tell what's what.

Once you've posted your report, we'd ask that you please *follow the discussion* that you created and wait patiently. We may need to ask for further details or clarification; but we've always got plenty to do, and it could be a while before we can give your report the time it deserves.

<a name="pull-request-guidelines"></a>
## Pull Request Guidelines

- Read the [Contributor License Agreement](#contributor-license-agreement).

- Checkout a topic branch from `develop` and merge back against `develop`.

- [Squash the commits](http://davidwalsh.name/squash-commits-git) if there are too many small ones.

- Follow the [code style](#coding-style).

<a name="security-vulnerabilities"></a>
## Security Vulnerabilities

If you discover a security vulnerability within ZEDx, please send an e-mail to <a href="mailto:security@zedx.io">security@zedx.io</a>. All security vulnerabilities will be promptly addressed.

<a name="coding-style"></a>
## Coding Style

ZEDx follows the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) coding standard and the [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) autoloading standard.

<a name="phpdoc"></a>
### PHPDoc

Below is an example of a valid ZEDx documentation block. Note that the `@param` attribute is followed by two spaces, the argument type, two more spaces, and finally the variable name:

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

If you're code style isn't perfect, don't worry! [StyleCI](https://styleci.io/) will automatically merge any style fixes into the ZEDx repository after any pull requests are merged. This allows us to focus on the content of the contribution and not the code style.

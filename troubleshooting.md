# Troubleshooting

- [Introduction](#introduction)
- [Troubleshooting installation](#troubleshoot-installation)
- [Troubleshooting ZEDx](#troubleshoot-zedx)
    - [Step 1: Turn on debug mode](#step-1-turn-on-debug-mode)
    - [Step 2: Reproduce the issue.](#step-2-reproduce-the-issue)
    - [Step 3: Collect information.](#step-3-collect-information)
    - [Step 4: Prepare a report.](#step-4-prepare-a-report)

<a name="introduction"></a>
## Introduction

If ZEDx isn't installing or working as expected, the first thing you should do is *check again* whether your environment meets the [system requirements](https://zedx.io/docs/installation/). If you're missing something that ZEDx needs to run (such as the PHP `MCrypt` extension, for example) you'll need to remedy that first.

Next, you should take a few minutes to search the [Support forum](https://discuss.zedx.io/t/support) and the [issue tracker](https://github.com/zedx/core/issues). It's possible that someone has already reported the problem, and a fix is either available or on the way. If you've searched thoroughly and can't find any information about the problem, it's time to start troubleshooting.

<a name="troubleshoot-installation"></a>
## Troubleshooting installation

<div class="content-list" markdown="1">
1. **An error 500 is displayed when downloading the application files**: You may need to increase or disable the timeout limit on your webserver. For example, Apache's FastCGI sometimes has the `-idle-timeout` option set to 30 seconds.

1. **A blank screen is displayed when opening the application**: Check the permissions are set correctly on the files and folders. For example, running the command `chmod -R 777 *` can fix it.

1. **An error code "liveConnection" is displayed**: The installer will test a connection to the installation server using port 80. Check that your webserver can create outgoing connections on port 80 via PHP. Contact your hosting provider or this is often found in the server firewall settings.

1. **MySQL shows an error "Syntax error or access violation: 1067 Invalid default value for ..."**: Check your MySQL settings file to make sure the `NO_ZERO_DATE` setting is disabled.

> **Note:** A detailed installation log can be found in the `install_files/install.log` file.
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
### Step 3: Collect information.

If it looks like you're going to need help solving the problem, it's time to get serious about collecting data. Look for error messages or other information about the problem in the following places:

- Displayed on the actual page
- Displayed in the browser console
- Recorded in the server's error log

Copy any messages to a text file and jot down a few notes about *when* the error occurred, *what* you were doing at the time, and so on. Be sure to include any insights you may have gleaned about the conditions under which the issue does and doesn't occur. Add as much information as possible about your server environment: OS version, web server version, PHP version and handler, et cetera.

<a name="step-4-prepare-a-report"></a>
## Step 4: Prepare a report.

Once you have gathered all the information you can about the problem, you're ready to file a bug report. Please post it as a new discussion in the [Support forum](https://discuss.zedx.io/t/support); you'll find more information about how to report bugs on the [Contributing](https://zedx.io/docs/contributions) page. We also recommend that you read through [this article](http://www.chiark.greenend.org.uk/~sgtatham/bugs.html) for some useful pointers on how to write an effective bug report.

If you discover something new about the issue after filing your report, please add that information at the bottom of your original post. It's a good idea to file a report even if you have solved the problem on your own, since other users may also benefit from your solution. If you've found a temporary workaround for the problem, be sure to mention that as well.

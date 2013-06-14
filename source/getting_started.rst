Getting Started
===============

This section is primarily written for Windows users. There are extra sections
about installing Git Extensions on Linux and Mac OS X. 

Installation
------------

There is a single click installer that installs MsysGit, Kdiff3 and Git Extensions. The installer will detect 
if 32bit and/or 64bit versions should be installed.
The installer can be found `here <http://code.google.com/p/gitextensions/>`_.

.. image:: /images/install/install1.png

.. figure:: /images/install/install2.png

    Git Extensions depends heavily on MsysGit. When MsysGit is not installed, ensure the "Install MsysGit" checkbox is checked. Kdiff3 is 
    optional, but is advised as a merge tool.

.. image:: /images/install/install3.png

.. figure:: /images/install/install4.png

    Choose the options to install.

.. figure:: /images/install/install5.png

    Choose the SSH client to use. PuTTY is the default because it has better Windows integration.

.. image:: /images/install/install6.png

Installation (Linux)
--------------------
You can watch this video as a starting point: `Install Git Extensions on Ubuntu 11.04  <http://www.youtube.com/watch?v=zk2MMUQuW4s>`_

For further help go to https://groups.google.com/forum/?fromgroups=#!forum/gitextensions

Installation (Mac)
------------------

First, make sure you have the latest mono version on your Mac. This section will cover installation of mono 2.10.11 on a Mac.

1) Download mono latest version. You can always check for this here: http://www.go-mono.com/mono-downloads/download.html
2) After you have completed the download, you will see a .dmg file. Double click it to open the package.
3) Inside the .dmg file you will have MonoFramework-{version}.pkg. Double click to start the installation process.
4) Follow the wizard until it's completion.
5) If everything went okay, you should open your terminal and check mono version::

    $ mono --version
    Mono JIT compiler version 2.10.11 (mono-2-10/2baeee2 Wed Jan 16 16:40:16 EST 2013)
    Copyright (C) 2002-2012 Novell, Inc, Xamarin, Inc and Contributors. www.mono-project.com
        TLS:           normal
        SIGSEGV:       normal
        Notification:  kqueue
        Architecture:  x86
        Disabled:      none
        Misc:          softdebug 
        LLVM:          yes(2.9svn-mono)
        GC:            Included Boehm (with typed GC)

6) Now download GitExtensions latest version from https://code.google.com/p/gitextensions/downloads/list. Remember to select the appropriate package otherwise you could have problems.
7) Browse into the folder where you extracted the package and just run mono command, like the example below::

    $ mono GitExtensions.exe 

This is the minimal setup you need in order to run Git Extensions.

Settings
--------

All settings will be verified when Git Extensions is started for the first time. If Git Extensions requires 
any settings to be changed, the Settings dialog will be shown. All incorrect settings will be marked in red. 
You can ask Git Extensions to try to fix the setting for you by clicking on it.
When installing Git Extensions for the first time (and you do not have Git already installed on your system),
you will normally be required to configure your username and email address.

The settings dialog can be invoked at any time by selecting ``Settings`` from the ``Settings`` menu option.

.. image:: /images/settings/settings.png

The following buttons are always available on any page of the Settings dialog. Sometimes the ``Cancel`` and ``Discard``
buttons have no effect for the page - this will be noted on the page in the area next to the buttons.

+-------------------------------+--------------------------------------------------------------------------+
| Button                        | Description                                                              |
+===============================+==========================================================================+
|``OK``                         | Save any entered changes made in *any* settings page and close the       |
|                               | Settings dialog.                                                         |
+-------------------------------+--------------------------------------------------------------------------+
|``Cancel``                     | Any entered changes in *any* settings page are *not* saved. The Settings |
|                               | dialog is closed.                                                        |
+-------------------------------+--------------------------------------------------------------------------+
|``Discard``                    | Any entered changes in *any* settings page are discarded i.e. they are   |
|                               | reset back to their original values.                                     |
+-------------------------------+--------------------------------------------------------------------------+
|``Apply``                      | Any entered changes in *any* settings page are saved.                    |
+-------------------------------+--------------------------------------------------------------------------+

All settings that are specific to Git Extensions will be stored in a file either in the user's application data path or with the program. 
The location is dependant on the IsPortable setting in the GitExtensions.exe.config file that is with the program.
The settings that are used by Git are stored in the configuration files of Git. The global settings are stored in a file called 
``.gitconfig`` in the user directory. The local settings are stored in the ``.git\config`` file of the repository.

Checklist
^^^^^^^^^

This page is a visual overview of the minimal settings that Git Extensions requires to work properly. Any items highlighted in red should
be configured by clicking on the highlighted item. 

This page contains the following settings and buttons.

+---------------------------------------------------+----------------------------------------------------------------------------+
| Setting                                           | Description                                                                |
+===================================================+============================================================================+
|Check settings at startup (disables automatically  | Forces Git Extensions to re-check the minimal set of required settings     |
|if all settings are correct)                       | the next time Git Extensions is started. If all settings are 'green' this  |
|                                                   | will be automatically unchecked.                                           |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Save and rescan Button                             | Saves any setting changes made and re-checks the settings to see if the    |
|                                                   | minimal requirements are now met.                                          |
+---------------------------------------------------+----------------------------------------------------------------------------+

Git
^^^

This page contains the settings needed to access git repositories. The repositories will be accessed using external 
tools. For Windows usually MsysGit or cygwin are used. Git Extensions will try to configure these settings automatically.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Git          |Command used to run git (git.cmd or  | Needed for Git Extensions to run Git commands. Set the full command used   |
|             |git.exe)                             | to run git (MsysGit or cygwin). Use the Browse button to find the          |
|             |                                     | executable on your file system.                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to Linux tools (sh). Leave empty| A few linux tools are used by Git Extensions. When MsysGit is installed,   |
|             |when it is in the path.              | these tools are located in the bin directory of MsysGit. Use the           |
|             |                                     | Browse button to find the directory on your file system.                   |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Environment  |Change HOME Button                   | This button opens a dialog where the HOME directory can be changed.        |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

The global configuration file used by git will be put in the HOME directory. On some systems the home directory is not set 
or is pointed to a network drive. Git Extensions will try to detect the optimal setting for your environment. When there is 
already a global git configuration file, this location will be used. If you need to relocate the home directory for git, 
click the Change HOME button to change this setting. Otherwise leave this setting as the default.

Git Extensions
^^^^^^^^^^^^^^

This page contains all the settings needed for Git Extensions to run properly.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Performance  |Show repository status in browse     | When enabled, the number of pending commits are shown on the toolbar as a  |
|             |dialog (number of changes in toolbar,| figure in parentheses next to the Commit button. Git Extensions must be    |
|             |restart required)                    | stopped and restarted to activate changes to this option.                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Show current working dir changes in  | When enabled, two extra revisions are added to the revision graph. The     |
|             |revision graph                       | first shows the current working directory status. The second shows the     |
|             |                                     | staged files. This option can cause slowdowns when browsing large          |
|             |                                     | repositories.                                                              |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Use FileSystemWatcher to check if    | Using the FileSystemWatcher to check index state improves the performance  |
|             |index is changed                     | in some cases. Turn this off if you experience refresh problems in commit  |
|             |                                     | log.                                                                       |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Show stash count on status bar in    | When you use the stash a lot, it can be useful to show the number of       |
|             |browse window                        | stashed items on the toolbar. This option causes serious slowdowns in large|
|             |                                     | repositories and is turned off by default.                                 |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Check for uncommitted changes in     | Git Extensions will not allow you to checkout a branch if you have         |
|             |checkout branch dialog               | uncommitted changes on the current branch. If you select this option, Git  |
|             |                                     | Extensions will display a dialog where you can decide what to do with      |
|             |                                     | uncommitted changes before swapping branches.                              |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Limit number of commits that will be | Git Extensions uses lazy loading to load the commit log. Lower this number |
|             |loaded in list at start-up           | to increase the start-up speed. Increase the number for faster scrolling.  |
|             |                                     | Turn off revision graph for optimal result!                                |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Behaviour    |Close Process dialog when process is | When a process is finished, close the process dialog automatically. Leave  |
|             |succeeded                            | this option off if you want to see the result of processes. When a process |
|             |                                     | has failed, the dialog will automatically remain open.                     |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Show console window when executing   | Git Extensions uses command line tools to access the git repository. In    |
|             |git process                          | some environments it might be useful to see the command line dialog when a |
|             |                                     | process is executed. An option on the command line dialog window displayed |
|             |                                     | allows this setting to to be turned off.                                   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Use patience diff algorithm          | Use the Git 'patience diff' algorithm instead of the default. This         |
|             |                                     | algorithm is useful in situations where two files have diverged            |
|             |                                     | significantly and the default algorithm may become 'misaligned', resulting |
|             |                                     | in a totally unusable conflict file.                                       |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Show errors when staging files       |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Include untracked files in stash     |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Follow renames in file history       | Try to follow file renames in the file history.                            |
|             |(experimental)                       |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Open last working dir on startup     | When starting Git Extensions, open the last used repository (bypassing the |
|             |                                     | Start Page).                                                               |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Play Special Startup Sound           | Play a sound when starting Git Extensions. It will put you in a good       |
|             |                                     | moooooood!                                                                 |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Compose commit messages in Commit    | If this is unchecked, then commit messages cannot be entered in the commit |
|             |dialog (otherwise the message will be| dialog. When the Commit button is clicked, a new editor window is opened   |
|             |requested during commit)             | where the commit message can be entered.                                   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Revision grid quick search timeout   | The timeout (milliseconds) used for the quick search feature in the        |
|             |[ms]                                 | revision graph. The quick search will be enabled when you start typing and |
|             |                                     | the revision graph has the focus.                                          |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Smtp server for sending patches by   | Smtp server to use for sending patches.                                    |
|             |email                                |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

Appearance
^^^^^^^^^^

This page contains settings that affect the appearance of the application.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|General      |Show relative date instead of full   | Show relative date, e.g. 2 weeks ago, instead of full date.                |
|             |date                                 | Displayed on the ``commit`` tab on the main Commit Log window.             |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Show current branch in Visual Studio |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Auto scale user interface when high  |                                                                            |
|             |dpi is used                          |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Truncate long filenames              |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Author images|Get author image from gravatar.com   | Whether or not to retrieve the user avatar from                            |
|             |                                     | `gravatar <http://en.gravatar.com/>`_. This avatar is displayed on the     |
|             |                                     | ``commit`` tab on the main Commit Log window.                              |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Image size                           | The display size of the user avatar.                                       |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Cache images                         | The number of days to elapse before gravatar is checked for any changes to |
|             |                                     | a user's avatar.                                                           |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |No image service                     |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Clear image cache button             | Clear the cached avatars.                                                  |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Fonts        |Code font                            | Change the font used for the display of file contents.                     |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Application font                     | Change the font used on Git Extensions windows and dialogs.                |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Language     |Language (restart required)          | Choose the language for the Git Extensions interface.                      |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Dictionary for spelling checker      | Choose the dictionary to use for the spelling checker in the Commit dialog.|
+-------------+-------------------------------------+----------------------------------------------------------------------------+

Colors
^^^^^^

This page contains settings to define the colors used in the application.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Revision     |Multicolor branches                  | Displays branch commits in different colors if checked. If unchecked,      |
|graph        |                                     | allows the color to be selected.                                           |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Striped branch change                |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Draw branch borders                  | Outlines branch commits in a black border if checked.                      |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Draw non relatives graph gray        | Show commit history in gray for branches not related to the current branch.|
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Draw non relatives text gray         | Show commit text in gray for branches not related to the current branch.   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color tag                            | Color to show tags in.                                                     |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color branch                         | Color to show branch names in.                                             |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color remote branch                  | Color to show remote branch names in.                                      |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color other label                    | Color to show other labels in.                                             |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Application  |Icon style                           | Change icons. Useful for recognising various open instances.               |
|Icon         +-------------------------------------+----------------------------------------------------------------------------+
|             |Icon color                           | Changes color of the selected icons.                                       |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Difference   |Color removed line                   | Highlight color for lines that have been removed.                          |
|View         |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color added line                     | Highlight color for lines that have been added.                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color removed line highlighting      | Highlight color for characters that have been removed in lines.            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color added line highlighting        | Highlight color for characters that have been added in lines.              |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color section                        | Highlight color for a section.                                             |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

.. _settings-start-page:

Start Page
^^^^^^^^^^

This page allows you to add/remove or modify the Categories and repositories that will appear on the Start Page when Git Extensions is 
launched. Per Category you can either configure an RSS feed or add repositories. The order of both Categories, and repositories within
Categories, can be changed using the context menus in the Start Page. See :ref:`start-page` for further details.
 
+---------------------------------------------------+----------------------------------------------------------------------------+
| Setting                                           | Description                                                                |
+===================================================+============================================================================+
|Categories                                         | Lists all the currently defined Categories. Click the Add button to        |
|                                                   | add a new empty Category. The default name is 'new'.  To remove a Category |
|                                                   | select it and click Remove. This will delete the Category *and* any        |
|                                                   | repositories belonging to that Category.                                   |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Caption                                            | This is the Category name displayed on the Start Page.                     |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Type                                               | Specify the type: an RSS feed or a repository.                             |
+---------------------------------------------------+----------------------------------------------------------------------------+
|RSS Feed                                           | Enter the URL of the RSS feed.                                             |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Path/Title/Description                             | For each repository defined for a Category, shows the path, title and      |
|                                                   | description. To add a new repository, click on a blank line and type the   |
|                                                   | appropriate information. The contents of the Path field are shown on the   |
|                                                   | Start Page as a link to your repository *if* the Title field is blank. If  |
|                                                   | the Title field is non-blank, then this text is shown as the link to your  |
|                                                   | repository. Any text in the Description field is shown underneath the      |
|                                                   | repository link on the Start Page.                                         |
+---------------------------------------------------+----------------------------------------------------------------------------+

An RSS Feed can be useful to follow repositories on GitHub for example. See this page on GitHub: https://help.github.com/articles/viewing-your-feeds.
You can also follow commits on public GitHub repositories by

1) In your browser, navigate to the public repository on GitHub.
2) Select the branch you are interested in.
3) Click on the Commits tab.
4) You will find a RSS icon next to the words "Commit History".
5) Copy the link
6) Paste the link into the RSS Feed field in the Settings - Start Page as shown above.

Your Start Page will then show each commit - clicking on a link will open your browser and take you to the commit on GitHub. 

Global Settings
^^^^^^^^^^^^^^^

This page contains the following global Git settings. These settings will affect all repositories.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|             |User name                            | User name shown in commits and patches.                                    |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |User email                           | User email shown in commits and patches.                                   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Editor                               | Editor that git.exe opens (e.g. for editing commit message). This is not   |
|             |                                     | used by Git Extensions, only when you call git.exe from the command line.  |
|             |                                     | By default Git will use the command line text editor vi.                   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Mergetool                            | Merge tool used to solve merge conflicts. Git Extensions will search for   |
|             |                                     | common merge tools on your system.                                         |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to mergetool                    | Path to merge tool. Git Extensions will search for common merge tools on   |
|             |                                     | your system.                                                               |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Mergetool command                    | Command that Git uses to start the merge tool. Git Extensions will try to  |
|             |                                     | set this automatically when a merge tool is chosen. This setting can be    |
|             |                                     | left empty when Git supports the mergetool (e.g. kdiff3).                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Keep backup (.orig) after merge      | Check to save the state of the original file before modifying to solve     |
|             |                                     | merge conflicts. Refer to Git configuration setting                        |
|             |                                     | ```mergetool.keepBackup```.                                                |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Difftool                             | Diff tool that is used to show differences between source files. Git       |
|             |                                     | Extensions will search for common diff tools on your system.               |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to difftool                     | The path to the diff tool. Git Extensions will search for common diff tools|
|             |                                     | on your system.                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |DiffTool command                     | Command that Git uses to start the diff tool. This setting should only be  |
|             |                                     | filled in when Git doesn't support the diff tool.                          |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to commit template              | A path to a file whose contents are used to pre-populate the commit message|
|             |                                     | in the commit dialog.                                                      |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Line endings |Checkout/commit radio buttons        |Choose how git should handle line endings when checking out and checking in |
|             |                                     |files. Refer to                                                             |
|             |                                     |https://help.github.com/articles/dealing-with-line-endings#platform-all     |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|             |Files content encoding               | Choose the encoding you want GitExtensions to use.                         |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

Local Settings
^^^^^^^^^^^^^^

This page contains the Git settings *for a repository*. These settings are only required if you wish to override the global
Git settings for this specific repository.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|             |User name                            | User name shown in commits and patches.                                    |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |User email                           | User email shown in commits and patches.                                   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Editor                               | Editor that git.exe opens (e.g. for editing commit message). This is not   |
|             |                                     | used by Git Extensions, only when you call git.exe from the command line.  |
|             |                                     | By default Git will use the command line text editor vi.                   |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Mergetool                            | Merge tool used to solve merge conflicts. Git Extensions will search for   |
|             |                                     | common merge tools on your system.                                         |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Keep backup (.orig) after merge      | Check to save the state of the original file before modifying to solve     |
|             |                                     | merge conflicts. Refer to Git configuration setting                        |
|             |                                     | ```mergetool.keepBackup```.                                                |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Line endings |Checkout/commit radio buttons        |Choose how git should handle line endings when checking out and checking in |
|             |                                     |files. Refer to                                                             |
|             |                                     |https://help.github.com/articles/dealing-with-line-endings#platform-all     |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|             |Files content encoding               | Choose the encoding you want GitExtensions to use.                         |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

SSH
^^^

This page allows you to configure the SSH client you want Git to use. Git Extensions is optimized for PuTTY. Git Extensions 
will show command line dialogs if you do not use PuTTY and user input is required. Git Extensions can load SSH keys for PuTTY 
when needed.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Specify which|PuTTY radio button                   | Use PuTTY as SSH client.                                                   |
|ssh client   +-------------------------------------+----------------------------------------------------------------------------+
|to use       |OpenSSH radio button                 | Use OpenSSH as SSH client.                                                 |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Other ssh client                     | Use another SSH client. Enter the path to the SSH client you wish to use.  |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Configure    |Path to plink.exe                    | Enter the path to the plink.exe executable.                                |
|PuTTY        |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to puttygen                     | Enter the path to the puttygen.exe executable.                             |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to pageant                      | Enter the path to the pageant.exe executable.                              |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Automatically start authentication   |                                                                            |
|             |checkbox                             |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

.. _settings-scripts:

Scripts
^^^^^^^

This page allows you to configure specific commands to run before/after Git actions or to add a new command to the User Menu. 
The top half of the page summarises all of the scripts currently defined. If a script is selected from the summary, the bottom
half of the page will allow modifications to the script definition.

A hotkey can also be assigned to execute a specific script. See :ref:`settings-hotkeys`.

+---------------------------------------------------+----------------------------------------------------------------------------+
| Setting                                           | Description                                                                |
+===================================================+============================================================================+
|Add Button                                         | Adds a new script. Complete the details in the bottom half of the screen.  |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Remove Button                                      | Removes a script.                                                          |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Up/Down Arrows                                     | Changes order of scripts.                                                  |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Name                                               | The name of the script.                                                    |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Enabled checkbox                                   | If checked, the script is active and will be performed at the appropriate  |
|                                                   | time (as determined by the On Event setting).                              |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Ask for confirmation checkbox                      | If checked, then a popup window is displayed just before the script is run |
|                                                   | to confirm whether or not the script is to be run. Note that this popup    |
|                                                   | is *not* displayed when the script is added as a command to the User Menu  |
|                                                   | (On Event setting is ShowInUserMenuBar).                                   |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Add to revision grid context menu checkbox         | If checked, the script is added to the context menu that is displayed when |
|                                                   | right-clicking on a line in the Commit Log page.                           |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Command                                            | Enter the command to be run. This can be any command that your system can  |
|                                                   | run e.g. an executable program, a .bat script, a Python command, etc.      |
|                                                   | Use the ```Browse`` button to find the command to run.                     |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Arguments                                          | Enter any arguments to be passed to the command that is run.  The          |
|                                                   | ```Help``` button displays items that will be resolved by Git Extensions   |
|                                                   | before executing the command e.g. {cBranch} will resolve to the currently  |
|                                                   | checked out branch, {UserInput} will display a popup where you can enter   |
|                                                   | data to be passed to the command when it is run.                           |
+---------------------------------------------------+----------------------------------------------------------------------------+
|On Event                                           | Select when this command will be executed, either before/after certain Git |
|                                                   | commands, or displayed on the User Menu bar.                               |
+---------------------------------------------------+----------------------------------------------------------------------------+

.. _settings-hotkeys:

Hotkeys
^^^^^^^

This page allows you to define keyboard shortcuts to actions when specific pages of Git Extensions are displayed.
The HotKeyable Items identifies a page within Git Extensions. Selecting a Hotkeyable Item displays the list of
commands on that page that can have a hotkey associated with them. 

The Hotkeyable Items consist of the following pages

1) Commit: the page displayed when a Commit is requested via the ```Commit``` User Menu button or the ```Commands/Commit``` menu option.
2) Browse: the Commit Log page (the page displayed after a repository is selected from the Start Page).
3) RevisionGrid: the list of commits on the Commit Log page.
4) FileViewer: the page displayed when viewing the contents of a file.
5) FormMergeConflicts: the page displayed when merge conflicts are detected that need correcting.
6) Scripts: shows scripts defined in Git Extensions and allows shortcuts to be assigned. Refer :ref:`settings-scripts`.    

+---------------------------------------------------+----------------------------------------------------------------------------+
| Setting                                           | Description                                                                |
+===================================================+============================================================================+
|Hotkey                                             | After selecting a Hotkeyable Item and the Command, the current keyboard    |
|                                                   | shortcut associated with the command is displayed here. To alter this      |
|                                                   | shortcut, just press the keyboard combination required. This field will be |
|                                                   | updated to reflect the keys pressed.                                       |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Apply button                                       | Click to apply the entered keyboard combination to the Command.            |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Clear button                                       | Sets the keyboard shortcut for the Command to 'None'.                      |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Reset all Hotkeys to defaults button               | Resets all keyboard shortcuts to the defaults (i.e. the values when Git    |
|                                                   | Extensions was first installed).                                           |
+---------------------------------------------------+----------------------------------------------------------------------------+

Shell Extension
^^^^^^^^^^^^^^^

When installed, Git Extensions adds items to the context menu when a file/folder is right-clicked within Windows Explorer. One of these items
is ```Git Extensions``` from which a further(cascaded) menu can be opened. This settings page identifies what items will appear on that cascaded
menu. 

.. note:: what is displayed also depends on what item is being right-clicked in Windows Explorer; 
   a file or a folder(and whether the folder is a Git repository or not).


Advanced
^^^^^^^^
This page allows advanced settings to be modified. Clicking on the '+' symbol on the tree of settings will display further settings.
Refer :ref:`settings-confirmations`.   
 
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Checkout     |Always show checkout dialog          | Always show the Checkout Branch dialog when swapping branches.             |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Use last chosen "local changes"      |                                                                            |
|             |action as default action.            |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|General      |Don't show help images               |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

.. _settings-confirmations:

Confirmations
^^^^^^^^^^^^^
This page allows you to turn off certain confirmation popup windows.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Don't ask to |Amend last commit                    |If checked do not display popup warning about the rewriting of history.     |
|confirm to   +-------------------------------------+----------------------------------------------------------------------------+
|             |Apply stashed changes                |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Push a new branch for the remote     |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Add a tracking reference for newly   |                                                                            |
|             |pushed branch                        |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

Plugins
^^^^^^^

Plugins provide extra functionality for Git Extensions.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Plugin       | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Check for    |**This plugin is used by Git Extensions to check for updates to the Git Extensions software.**                    |
|Updates      |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Enabled (true/false)                 |Enable or disable the check.                                                |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Check every # days                   |Check for updates after this number of days have elapsed since the last     |
|             |                                     |check.                                                                      |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Last check (yyyy/M/dd)               |Shows date of the last check.                                               |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Auto compile |                                                                                                                  |
|SubModules   |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Enabled (true/false)                 |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to msbuild.exe                  |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |msbuild.exe arguments                |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Create local |**This plugin will create local tracking branches for all branches on a remote repository. The remote repository  |
|tracking     |is specified when the plugin is run.**                                                                            |
|branches     |                                                                                                                  |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Delete       |                                                                                                                  |
|obsolete     |                                                                                                                  |
|branches     |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Delete obsolete branches older than  |                                                                            |
|             |(days)                               |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Branch where all branches should be  |                                                                            |
|             |merged                               |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Find large   |                                                                                                                  |
|files        |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Find large files bigger than (Mb)    |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Gerrit Code  |                                                                                                                  |
|Review       |                                                                                                                  |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Github       |                                                                                                                  |
|             |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |OAuth Token                          |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Impact Graph |                                                                                                                  |
|             |                                                                                                                  |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Statistics   |**This plugin provides various statistics (and a pie chart) about the current Git repository. For example, number |
|             |of commits by author, lines of code per language.**                                                               |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Code files                           |Specifies extensions of files that are considered code files.               |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Directories to ignore (EndsWith)     |Ignore these directories when calculating statistics.                       |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Ignore submodules (true/false)       |Ignore submodules when calculating statistics.                              |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|gource       |                                                                                                                  |
|             |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to "gource"                     |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Arguments                            |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Proxy        |                                                                                                                  |
|Switcher     |                                                                                                                  |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |USername                             |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Password                             |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |HttpProxy                            |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |HttpProxyPort                        |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Release Notes|**This plugin will generate 'release notes'. This involves summarising all commits between the specified from and |
|Generator    |to commit expressions when the plugin is started. This output can be copied to the clipboard in various formats.**|
+-------------+-------------------------------------+----------------------------------------------------------------------------+


.. _start-page:

Start Page
----------

The start page contains the most common tasks, recently opened repositories and favourites. The left side of the start page (Common Actions
and Recent Repositories) is static. The right side of the page is where favourite repositories can be added, grouped under Category headings.

.. image:: /images/start_page.png

Recent Repositories can be moved to favourites using the repository context menu. Choose ``Move to category / New category`` to create a new category
and add the repository to it, or you can add the repository to an existing category (e.g. 'Currents' as shown below).

.. image:: /images/move_to_category.png

A context menu is available for both the category and the repositories listed underneath it.

Entries on Category context menu 

+------------------+-------------------------------------------------------------------------------------------------------+
|Move Up           | Move the category (and any repositories under it) higher on the page.                                 |
+------------------+-------------------------------------------------------------------------------------------------------+
|Move Down         | Move the category (and any repositories under it) lower on the page.                                  |
+------------------+-------------------------------------------------------------------------------------------------------+
|Remove            | Remove the category (and any repositories under it) from the page. Note: Git repositories are *not*   |
|                  | physically removed either locally or remotely.                                                        |
+------------------+-------------------------------------------------------------------------------------------------------+
|Edit              | Shows the Start Page settings window where both category and repository details can be modified.      |
|                  | See :ref:`settings-start-page`.                                                                       |
+------------------+-------------------------------------------------------------------------------------------------------+

Entries on repository context menu

+------------------+-------------------------------------------------------------------------------------------------------+
|Move to category  | Move the repository to a new or existing category.                                                    |
+------------------+-------------------------------------------------------------------------------------------------------+
|Move up           | Move the repository higher (within the category).                                                     |
+------------------+-------------------------------------------------------------------------------------------------------+
|Move down         | Move the repository lower (within the category).                                                      |
+------------------+-------------------------------------------------------------------------------------------------------+
|Remove            | Remove the repository from the category. Note: the repository is *not* physically removed either      |
|                  | locally or remotely.                                                                                  |
+------------------+-------------------------------------------------------------------------------------------------------+
|Edit              | Shows the Start Page settings window where both category and repository details can be modified.      |
|                  | See :ref:`settings-start-page`.                                                                       |
+------------------+-------------------------------------------------------------------------------------------------------+
|Show current      | Toggles the display of the branch name next to the repository name. This identifies the currently     |
|branch            | checked out branch for the repository.                                                                |
+------------------+-------------------------------------------------------------------------------------------------------+

To open an existing repository, simply click the link to the repository under Recent Repositories or within the Categories that you have set up, or 
select Open repository (from where you can select a repository to open from your local file system).

To create a new repository, one of the following options under Common Actions can be selected. 

Clone repository
----------------

You can clone an existing repository using this option. It displays the following dialog.

.. image:: /images/clone.png

The repository you want to clone could be on a network share or could be a repository that is accessed through an internet 
or intranet connection. Depending on the protocol (http or ssh) you might need to load a SSH key into PuTTY. You also need to specify where
the cloned repository will be created and the initial branch that is checked out.  

There are two different types of repositories you can create when making a clone. A personal repository contains the complete 
history and also contains a working copy of the source tree. A central repository is used as a public repository where 
developers push the changes they want to share with others to. A central repository contains the complete history but does not 
have a working directory like personal repositories.

Clone SVN repository
--------------------

You can clone an existing SVN repository using this option, which creates a Git repository from the SVN repository you specify. 
For further information refer to the `Pro Git book <http://git-scm.com/book/en/Git-and-Other-Systems-Migrating-to-Git>`_.

Clone Github repository
-----------------------

This option allows you to 

1) Fork a repository on GitHub so it is created in your personal space on GitHub.
2) Clone any repositories on your personal space on GitHub so that it becomes a local repository on your machine.

You can see your own personal repositories on GitHub, and also search for repositories using the ``Search for repositories`` tab.

.. image:: /images/github_clone.png

Create new repository
---------------------

When you do not want to work on an existing project, you can create your own repository using this option.

.. image:: /images/new_repository.png

Select a directory where the repository is to be created. You can choose to create a Personal repository or a Central repository.

A personal repository looks the same as a normal working directory but has a directory named ``.git`` at the root level 
containing the version history. This is the most common repository.

Central repositories only contain the version history. Because a central repository has no working directory you cannot 
checkout a revision in a central repository. It is also impossible to merge or pull changes in a central repository. This 
repository type can be used as a public repository where developers can push changes to or pull changes from.


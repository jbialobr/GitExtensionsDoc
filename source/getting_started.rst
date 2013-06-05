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
Settings that are used by Git are stored in the configuration files of Git. The global settings are stored in a file called 
``.gitconfig`` in the user directory. The local settings are stored in the ``.git\config`` file of the repository.

Settings - Checklist
^^^^^^^^^^^^^^^^^^^^

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
|``Save and rescan`` Button                         | Saves any setting changes made and re-checks the settings to see if the    |
|                                                   | minimal requirements are now met.                                          |
+---------------------------------------------------+----------------------------------------------------------------------------+

Settings - Git
^^^^^^^^^^^^^^

This page contains the settings needed to access git repositories. The repositories will be accessed using external 
tools. For Windows usually MsysGit or cygwin are used. Git Extensions will try to configure these settings automatically.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Git          |Command used to run git (git.cmd or  | Needed for Git Extensions to run Git commands. Set the full command used   |
|             | git.exe)                            | to run git (MsysGit or cygwin). Use the ``Browse`` button to find the      |
|             |                                     | executable on your file system.                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Path to Linux tools (sh). Leave empty| A few linux tools are used by Git Extensions. When MsysGit is installed,   |
|             |when it is in the path.              | these tools are located in the bin directory of MsysGit. Use the           |
|             |                                     | ``Browse`` button to find the directory on your file system.               |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Environment  |``Change HOME`` Button               | This button opens a dialog where the HOME directory can be changed.        |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

The global configuration file used by git will be put in the HOME directory. On some systems the home directory is not set 
or is pointed to a network drive. Git Extensions will try to detect the optimal setting for your environment. When there is 
already a global git configuration file, this location will be used. If you need to relocate the home directory for git, 
click the ``Change HOME`` button to change this setting. Otherwise leave this setting as the default.

Settings - Git Extensions
^^^^^^^^^^^^^^^^^^^^^^^^^

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
|             |Check for uncommitted changes in     |                                                                            |
|             |checkout branch dialog               |                                                                            |
|             |                                     |                                                                            |
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
|             |                                     | process is executed.                                                       |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Use patience diff algorithm          |                                                                            |
|             |                                     |                                                                            |
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
|             |Open last working dir on startup     |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Play Special Startup Sound           |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Compose commit messages in Commit    |                                                                            |
|             |dialog (otherwise the message will be|                                                                            |
|             |requested during commit)             |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Revision grid quick search timeout   | The timeout (milliseconds) used for the quick search feature in the        |
|             |[ms]                                 | revision graph. The quick search will be enabled when you start typing and |
|             |                                     | the revision graph has the focus.                                          |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Smtp server for sending patches by   | Smtp server to use for sending patches.                                    |
|             |email                                |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

Settings - Appearance
^^^^^^^^^^^^^^^^^^^^^

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
|             |``Clear image cache`` button         | Clear the cached avatars.                                                  |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Fonts        |Code font                            | Change the font used for the display of file contents.                     |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Application font                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Language     |Language (restart required)          | Choose the language for the Git Extensions interface.                      |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Dictionary for spelling checker      | Choose the dictionary to use for the spelling checker in the Commit dialog.|
+-------------+-------------------------------------+----------------------------------------------------------------------------+

Settings - Colors
^^^^^^^^^^^^^^^^^

This page contains settings to define the colors used in the application.

+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Group        | Setting                             | Description                                                                |
+=============+=====================================+============================================================================+
|Revision     |Multicolor branches                  |                                                                            |
|graph        |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Striped branch change                |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Draw branch borders                  |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Draw non relatives graph gray        |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Draw non relatives text gray         |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color tag                            |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color branch                         |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color remote branch                  |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color other label                    |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Application  |Icon style                           |   useful for recognising various open instances. FIX                       |
|Icon         |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Icon color                           |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+
|Difference   |Color removed line                   |                                                                            |
|View         |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color added line                     |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color removed line highlighting      |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color added line highlighting        |                                                                            |
|             |                                     |                                                                            |
|             +-------------------------------------+----------------------------------------------------------------------------+
|             |Color section                        |                                                                            |
|             |                                     |                                                                            |
+-------------+-------------------------------------+----------------------------------------------------------------------------+

.. _settings-start-page:

Settings - Start Page
^^^^^^^^^^^^^^^^^^^^^

The items on the Start Page can be edited. In this tab you can add and remove categories. Per category you can either configure 
a RSS feed or add repositories. The order can be changed using the context menus in the Start Page.
If the title is set (i.e. non-blank), then this will be displayed on the Start Page as a link to your repository. If the title is blank,
then the path of your repository is displayed as a link on the Start Page. Any Description entered will be also be shown
on the Start Page. 

Settings - Global Settings
^^^^^^^^^^^^^^^^^^^^^^^^^^

This page contains the following global Git settings.

+------------------+-------------------------------------------------------------------------------------------------------+
|User name         | User name shown in commits and patches.                                                               |
+------------------+-------------------------------------------------------------------------------------------------------+
|User email        | User email shown in commits and patches.                                                              |
+------------------+-------------------------------------------------------------------------------------------------------+
|Editor            | Editor that git.exe opens (e.g. for editing commit message). This is not used by Git Extensions, only |
|                  | when you call git.exe from the command line. By default Git will use the command line text editor vi. |
+------------------+-------------------------------------------------------------------------------------------------------+
|Mergetool         | Merge tool used to solve merge conflicts. Git Extensions will search for common merge tools on your   |
|                  | system.                                                                                               |
+------------------+-------------------------------------------------------------------------------------------------------+
|Path to mergetool | Path to merge tool. Git Extensions will search for common merge tools on your system.                 |
+------------------+-------------------------------------------------------------------------------------------------------+
|Mergetool command | Command that Git uses to start the merge tool. Git Extensions will try to set this automatically when |
|                  | a merge tool is chosen. This setting can be left empty when Git supports the mergetool (e.g. kdiff3). |
+------------------+-------------------------------------------------------------------------------------------------------+
|Difftool          | Diff tool that is used.                                                                               |
+------------------+-------------------------------------------------------------------------------------------------------+
|Path to difftool  | The path to the diff tool.                                                                            |
+------------------+-------------------------------------------------------------------------------------------------------+
|DiffTool command  | Command that Git uses to start the diff tool. This setting should only be filled in when Git doesn't  |
|                  | support the diff tool.                                                                                |
+------------------+-------------------------------------------------------------------------------------------------------+
|Line endings      | Choose how git should handle line endings when checking out and checking in files.                    |
+------------------+-------------------------------------------------------------------------------------------------------+
|Files content     | Choose the encoding you want GitExtensions to use.                                                    |
|encoding          |                                                                                                       |
+------------------+-------------------------------------------------------------------------------------------------------+

Settings - SSH
^^^^^^^^^^^^^^

In the tab ``SSH`` you can configure the SSH client you want Git to use. Git Extensions is optimized for PuTTY. Git Extensions 
will show command line dialogs if you do not use PuTTY and user input is required. Git Extensions can load SSH keys for PuTTY 
when needed.

Settings - Scripts
^^^^^^^^^^^^^^^^^^

Settings - Hotkeys
^^^^^^^^^^^^^^^^^^

Settings - Shell extension
^^^^^^^^^^^^^^^^^^^^^^^^^^

Settings - Advanced
^^^^^^^^^^^^^^^^^^^

Settings - Plugins
^^^^^^^^^^^^^^^^^^

Start Page
----------

The start page contains the most common tasks, recently opened repositories and favourites. The left side of the start page (Common Actions
and Recent Repositories) is static. The right side of the page is where favourite repositories can be added, grouped under Category headings.

.. image:: /images/start_page.png

Recent Repositories can be moved to favourites using the context menu. Choose ``Move to category / New category`` to create a new category
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

** UPTO HERE **

Clone existing repository
-------------------------

You can clone an existing repository using the ``Clone`` menu option. You can choose the repository type to clone to. For 
personal use you need to choose ``Personal repository``. For a central or public repository, choose ``Central repository``. A 
central repository does not have a working directory.

.. image:: /images/clone.png

The repository you want to clone could be on a network share or could be a repository that is accessed through an internet 
or intranet connection. Depending on the protocol (http or ssh) you might need to load a SSH key into PuTTY.

There are two different types of repositories you can create when making a clone. A personal repository contains the complete 
history and also contains a working copy of the source tree. A central repository is used as a public repository where 
developers push the changes they want to share with others to. A central repository contains the complete history but does not 
have a working directory like personal repositories.

Create new repository
---------------------

When you do not want to work on an existing project, you can create your own repository. Choose the menu option 
``Create new repository`` to create a new repository.

.. image:: /images/new_repository.png

You can choose to create a Personal repository or a Central repository.

A personal repository looks the same as a normal working directory but has a directory named ``.git`` at the root level 
containing the version history. This is the most common repository.

Central repositories only contain the version history. Because a central repository has no working directory you cannot 
checkout a revision in a central repository. It is also impossible to merge or pull changes in a central repository. This 
repository type can be used as a public repository where developers can push changes to or pull changes from.


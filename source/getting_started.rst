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

.. image:: /images/install/install2.png

    Git Extensions depends heavily on MsysGit. When MsysGit is not installed, ensure the "Install MsysGit" checkbox is checked. Kdiff3 is 
    optional, but is advised as a merge tool.

.. image:: /images/install/install3.png

.. image:: /images/install/install4.png

    Choose the options to install.

.. image:: /images/install/install5.png

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
any settings to be changed, the settings dialog will be shown. All incorrect settings will be marked in red. 
You can ask Git Extensions to try to fix the setting for you by clicking on it.
When installing Git Extensions for the first time (and you do not have Git already installed on your system), you will normally be required to configure your username 
and email address. 

.. image:: /images/settings/checklist.png

All settings that are specific to Git Extensions will be stored in a file either in the user's application data path or with the program. 
The location is dependant on the IsPortable setting in the GitExtensions.exe.config file that is with the program.
Settings that are used by Git are stored in the configuration files of Git. The global settings are stored in a file called 
``.gitconfig`` in the user directory. The local settings are stored in the ``.git\config`` file of the repository.

.. image:: /images/settings/git.png


The 'Git' tab contains the settings needed to access git repositories. The repositories will be accessed using external 
tools. For Windows usually MsysGit or cygwin are used. Git Extensions will try to configure these settings automatically.

+-----------------------------------------+--------------------------------------------------------------------------+
|Command to run git (git.cmd or git.exe)  | Needed for Git Extensions to run Git commands. Set the full command      |
|                                         | used to run git (MsysGit or cygwin).                                     |
+-----------------------------------------+--------------------------------------------------------------------------+
|Path to Linux tools                      | A few linux tools are used by Git Extensions. When MsysGit is installed, |
|                                         | these tools are located in the bin directory of MsysGit.                 |
+-----------------------------------------+--------------------------------------------------------------------------+

The global configuration file used by git will be put in the home directory. On some systems the home directory is not set 
or is pointed to a network drive. Git Extensions will try to detect the optimal setting for your environment. When there is 
already a global git configuration file, this location will be used. If you need to relocate the home directory for git, 
click the ``Change HOME`` button to change this setting. Otherwise leave this setting as the default.

.. image:: /images/settings/git_extensions.png

The ‘Git Extensions’ tab contains all settings needed for Git Extensions to run properly.

+---------------------------------------------------+----------------------------------------------------------------------------+
|Show repository status in browse dialog (number of | When enabled, the number of pending commits are shown on the toolbar as a  |
|changes in toolbar, restart required)              | figure in parentheses next to the Commit button. Git Extensions must be    |
|                                                   | stopped and restarted to activate changes to this option.                  |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Show current working dir changes in revision graph | When enabled, two extra revisions are added to the revision graph. The     |
|                                                   | first shows the current working directory status. The second shows the     |
|                                                   | staged files. This option can cause slowdowns when browsing large          |
|                                                   | repositories.                                                              |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Use FileSystemWatcher to check if index is changed | Using the FileSystemWatcher to check index state improves the performance  |
|                                                   | in some cases. Turn this off if you experience refresh problems in commit  |
|                                                   | log.                                                                       |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Show stash count on status bar in browse window    | When you use the stash a lot, it can be useful to show the number of       |
|                                                   | stashed items on the toolbar. This option causes serious slowdowns in large|
|                                                   | repositories and is turned off by default.                                 |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Limit number of commits that will be loaded in     | Git Extensions uses lazy loading to load the commit log. Lower this number |
|list at start-up.                                  | to increase the start-up speed. Increase the number for faster scrolling.  |
|                                                   | Turn of revision graph for optimal result!                                 |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Close process dialog automatically when process is | When a process is finished, clause the process dialog automatically. Leave |
|succeeded                                          | this option off if you want to see the result of processes. When a process |
|                                                   | has been failed, the dialog will keep open.When a process is finished,     |
|                                                   | clause the process dialog automatically. Leave this option off if you want |
|                                                   | to see the result of processes. When a process has been failed, the dialog |
|                                                   | will keep open.                                                            |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Show console window when executing git process     | Git Extensions uses command line tools to access the git repository. In    |
|                                                   | some environments it might be useful to see the command line dialog when a |
|                                                   | process is executed.                                                       |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Follow renames in file history (experimental)      | Try to follow file renames in the file history.                            |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Revision grid quick search timeout [ms]            | The timeout (milliseconds) used for the quick search feature in the        |
|                                                   | revision graph. The quick search will be enabled when you start typing and |
|                                                   | the revision graph has the focus.                                          |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Smtp server for sending patches by email           | Smtp server to use for sending patches.                                    |
+---------------------------------------------------+----------------------------------------------------------------------------+

.. image:: /images/settings/appearance.png

+---------------------------------------------------+----------------------------------------------------------------------------+
|Show relative date instead of full date            | Show relative date, e.g. 2 weeks ago, instead of full date.                |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Get author image from gravatar.com                 | Whether or not to retrieve the user avatar from gravatar. This avatar is   |
|                                                   | displayed on the 'commit' tab on the main Commit Log window.               |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Image size                                         | The display size of the user avatar.                                       |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Cache images                                       | Long duration will do less requests but will take more time to update      |
|                                                   | user's avatar changes.                                                     |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Clear image cache                                  | Clear the cached avatars.                                                  |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Fonts                                              | Change the used font.                                                      |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Language (restart required)                        | Choose the language for the Git Extensions interface.                      |
+---------------------------------------------------+----------------------------------------------------------------------------+
|Dictionary for spelling checker                    | Choose the dictionary to use for the spelling checker in the commit dialog.|
+---------------------------------------------------+----------------------------------------------------------------------------+

.. image:: /images/settings/colors.png

In the colors tab the following items can be set:

+-----------------------+-------------------------------------------------------------------------------------------+
|Revision graph colors  | The colors that are used in the revision graph.                                           |
+-----------------------+-------------------------------------------------------------------------------------------+
|Difference view colors | The colors that are used to mark changes.                                                 |
+-----------------------+-------------------------------------------------------------------------------------------+
|Application Icon       | The color of the application icon. This is useful for recognising various open instances. |
+-----------------------+-------------------------------------------------------------------------------------------+

.. image:: /images/settings/start_page.png

The items on the Start Page can be edited. In this tab you can add and remove categories. Per category you can either configure 
a RSS feed or add repositories. The order can be changed using the context menus in the Start Page.
If the title is set (i.e. non-blank), then this will be displayed on the Start Page as a link to your repository. If the title is blank,
then the path of your repository is displayed as a link on the Start Page. Any Description entered will be also be shown
on the Start Page. 

.. image:: /images/settings/global_settings.png

In the ``Global settings`` tab the following global Git settings can be entered.

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

.. image:: /images/settings/ssh.png

In the tab ``SSH`` you can configure the SSH client you want Git to use. Git Extensions is optimized for PuTTY. Git Extensions 
will show command line dialogs if you do not use PuTTY and user input is required. Git Extensions can load SSH keys for PuTTY 
when needed.

Start Page
----------

The start page contains the most common tasks, recently opened repositories and favourites. The left side of the start page (Common Actions
and Recent Repositories) is static. The right side of the page is where favourite repositories can be added, grouped under Category headings.

.. image:: /images/start_page.png

**UPTO HERE** Repositories can be moved to favourites using the context menu. Choose edit to add new repositories to any category.

.. image:: /images/move_to_category.png

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
checkout a revision in a central repository. It is also impossible to merge or pull changes to a central repository. This 
repository type can be used as a public repository where developers can push changes to or pull changes from.


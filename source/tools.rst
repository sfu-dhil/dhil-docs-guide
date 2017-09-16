.. _tools:

Documentation Tools
===================

In order to create documentation using Sphinx, it must first be installed and run via the command line. The documentation and updates are then pushed to GitHub.

.. _tools-using-the-command-line:

Using the command line
----------------------

Installing and using Sphinx will require a basic understanding how to use the command line and a few commands. Using Sphinx primarily requires locating and opening the directory (or folder) where the documentation is and performing commands within that directory.

Each operating system has a different set of commands and different ways to access the command line. The instructions below should work for `bash <https://www.gnu.org/software/bash/>`_ using systems like Mac OS X, Linux, and other Unix-ish operating systems. 

For Windows users, the easiest way to follow the guide is to download a bash terminal like `Cygwin <https://cygwin.com/>`_.

In Mac OS X, access to the command line is through a program called Terminal.app, which is always installed in the Utilities folder, inside Applications.

**cd**

Changing directories using the command line is done using the :kbd:`cd` command, which stands for *change directory*. This is followed by a space then the directory you would like to move into.

This looks like this:

.. code-block:: console
  
  $ cd Documents

In this case we would like to change directories to the Documents folder. The :kbd:`$` represents the command line prompt. When inputting commands, you do not include the :kbd:`$`. The first part of this command is :kbd:`cd`, which is the change directory command. This is followed by :kbd:`Documents`, which is the directory we would like to change into.

**pwd**

When you hit enter to input the command, depending on your command line set up, nothing will appear on the screen. To check which directory you are in, you can use the :kbd:`pwd` command, which stands for *print working directory*, in other words the folder you are currently in.

In this case, it would look like this:

.. code-block:: console

  $ pwd
  /Users/your-username/Documents

This shows the full path for your current directory.

If you wish to go up a level to the previous or enclosing directory, you also use the :kbd:`cd` command, but you do not need to input a directory name. In the command line :kbd:`.` represents your current directory and :kbd:`..` represents the parent directory.

To change to the parent directory you can enter the following:

.. code-block:: console

  $ cd ..
  $ pwd
  /Users/your-username

If you then enter :kbd:`pwd` it will show you that you are back in your home directory.

**ls**

If you want to know the contents of a given directory, you can use the :kbd:`ls` command, which stands for *list directory*. When you enter :kbd:`ls` it will show you all the files and directories that are contained within your current directory.

This looks like the following:

.. code-block:: console

  $ ls
  Applications  Desktop  Documents  Downloads  my_thesis.txt

This is helpful for determining what is in your current directory.

.. seealso::

  For a more comprehensive guide to the command line, check out *Learn Code the Hard Way's* `command line crash course <https://learnpythonthehardway.org/book/appendixa.html>`_. 

.. _tools-installing-sphinx:

Installing Sphinx
-----------------

Sphinx is installed via the command line using pip, a package management system for python. To install Sphinx, you must first have both python and pip installed on your computer. To check if you have python installed, enter the following into the command line:

.. code-block:: console

  $ python --version

If you already have python it will return a version number. If unsuccessful it will return "command not found." Make sure you download the latest version of Python 2 rather than Python 3 for legacy support. If you are using a Mac, Python should be installed already. 

Next check if pip is installed by running the following in the command line:

.. code-block:: console

  $ pip --version

This will again return a version number or "command not found." If pip is installed, make sure it is up to date. More information about installing or upgrading pip can be found in the `pip installation documentation <https://pip.pypa.io/en/stable/installing/>`_.

.. seealso::
  
  For information about installing Python modules using pip in a humanities context, see the Programming Historian's `article about using Python and pip <http://programminghistorian.org/lessons/installing-python-modules-pip>`_.

Once python and pip are set up, you can install Sphinx by using the following comand:

.. code-block:: console

  $ pip install Sphinx


More detailed installation instructions can be found in the `Sphinx guide <http://www.sphinx-doc.org/en/stable/tutorial.html>`_.

.. _tools-using-sphinx:

Using Sphinx
------------

To use Sphinx, you will compose and edit the documentation using :ref:`reStructuredText <intro-what-is-restructuredtext>` and .rst files. For more information about text editors, see :ref:`Using reStructuredText <markup-using-restructuredtext>`.

The main directory of your documentation will contain a few files and a source folder. All .rst files you will edit should be created and edited in the source folder. There will be an index.rst that contains the table of contents tree where you link all .rst files you create. 

.. seealso::

  For more information, check out the `First Steps with Sphinx documentation <http://www.sphinx-doc.org/en/stable/tutorial.html#defining-document-structure>`_ and the `TOC tree documentation <http://www.sphinx-doc.org/en/stable/markup/toctree.html>`_.

To create or build the documentation from the reStructuredText markup, you will use the command line. Navigate to the main directory of your documentation. If you :kbd:`ls` inside of this directory, it will look something like this:

.. code-block:: console

  $ ls
  Makefile  Build  make.bat  source

To build a fully formatted version of the documentation, html for example, invoke the following command from within this directory.

.. code-block:: console

  $ make html

After hitting enter, a number of things will appear in the terminal window. If it is successful, the last line will read "Build successful. The HTML pages are in build/html." To view your newly created html documentation, enter the following command:

.. code-block:: console

  $ open build/html/index.html

Windows users may not be able to use the 'open' command. 'explorer' is the next best thing. It will open the directory in the GUI file explorer. 

.. code-block:: console

  $ explorer build/html

Click on the index.html file of your newly created documentation. Congratulations!

.. _tools-using-github:

Using GitHub
------------

All documentation will be stored and updated on GitHub. If you don't already have an account, you can make one on the `GitHub website <https://github.com>`_. If you are completely new to using GitHub, there is a good `video explaining what GitHub <https://www.youtube.com/watch?v=w3jLJU7DT5E>`_ is and how it works.

Before writing documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The first thing you will do after creating your own GitHub account is fork or copy the documentation you will be working on from the DHIL GitHub page to your personal page (click on the 'fork' button on the upper right corner on the project page you want to fork). The next step will be to create your own local copy of the documentation repository on your computer. You can do this using the command line or by using `SourceTree <https://www.sourcetreeapp.com>`_, a free git client. Download and install SourceTree. Another alternative (though currently in beta stage) is the `GitHub Desktop <https://desktop.github.com/>`_. Along with it comes the **Git Bash** -a bash terminal you can use for running Git on command line. Add your GitHub account login details to SourceTree / GitHub Desktop.

Once you have SourceTree or GitHub Desktop installed and linked to your GitHub account, you can then clone or download a copy of the documentation to your local computer. From SourceTree/GitHub Desktop, choose the **Remote** tab. The copy of the documentation you forked on GitHub will appear here. Choose **Clone** and select where you would like to save the local copy of the documentation repository. Once you have done this, you will be able to edit the documentation on your computer.

.. seealso::

  For a step-by-step guide to installing SourceTree, linking it with GitHub, and cloning a remote repository, see the `Install and Set Up SourceTree <https://confluence.atlassian.com/get-started-with-sourcetree/install-and-set-up-sourcetree-847359043.html>`_ documentation.

.. seealso::

  For a step-by-step guide to installing GitHub Desktop, linking it with GitHub, and cloning a remote repository, see the `Install and Set Up GitHub Desktop <https://help.github.com/desktop/guides/getting-started/>`_ documentation.

.. _tools-using-github-after:

After writing documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^

After you have finished writing and editing your documentation, you will need to commit the changes you've made in SourceTree / GitHub Desktop, push it to your remote copy of the repository on GitHub, then submit a pull request on the DHIL GitHub page.

.. seealso::

  For more information on using git within SourceTree, see the `Work using Git <https://confluence.atlassian.com/get-started-with-sourcetree/work-using-git-847359053.html>`_ documentation from SourceTree.

.. seealso::
  For instructions on commiting and pushing the changes, see SourceTree's `Commit and push a change (Git) guide <https://confluence.atlassian.com/get-started-with-sourcetree/commit-and-push-a-change-git-847359114.html>`_ instructions.

.. seealso::
  If you rather choose to use Git Bash to commit and push changes, see GitHub's `Managing files in a repository guide <https://help.github.com/categories/managing-files-in-a-repository/>`_ for instructions.

Once you have pushed your changes to your remote branch, you will then need to initiate a pull request, which asks the creator of the original repository (in this case, the DHIL GitHub account) to approve and incorporate the changes you have made. To do this, navigate to your forked version of the documentation repository on GitHub (now up-to-date with the changes you pushed from SourceTree / GitHub Desktop). In the top-right of the box with all the files listed (below the green "Clone or download" button), there is a **Pull Request** button. Click on this and go through the steps. Once this is finished, the pull request has been made. You will get a notification when the administrator of the DHIL GitHub page either approves or rejects your pull request. 

That's it! You've successfully added your documentation to the DHIL GitHub. Congratulations!
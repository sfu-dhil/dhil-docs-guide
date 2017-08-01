.. _intro:

Introduction
============

Welcome to the DHIL guide to writing documentation!

This guide will introduce you to the basics of creating documentation using Sphinx and reStructuredText. It will go over how to :ref:`use the command line <tools-using-the-command-line>` to :ref:`install and run Sphinx <tools-installing-sphinx>`, how to :ref:`write and format <markup-using-restructuredtext>` the documentation, how to :ref:`build the html files using Sphinx <tools-using-sphinx>`, and finally how to :ref:`upload the documentation <tools-using-github>` to Github.

What is Sphinx?
---------------

`Sphinx`_ is a tool for creating documentation using reStructuredText, a markup language. Sphinx was created for creating Python documentation, but can be used for many other types of projects including projects the DHIL supports and this guide! Sphinx can take a set up files written with the reStructuredText markup and some parameters and output the fully formatted documentation in a variety of formats, in this case, html.

.. _intro-what-is-restructuredtext:

What is reStructuredText?
-------------------------

`reStructuredText`_ is a lightweight markup language similar to `Markdown`_. Similar to html, reStrucuturedText is used for "marking up" a text to convey formatting syntax such a heading level, text formatting, and links. Unlike html, reStructuredText uses plaintext conventions such as underlining a phrase to create a heading, placing text between asterisks to indicate emphasis, or starting lines with an asterisk to create a list. reStructuredText markup can then be parsed by a program like Sphinx to create fully formatted documentation for the web.

For example, a block of reStructuredText markup looks like this::

  reStructuredText Example
  ^^^^^^^^^^^^^^^^^^^^^^^^

  This sentence has a **strong** *emphasis*. Here are a few reasons why:

  * Reason 1
  * Reason 2

    * Reason 2.1
    * Reason 2.2

  * Reason 3

When you use Sphinx to create the documentation, it take the markup above and formats it as it appears below.

reStructuredText Example
^^^^^^^^^^^^^^^^^^^^^^^^

This sentence has a **strong** *emphasis*. Here are a few reasons why:

* Reason 1
* Reason 2

  * Reason 2.1
  * Reason 2.2
  
* Reason 3

For more on reStructuredText formatting see the :ref:`reStructuredText Syntax section <markup-restructuredtext-syntax>`.

How do they work together?
--------------------------

Sphinx is a tool that takes documents formatted using the basic :ref:`reStructuredText markup syntax <markup-restructuredtext-syntax>` and converts them into finished, fully formatted documentation, ready to be put on the web. Sphinx is a command line tool. After :ref:`installing Sphinx <tools-installing-sphinx>`, you can run a series of basic commands to do things like create a new project or build the fully structured html from your reStructuredText files. You compose the documentation using :ref:`reStructuredText <markup-using-restructuredtext>` formatting in a text editor, build the documentation using the :ref:`Sphinx command line tools <tools-using-sphinx>`, and finally view the finished product in a web browser. In short, reStructuredText is the syntax you use to format your documentation, and Sphinx is the tool you use to turn it into html.

.. _Sphinx: http://www.sphinx-doc.org/en/stable/#

.. _reStructuredText: http://docutils.sourceforge.net/rst.html

.. _Markdown: https://en.wikipedia.org/wiki/Markdown
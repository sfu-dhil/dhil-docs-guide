.. _markup-documentation-markup:

Documentation Markup
====================

Sphinx documentation is composed using :ref:`reStructuredText <intro-what-is-restructuredtext>`, a markup language used for creating documentation. 

.. _markup-using-restructuredtext:

Using reStructuredText
----------------------

reStructuredText markup is created in text files with the .rst extension and edited using a text editor. I recommend either `TextWrangler <https://www.barebones.com/products/textwrangler/>`_ or `Sublime <https://www.sublimetext.com>`_. New files can be created by creating a new file in the text editor and saving it with a .rst extension.

reStructuredText composition is based on using a pre-defined set of markup conventions as seen in the :ref:`introduction <intro-what-is-restructuredtext>`. Below you will find a more detailed explanation of some of the more basic reStructuredText usages along with some external resources and guides.

.. _markup-restructuredtext-syntax:

reStructuredText Syntax
-----------------------

Paragraph basics
^^^^^^^^^^^^^^^^

When composing restrucutred text a blank line must be placed before and after most blocks of text. This includes links, headings, and other paragraphs, for example:

.. code-block:: rst
  :linenos:
  
  Paragraph one with a lovely sentence followed by a blank line.
  
  Paragrpah two with another lovely sentence.

Similar to html, ``*emphasis*`` (*italics*) and ``**strong emphasis**`` (**boldface**) can be used by wrapping text one and two asterisks respectively.

List and tables can also be created using reStructuredText syntax. See `paragraphs and inline markup <http://www.sphinx-doc.org/en/stable/rest.html#paragraphs>`_ documentation for more information.

Headings
^^^^^^^^

Headings are created by underlining the heading words with certain characters. For example, :kbd:`===` for headings, :kbd:`---` for subheadings, and :kbd:`^^^` for sub-subheadings. These are then automatically built into the TOC tree.

.. note::

  The underlined characters must be EXACTLY as long as the words they underline. If not, they will register as an error. This means a heading of the word "Heading," which is 9 characters long, would need exactly 9 :kbd:`=`, :kbd:`-`, or :kbd:`^` below it.

See `Sections <http://www.sphinx-doc.org/en/stable/rest.html#sections>`_ documentation for more details.

Links
^^^^^

reStructuredText makes use of both internal and external links to improve navigation within the documentation.

**Internal links**

The easiest way to create internal links is by referencing section beginnings, such as *Headings* or *Links* on this page. To do so, you must create a unique ID to reference the section. For example, if you had a section called "My favourite section" and wanted to create a link to it, you would do the following:

.. code-block:: rst

  .. _my-favourite-section:
  
  My favourite section
  --------------------

In this case, a section link is preceded by :kbd:`..` followed by an underscore (:kbd:`_`) and the link name with no spaces finished with a colon (:kbd:`:`).

To refer to this section elsewhere, you would use the following formatting:

.. code-block:: rst

  This is a paragraph that links to the best part of this documentation. You can find it :ref:`here <my-favourite-section>`.

In this case, you start with the reference tag (:ref:), this is followed by a backtick (`) the text you want displayed inline, angle brackets (<>) that contain the link you previously created without the preceding underscore followed by a final backtick to close the link (`). All together it looks like this:

.. code-block:: rst

  :ref:`inline text <link-without-underscore>`
  
See `ref role <http://www.sphinx-doc.org/en/stable/markup/inline.html#ref-role>`_ documentation for more details.

**External links**

External links can be formatted in a similar manner.

.. code-block:: rst

  This is an inline example of an external link to `SFU <http://www.sfu.ca>`_

In this case, the link starts with a backtick (`) the inline text to display, angle brackets (<>) with the external website inside, followed by a closing backtick (`) and an underscore (_).

External links can also be separated from their target similar to internal links. See `External links <http://www.sphinx-doc.org/en/stable/rest.html#external-links>`_ documentation for more information.

.. hint::

  This entire documentation guide is written using reStructuredText. To see the complete reStructuredText markup syntax for each page, click **Show Source** in the sidebar of each page.

External resources
------------------

The Sphinx documentation is a great resource for any questions about using reStructuredText. `The reStructuredText Primer <http://www.sphinx-doc.org/en/stable/rest.html>`_ Offers a good introduction to most of the basics of reStructuredText and links out to more detailed information for each topic.
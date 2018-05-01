.. _bootstrap:

==========
Bootstrap
==========

The **Bootstrap** Library offers collection of re-usable html, css and javascript code
in order to standardize front-end development for web applications. **Bootstrap** primarily
targets web interface elements such as typography, layout, buttons and etc. In addition,
it makes sure that good front-end development practices are observed along the way,
such as *responsive design* that allows the same application to scale appropriately
to different platforms and browsers, *e.g.* mobile devices.

**DHIL** web projects are built with **Symfony** framework in the back-end. For front-end
development, Symfony comes with Bootstrap support by default. As such, common interface
elements are generated through it. There are some design components that are
frequently used in DHIL web applications and should be mentioned in particular.
Some of them are *tabs* and *popovers*.

.. Note:: Find more about how to use Bootstrap `here <https://getbootstrap.com/docs/3.3/javascript/>`_. Current Bootstrap version in use at DHIL is 3.3

-----
Tabs
-----

Tabs can be used to organize and transition between panes of local content.
This could be useful, for instance, in organizing large forms that contain many
input fields, or long text fields that can be better presented by grouping its
content, since it eliminates the need for scrolling down.

Suppose we have a long table that lists various bibliographic information about a book.
Suppose further that we managed to group this information in the following way:

* Citation information
* Author information
* Entry information

Here’s a sample code to present this using bootstrap tabs. Note that this can be done
in either javascript or markup/html. Here we will implement it using the latter.
The implementation will take place in *twig.html* template file located in the
source directory of your Symfony project e.g. ``src/AppBundle/Resources/views/show.html.twig``

.. code-block:: html

  <!-- Nav tabs: list of tabs -->

    <ul class="nav nav-tabs" role="tablist">

    <li class="active"><a href="#citation" role="tab" data-toggle="tab">Citation</a></li>

    <li><a href="#author" role="tab" data-toggle="tab">Author</a></li>

    <li><a href="#entry" role="tab" data-toggle="tab">Entry</a></li>

  </ul>

  <!-- Tab panes: present the information here -->

  <div class="tab-content">

    <div role="tabpanel" class="tab-pane active" id="citation"> ... </div>

    <div role="tabpanel" class="tab-pane" id="author"> ... </div>

    <div role="tabpanel" class="tab-pane" id="entry"> ... </div>

  </div>


---------
Popovers
---------

Popovers are great for showing small overlays of content, like a field
description or a help text. Bootstrap popover plugin comes as opt-in, meaning
it should be initialized first. In order to do so, first, locate the *form.js* file
of your project, typically at ``src/AppBundle/Resources/public/js/form.js``

Add the line ``$('[data-toggle="popover"]').popover();`` as in:

.. code-block:: javascript

  $(document).ready(function () {
        $(window).bind('beforeunload', windowBeforeUnload);
        $('form').each(formDirty);
        $("a.popup").click(formPopup);
        $("a").each(link);
        $("*[data-confirm]").each(confirm);
        $('[data-toggle="popover"]').popover(); //add this line to enable bootstrap popover
        if (typeof $().collection === 'function') {
            simpleCollection();
            complexCollection();
        }
    });

Then, you can start to use popover markups in your *html.twig* file. Here’s a sample:

.. code-block:: html

  <tr>
    <th> <!-- table heading & popover text goes here -->
      <a href="#" data-toggle="popover"
      data-content="Full title, subtitle, signed author, and edition statement from the title page"
      data-trigger="hover" data-placement="bottom">Title</a>
    </th>
      <td> <!-- table content goes here -->
        {{ title.title }}
      </td>
  </tr>

This highlights the heading text in a table as a popover field. Crucial markup elements we have here are:

* ``data-toggle`` indicates what this data element is (i.e. it's a popover)
* ``data-content`` the content you want to appear as a popover text goes here (i.e. a help text)
* ``data-trigger`` the way in which you want the content to come into view (i.e. when mouse hovers over its link)
* ``data-placement`` the position in which you want the content to appear (i.e. at the bottom)


.. Note:: Field descriptions are taken from their respective project documentation. DHIL projects come with two types of documentation; the internal documentation that aims to inform the development team, while the external documentation aims to inform end users. Which field description is taken from which documentation type depends on where the description is intended to appear. For instance, an edit form that will be only accessible by project personnel should draw its field descriptions from the internal documentation.

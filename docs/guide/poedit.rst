
.. _../pages/guide/poedit#poedit:

Poedit
******

Poedit is a PO editing tool that will run on Linux or Windows.  It has a
reasonably simple interface as well as translation memory.  Its catalogue
manager does not seem logical at first but is powerful in that it allows you to
manage multiple projects.

`Virtaal <http://virtaal.translatehouse.org>`_ can import settings and
translation memory from Poedit.

.. _../pages/guide/poedit#issues:

Issues
======

* Poedit knows a file's encoding from the PO header.  Therefore, if a PO file
  has no header, Poedit opens a file using the system's default encoding.  This
  means that if you're using Windows, and you're opening UTF-8 PO files without
  headers, Poedit will open them in Windows plaintext encoding, and so break
  the files.

* It can only edit PO files.

.. _../pages/guide/poedit#resource:

Resource
========

* `Home page <http://www.poedit.net/>`_
* `Download <http://www.poedit.net/download.php>`_

.. _../pages/guide/poedit#using_poedit:

Using Poedit
============

.. _../pages/guide/poedit#setup:

Setup
-----

When you first run Poedit you will be asked for some information.  These items
are stored in the header of the PO files and include your name, email address,
etc.  The tabbed dialogue that appears needs the following information:

* Personalize: Supply your name and email address
* Editor: you can safely leave these unchanged
* Translation memory: leave unchanged for now
* Parser: unchanged

Click OK and you are presented with the PO editing interface.

.. _../pages/guide/poedit#the_first_time_with_poedit:

The first time with Poedit
--------------------------

Once Poedit is started you will see the translation interface.

Click file open to open and existing PO file.  If you have no PO file or only a
POT file.  Then simply copy the POT file so that it ends in .po

With a PO file open you will see all strings in the top part of the interface.
Strings are shown in different colours:

+---------+-----------------------------------------------------------------+
| Cyan    | untranslated                                                    |
+---------+-----------------------------------------------------------------+
| Yellow  | fuzzy - needs to be examined and might need to be retranslated  |
+---------+-----------------------------------------------------------------+
| White   | translated                                                      |
+---------+-----------------------------------------------------------------+

You translate in the lower half of the interface. The original string or
English string appears in the left.  You type your translations in the bottom
right hand section.  It seems that keyboard navigation does not work properly
so you will have to select each new string with the mouse.

Don't forget to save regularly using Ctrl-S.

Press F1 at anytime for the Poedit user manual.

.. _../pages/guide/poedit#using_poedit:

Using Poedit
------------

FIXME

.. _../pages/guide/poedit#using_the_catalogue_manager:

Using the Catalogue Manager
---------------------------

The catalogue manager allows you to manage projects with multiple PO files. ::

  File -> Catalog manager

Click on create new translation project.  Then for each directory that has PO
files add it to the project.

.. _../pages/guide/poedit#using_translation_memory:

Using Translation Memory
------------------------

FIXME

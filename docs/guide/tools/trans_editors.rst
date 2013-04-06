
.. _../pages/guide/tools/trans_editors#using_po_editing_tools:

Using PO editing tools
**********************

You need a PO editor to edit PO files which is the main format used by Free
Software, it is also the format the the Translate Toolkit uses when converting
Mozilla and OpenOffice.org files for editing

There are a few PO editing tools available.  Your choice really depends on
which platform you are running:

* I use Windows

  * Install `Virtaal <http://virtaal.translatehouse.org>`_, :doc:`Poedit
    </guide/poedit>`, or `IniTranslator
    <http://initranslator.sourceforge.net/wiki/index.php/Main_Page>`_

* I use Linux

  * I use KDE

    * Install or use `Lokalize
      <http://kde.org/applications/development/lokalize>`_ or `Virtaal
      <http://virtaal.translatehouse.org>`_

  * I use Gnome

    * Install or use `Virtaal <http://virtaal.translatehouse.org>`_ or
      `GTranslator <http://projects.gnome.org/gtranslator>`_

* I am not allowed to install software on my computer

  * If possible use a :doc:`web-based <online>` translation tool.  Not all
    translation projects have a web interface for translation. Possible options
    are `Pootle <http://pootle.translatehouse.org>`_, Rosetta and Kartouche.
    `POEditor <http://poeditor.com>`_ is available with a graphic interface.

* I am not allowed to use the web

  * If you cannot install software or use the web then you might want to look
    at using CSV files edited in a spreadsheet.  You will have to have access
    to email though.

.. _../pages/guide/tools/trans_editors#other_alternatives:

Other alternatives
==================
.. toctree::
   :maxdepth: 1
   :hidden:

   xliff_support_by_ms_windows_programs

You may be able to use a text editor to edit PO files, since they are text: 

* **vi** --- You can use the vi editor.  It includes syntax highlighting, but
  you might want to check if there is a `newer version
  <http://www.vim.org/scripts/script.php?script_id=913>`_
* **emacs** --- The Emacs editor has a PO mode for editing PO files.

Or you can try to convert and/or use another format:

* :ref:`CSV <toolkit:csv>` --- You can use a Spreadsheet to edit PO files that
  have been converted into CSV. It works quite well but is not highly
  recommended if you have good access to a PO editor listed above.
* :ref:`XLIFF <toolkit:xliff>` --- This is an emerging translation interchange
  standard.  We will see much more available in this format, convertors are
  being created to move PO files to Xliff and a number of editors both GPL and
  commercial are being made available.  A short report on :doc:`XLIFF support
  for MS Windows  <xliff_support_by_ms_windows_programs>`.

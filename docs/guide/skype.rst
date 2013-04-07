
.. _../pages/guide/skype#skype_localization:

Skype Localization
******************

Arguably the most important VoIP solution that can be localised.  This `Skype
devzone
<http://share.skype.com/sites/devzone/2006/03/localization_tricky_but_import.html>`_
article shows the importance of localisation -- ony 28% of users of Skype make
use of an English interface.

.. _../pages/guide/skype#how_to_localise_skype:

How to localise Skype
=====================

* `Skype Translation <http://forum.skype.com/lofiversion/index.php/f7.html>`_
  forum
* `Adding unsupported languages
  <http://forum.skype.com/lofiversion/index.php/t111756.html>`_ (Windows)

Skype makes use of Qt :ref:`toolkit:ts` files for localisation.  Thus a
compiled :ref:`toolkit:qm` file should bring localisation to your Skype GUI.
Unfortunately, certainly on the Linux builds, Skype does not seem to detect
languages based on the presence of a language file, rather it seems to have a
pre-set list of possible interface languages.  Rather sad as this would have
been an easy GUI to localise based on the power or Qt.

It is possible to update languages that exist within the Skype application.
`This thread <http://forum.skype.com/index.php?showtopic=103444>`_ (in
Hungarian) links to Hungarian `.ts and .qm
<http://forum.skype.com/index.php?act=Attach&type=post&id=13159>`_ files.  In a
Fedora install these are missing and by adding the files Hungarian becomes an
available interface languages.  This does not work though for Afrikaans (even
if the files are renamed), which seems to indicate that the supported languages
are pre-set within the binary.

.. _../pages/guide/skype#skype_translation_memory:

Skype Translation Memory
========================

* `Current <https://developer.skype.com/download/skypestrings>`_ text based
  file -- 2,900 phrases in 28 languages
* Older spreadsheet with `all existing translations
  <http://download.skype.com/share/devzone/AllLangs.zip>`_ (caution most are
  hidden so make sure you apply a filter again to see the others)


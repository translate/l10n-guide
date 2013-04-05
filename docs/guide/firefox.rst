
.. _../pages/guide/firefox#firefox:

Firefox
*******

Firefox is the web browser that was born out of the :doc:`mozilla` project. It
is now their default target and is renowned for its security.

This page contains Firefox-specific localisation notes and issues. You should
read this in conjunction with the :doc:`mozilla` pages as there are some things
shared between Firefox and :doc:`thunderbird` localisation.

As stated on the :doc:`mozilla` page, there are more complete instructions
about the requirements and processes involved in Mozilla localisation on the
`Mozilla L10n <https://wiki.mozilla.org/l10n/home_page>`_ project page.

.. _../pages/guide/firefox#links:

Links
=====
* `Firefox localisation home page on Mozilla wiki
  <http://wiki.mozilla.org/wiki/L10n:Home_Page>`_
* `Building a Native Installer under Windows XP
  <http://www.it46.se/downloads/firefox-swahili/building_firefox_installer_swahili_mini-HOWTO.txt>`_
* Requirements for official build: `Firefox Extras
  <http://wiki.mozilla.org/wiki/L10n:Firefox_Extras>`_

.. _../pages/guide/firefox#settings:

Settings
========

These are configurations not customisations.  These are things that you
**must** change. Remember that you need to go through a formal procedure of
review to commit changes to some of these files in the Mozilla repository,
especially a file like browser/chrome/browser-region/region.properties. This
usually means you need to file a bug, ask for review by setting flags and more
things and put people in CC. Ask at Mozilla for the newest rules.

#. file: ``toolkit/defines.inc.po``

   * entry: ``MOZ_LANG_TITLE``
   * use: Used in the language .xpi in file ``install.rdf``.  Its added to *%s
     Langauge Pack*
   * action: Set to the English name for your language

#. file: ``browser/defines.inc.po``

   * entry: ``MOZ_LANGPACK_CREATOR``
   * use: Used in ``install.rdf``'s creator tag
   * action: Set to the name of the language pack translator eg. a group,
     company or person

#. file: ``browser.inc``

   * entry: ``MOZ_LANGPACK_CONTRIBUTORS``
   * use: Credit those who helped create the language pack
   * action: you need to edit this file directly ie. not the PO file.  Uncomment
     the ``MOZ_LANGPACK_CONTRIBUTORS`` line and make changes as needed.

#. file: ``toolkit/chrome/global/intl.properties.po``

   * entry: ``general.useragent.locale``
   * use: FIXME Assume this is the locale the browser publishes.
   * action: change to your locale ``xx-YY`` (language-COUNTRY) leave out
     country if you don't need that for your language

#. file: ``toolkit/chrome/global/intl.properties.po``

   * entry: ``intl.accept_languages``
   * use: tells a website what languages you prefer your content in
   * action: set the various language settings you require

#. file: ``browser/chrome/browser-region/region.properties.po``

   * entry: ``general.useragent.contentlocale``
   * use: unsure
   * action: change it to your country code

.. _../pages/guide/firefox#customisation:

Customisation
=============

You can change various settings to make the browser more specific to your
locale.  Be aware that some changes are not allowed in official Mozilla
Foundation builds.

TODO

* Default start URL
* Default search engine
* Adding search engines specific to your locale
* Bookmark customisation
* Browser identification
* Accepted languages

.. _../pages/guide/firefox#other_things_to_localise:

Other things to localise
========================

* Web parts. See http://wiki.mozilla.org/L10n:Web_parts
* Google snippets. See `this bugzilla bug
  <https://bugzilla.mozilla.org/show_bug.cgi?id=366268>`_

This extract of an e-mail from Pavel Franc of the Czech team highlights other
pieces of Firefox that need to be localised::

   The Czech (cs-CZ) Thunderbird 1.0 windows builds are ready.
   We do now our QA testing.
    
   ftp://ftp.czilla.cz/test/thunderbird/1.0/
   
   The following files outside chrome were changed in zip archive:
   
     * * README.txt ... translated
     * * talkback-l10n.ini ... translated
     * + cs.aff ... Czech spellchecker
     * + cs.dic ... Czech spellchecker
     * - en-US.aff ... removed
     * - en-US.dic ... removed
     * * rss.rdf ... translated
     * * mailViews.dat ... translated
     * * all-thuderbird.js ... changed useragent.locale
   
   and in installer:
     * * install.js ... changed locale and translated shortcuts
     * * UninstallThunderbird.zip ... translated
     * * 7zSD.sfx ... translated by ResourceHacker

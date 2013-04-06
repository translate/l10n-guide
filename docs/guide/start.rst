
.. _../pages/guide/start#localisation_guide:

Localisation Guide
******************

The general aim of this document is not to replace other well written works but
to draw them together.  So for instance the section on projects contains
information that should help you get started and point you to the documents
that are often hard to find.  The section of translation should provide a
general enough overview of common mistakes and pitfalls.  We have found the
localisation community very fragmented and hope that through this document we
can bring people together and unify information that is out there but in many
many different places.  The one section that we feel is unique is the guide to
developers --- they make assumptions about localisation without fully
understanding the implications, we complain but honestly there is not one place
that can help give a developer and overview of what is needed from them, we
hope that the developer section goes a long way to solving that issue.

.. toctree::
   :maxdepth: 1
   :hidden:

   purpose
   contributing
   credits
   copyright
   editing
   localising_anloc_manual

* :doc:`purpose`
* :doc:`contributing`
* :doc:`credits`
* :doc:`copyright`

If you would like to help expand this document then please take a quick look at
our :doc:`editing guidelines <editing>`.

.. _../pages/guide/start#start_here:

Start here
==========

If you want some general introductory material about working on the
localisation of Free and Open Source Software, maybe you want to have a look at
this book produced by the African Network for Localisation:

http://www.africanlocalisation.net/foss-localisation-manual

It is available in English and other languages [#f1]_. These wiki pages here
tend to be more detailed, less structured and sometimes more technical.

.. _../pages/guide/start#reading_list:

Reading List
============
.. toctree::
   :maxdepth: 1
   :hidden:

   general_articles

Some useful reading for the soon to be and established localisers.  Please add
good useful articles to these lists.

* :doc:`general_articles` - as yet unclassified but interesting

.. _../pages/guide/start#managing_a_translation_effort:

Managing a translation effort
=============================
.. toctree::
   :maxdepth: 1
   :hidden:

   translateathon
   project_objectives
   golden_rules
   message_marking
   direction/profiling
   short_strings_first
   bootup
   existing_glossaries
   creating_glossaries
   custom_web_searches
   translator_skill_requirements
   costing

* Running a :doc:`translateathon`
* Setting direction

  * Philosophical

    * :doc:`Creating project objectives <project_objectives>`
    * :doc:`Golden rules <golden_rules>`

  * Automated methods

    * :doc:`Message marking <message_marking>`
    * :doc:`Profiling <direction/profiling>`

  * Practical

    * :doc:`1, 2, short, long <short_strings_first>`
    * :doc:`Let the bootup process be your guide <bootup>`

* Glossaries

  * :doc:`Existing Glossaries <existing_glossaries>`
  * :doc:`creating_glossaries`
  * :doc:`custom_web_searches`

* Translators

  * :doc:`Skills required <translator_skill_requirements>`

* :doc:`costing`

.. _../pages/guide/start#project_specific_information:

Project specific information
============================
.. toctree::
   :maxdepth: 1
   :hidden:

   gnome_desktop
   kde_desktop
   xfce
   mozilla
   firefox
   thunderbird
   openoffice.org
   debian
   fedora
   project/mandrake
   suse
   wikis
   project/howto
   google
   skype
   project/manpages

* Desktop Systems

  * :doc:`GNOME <gnome_desktop>`
  * :doc:`KDE <kde_desktop>`
  * :doc:`xfce`

* Major Applications

  * :doc:`mozilla`: :doc:`firefox`, :doc:`thunderbird`
  * :doc:`openoffice.org`

* Distributions

  * :doc:`debian`
  * :doc:`fedora`/Red Hat
  * :doc:`Mandriva <project/mandrake>`
  * :doc:`suse`

* :doc:`wikis`
* :doc:`The Translation Project <project/howto>` (some parts need to move
  to other sections)
* Other

  * :doc:`google`
  * :doc:`skype`
  * :doc:`Man pages <project/manpages>`
  * `WINE <http://wiki.winehq.org/Translating>`_
  * `ReactOS <http://www.reactos.org/wiki/index.php/Translation_Introduction>`_
    - Microsoft Windows clone
  * `OpenMoko <http://wiki.openmoko.org/wiki/Translation_HOWTO>`_

.. _../pages/guide/start#translation:

Translation
===========
.. toctree::
   :maxdepth: 1
   :hidden:

   translation_guidelines
   word_definitions
   translation/commonerrors
   pofilter_examples
   translation/accelerators
   translation/plurals
   translation/variables
   translation/variables
   translation/equations
   translation/program_syntax
   translation/paths_urls
   translation/html
   translation/escaping
   translation/casual_language
   translation/capitalisation
   translation/creating_new_words
   translation/brandnames
   translation/program_names
   translation/punctuation
   translation/problem_words
   british_english
   testing

* Per language :doc:`translation_guidelines`
* Online resource for :doc:`word_definitions`
* When translating

  * :doc:`Common translation errors <translation/commonerrors>` with
    :doc:`pofilter_examples`
  * :doc:`Accelerator keys <translation/accelerators>`
  * :doc:`Plurals <translation/plurals>`
  * :doc:`Variables <translation/variables>`
  * :doc:`Equations <translation/equations>`
  * :doc:`Program syntax and spreadsheet functions
    <translation/program_syntax>`
  * :doc:`Paths and example URLs <translation/paths_urls>`
  * :doc:`What bits of HTML to translate <translation/html>`
  * :doc:`Escaping <translation/escaping>`
  * :doc:`Casual Language <translation/casual_language>`
  * :doc:`Capitalisation <translation/capitalisation>`
  * :doc:`Creating new words <translation/creating_new_words>`
  * :doc:`Brand names <translation/brandnames>`
  * :doc:`Program names <translation/program_names>`
  * :doc:`Punctuation <translation/punctuation>`
  * :doc:`Words that you should watch out for
    <translation/problem_words>`

* :doc:`british_english`
* :doc:`Testing Translations <testing>`

.. _../pages/guide/start#locales:

Locales
=======

.. toctree::
   :maxdepth: 1
   :hidden:

   locales/about
   locale_resource
   locales/glibc
   kde_locale
   locales_x11

* :doc:`All about locales <locales/about>`
* :doc:`Resource for locale data content <locale_resource>`
* Creating locale files

  * :doc:`locales/glibc`
  * `OpenOffice.org <http://www.khmeros.info/tools/openoffice_locale_.htm>`_
  * CLDR
  * :doc:`KDE <kde_locale>`
  * `Solaris <http://developers.sun.com/dev/gadc/faq/locale.html>`_

* :doc:`Patching X11 to accept your locale files <locales_x11>`

.. _../pages/guide/start#tools:

Tools
=====

.. _../pages/guide/start#translation_tools:

Translation Tools
-----------------
.. toctree::
   :maxdepth: 1
   :hidden:

   tools/trans_editors
   tools/comparison
   tools/list
   tools/online
   tools/spreadsheet

* Choosing a :doc:`translation editor <tools/trans_editors>`
* :doc:`Comparison Chart <tools/comparison>`
* :doc:`A list of available tools <tools/list>`
* :doc:`Online or web-based tools <tools/online>`
* :doc:`Using your spreadsheet to translate <tools/spreadsheet>`

.. _../pages/guide/start#glossary_tools:

Glossary Tools
--------------

.. toctree::
   :maxdepth: 1
   :hidden:

   tools/glossary

* :doc:`Glossary creation and management <tools/glossary>`
* `TranslateIt <http://mac.gettranslateit.com/>`_ on OSX provides system-wide
  translation into single or multiple languages, as well as glossary creation

.. _../pages/guide/start#source_control:

Source Control
--------------

.. toctree::
   :maxdepth: 1
   :hidden:

   cvs
   tortoise
   wincvs
   svntips

* Using :doc:`cvs`

  * :doc:`tortoise` and :doc:`wincvs` --- CVS applications for Windows
  * `CrossVC <http://crossvc.com/>`_ -- cross-platform CVS GUI front-end
  * The `BBEdit <http://www.barebones.com/index.shtml>`_ text editor for OSX
    integrates CVS

* `Using SVN <http://svnbook.red-bean.com/en/1.1/>`_

  * An `SVN Summary <http://wiki.gnucash.org/wiki/Subversion>`_ for people
    switching from CVS
  * :doc:`SVN Tips for Translators <svntips>`
  * `svnX
    <http://www.lachoseinteractive.net/en/community/subversion/svnx/features/>`_
    -- intuitive SVN front-end for Mac OSX
  * `PathFinder <http://www.cocoatech.com/>`_ for OSX has an SVN pane, and a
    multi-tab terminal pane
  * The `BBEdit <http://www.barebones.com/index.shtml>`_ text editor for OSX
    integrates SVN

* Using `Git <http://git-scm.com/>`_

  * A `Git-SVN Crash Course <http://git.or.cz/course/svn.html>`_ for people
    switching from SVN
  * How to use `Git at Debian <http://wiki.debian.org/Alioth/Git>`_
  * How to use `Git at GNOME
    <http://live.gnome.org/TranslationProject/GitHowTo>`_

* Using `Bazaar <http://bazaar.canonical.com/DownloadBzr>`_

  * The `Bzr Wiki <http://bazaar.canonical.com/Bzr>`_
  * A `Bzr tutorial <http://bazaar.canonical.com/IntroductionToBzr>`_
  * `Bzr for SVN users <http://bazaar-vcs.org/BzrForSVNUsers>`_

* `Using SSH
  <http://www.sshkeychain.org/mirrors/SSH-with-Keys-HOWTO/SSH-with-Keys-HOWTO.html>`_

  * `SSHKeychain <http://www.sshkeychain.org/>`_ on OSX manages your SSH keys
  * `SSHAgent <http://www.phil.uu.nl/~xges/ssh/>`_ on OSX allows seamless SSH logins
  * `SSH Tunnel Manager <http://projects.tynsoe.org/en/stm/download.php>`_ on
    OSX manages your SSH tunnels (e.g. to OpenOffice.org)

.. _../pages/guide/start#other_tools:

Other tools
-----------
.. toctree::
   :maxdepth: 1
   :hidden:

   gettext_hacks
   statistics
   comparingfiles

* :doc:`gettext_hacks`
* :doc:`statistics` generation
* :doc:`Comparing Files <comparingfiles>` -- how to find changes in
  translations (diffing)

.. _../pages/guide/start#cat_tools_used_by_translators:

CAT tools used by translators
-----------------------------

.. toctree::
   :maxdepth: 1
   :hidden:

   common_cat_tools
   introduction_to_wordfast
   preparing_files_for_wordfast
   translation_memory_with_wordfast
   po_with_wordfast
   preptags
   cafetran
   open_language_tools

* Overview of :doc:`common_cat_tools`, and how they handle l10n files files
* Wordfast

  * :doc:`introduction_to_wordfast`
  * :doc:`preparing_files_for_wordfast`
  * :doc:`translation_memory_with_wordfast`
  * :doc:`po_with_wordfast`

* :doc:`preptags` http://www.preptags.com
* :doc:`cafetran`
* :doc:`open_language_tools`

.. _../pages/guide/start#fonts,_characters_and_rendering:

Fonts, characters and rendering
===============================

.. toctree::
   :maxdepth: 1
   :hidden:

   unicode
   foss_fonts
   ms_core_fonts
   other_fonts
   keyboards
   web-based_font_rendering


* :doc:`unicode`

  * `Unicode Checker <http://earthlingsoft.net/UnicodeChecker/>`_ on OSX
    provides system-wide Unicode codepoint and conversion/normalization
    services
  * `Your Multilingual Mac <http://homepage.mac.com/thgewecke/mlingos9.html>`_
    is a comprehensive Unicode resource

* Fonts

  * `The Unicode Font Guide <http://www.unifont.org/fontguide/>`_
  * :doc:`foss_fonts`
  * :doc:`Microsoft Core Fonts <ms_core_fonts>`
  * :doc:`other_fonts`

* :doc:`keyboards`

  * How to edit `X11 Keymaps
    <http://wiki.services.openoffice.org/wiki/X11Keymaps>`_ or create your own
  * Edit or create OSX keyboard layouts using `Ukelele
    <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ukelele>`_

* Rendering

  * :doc:`web-based_font_rendering`

.. _../pages/guide/start#other_localisation:

Other localisation
==================

.. toctree::
   :maxdepth: 1
   :hidden:

   document_translation
   spelling_checkers
   evaluating_spellcheckers
   spell_checker_case_studies
   hyphenation
   thesaurus
   grammar
   application_specific
   calenders
   weather_applications
   kstars


* :doc:`document_translation`
* Language Tools

  * :doc:`spelling_checkers`

    * :doc:`evaluating_spellcheckers` -- how to evaluate the performance of
      spell checkers
    * :doc:`spell_checker_case_studies` -- Documenting a discussion on
      developing spellcheckers that meet the needs of different languages
    * `Enchant <http://www.abisource.com/projects/enchant/>`_
    * `Hunspell <http://hunspell.sourceforge.net/>`_
    * `Aspell <http://aspell.net/>`_
    * `CocoAspell <http://cocoaspell.leuski.net/>`_ integrates the Aspell
      dictionaries into the OSX system-wide spellchecker

  * :doc:`hyphenation`
  * :doc:`thesaurus`
  * :ref:`Automatic correction <openoffice.org#autocorrect>`
  * :doc:`grammar` checkers

* Other

  * A list of programs with :doc:`application_specific`, non-translation,
    localisation requirements
  * :doc:`calenders`
  * :doc:`weather_applications`
  * :doc:`kstars`

.. _../pages/guide/start#notes_to_programmers:

Notes to programmers
====================

.. toctree::
   :maxdepth: 1
   :hidden:

   programmers/gettext
   plurals_programmers
   variables_programmers
   translation_comments
   unicode_normalization
   unfuzzying
   monolingual
   nonpo

* Other guides

  * `KDE Programmer's i18n howto
    <http://developer.kde.org/documentation/library/kdeqt/kde3arch/kde-i18n-howto.html>`_

* :wiki:`Working with Gettext <programmers/gettext>`
* :doc:`Plurals <plurals_programmers>`
* :doc:`Variables <variables_programmers>`
* :doc:`translation_comments`
* :doc:`unicode_normalization`
* `intltool <http://www.freedesktop.org/wiki/Software/intltool>`_ - used by
  Gnome and others to localise .desktop, .xml, .glade and other file types.
* :doc:`unfuzzying` typo/grammar fixes to original strings
* :doc:`monolingual` formats create certain problems that need resolving for
  localization
* :doc:`nonpo` -- working with non-PO formats

.. rubric:: Footnote

.. [#f1] You can :doc:`help localize the Anloc manual <localising_anloc_manual>`

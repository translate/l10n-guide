
.. _../pages/guide/start#localisation_guide:

Localisation Guide
******************

The general aim of this document is not to replace other well written works but to draw them together.  So for instance the section on projects contains information that should help you get started and point you to the documents that are often hard to find.  The section of translation should provide a general enough overview of common mistakes and pitfalls.  We have found the localisation community very fragmented and hope that through this document we can bring people together and unify information that is out there but in many many different places.  The one section that we feel is unique is the guide to developers --- they make assumptions about localisation without fully understanding the implications, we complain but honestly there is not one place that can help give a developer and overview of what is needed from them, we hope that the developer section goes a long way to solving that issue.

  * :doc:`purpose`
  * :doc:`contributing`
  * :doc:`credits`
  * :doc:`copyright`

If you would like to help expand this document then please take a quick look at our :doc:`editing guidelines <editing>`.

.. _../pages/guide/start#start_here:

Start here
==========

If you want some general introductory material about working on the localisation of Free and Open Source Software, maybe you want to have a look at this book produced by the African Network for Localisation:

http://www.africanlocalisation.net/foss-localisation-manual

It is available in English and other languages. These wiki pages here tend to be more detailed, less structured and sometimes more technical.

.. _../pages/guide/start#reading_list:

Reading List
============

Some useful reading for the soon to be and established localisers.  Please add good useful articles to these lists.

  * :doc:`case studies` - people who have run a localisation project
  * :doc:`localisation introduction` - guides and intros to localisation
  * :doc:`industry articles` - useful articles from the formal localisation industry
  * :doc:`general articles` - as yet unclassified but interesting

.. _../pages/guide/start#managing_a_translation_effort:

Managing a translation effort
=============================

  * Running a :doc:`guide/translateathon`
  * Setting direction
    * Philosophical
      * :doc:`Creating project objectives <project_objectives>`
      * :doc:`Golden rules <golden_rules>`
    * Automated methods
      * :doc:`Message marking <message_marking>`
      * :doc:`Profiling <guide/direction/profiling>`
    * Practical
      * :doc:`1, 2, short, long <short_strings_first>`
      * :doc:`Let the bootup process be your guide <bootup>`
  * Glossaries
    * :doc:`Existing Glossaries <existing_glossaries>`
    * :doc:`creating glossaries`
    * :doc:`custom web searches`
  * Translators
    * :doc:`Skills required <translator skill requirements>`
  * :doc:`costing`

.. _../pages/guide/start#project_specific_information:

Project specific information
============================

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
    * :doc:`Mandriva <guide/project/mandrake>`
    * :doc:`suse`
    * :doc:`ubuntu`
  * :doc:`wikis`

  * :doc:`The Translation Project <guide/project/howto>` (some parts need to move to other sections)
  * Other
    * :doc:`google`
    * :doc:`skype`
    * :doc:`Man pages <guide/project/manpages>`
    * `WINE <http://wiki.winehq.org/Translating>`_
    * `ReactOS <http://www.reactos.org/wiki/index.php/Translation_Introduction>`_ - Microsoft Windows clone
    * `OpenMoko <http://wiki.openmoko.org/wiki/Translation_HOWTO>`_

.. _../pages/guide/start#translation:

Translation
===========

  * Per language :doc:`translation guidelines`
  * Online resource for :doc:`word definitions`
  * When translating
    * :doc:`Common translation errors <guide/translation/commonerrors>` with :doc:`pofilter examples`
    * :doc:`Accelerator keys <guide/translation/accelerators>`
    * :doc:`Plurals <guide/translation/plurals>`
    * :doc:`Variables <guide/translation/variables>`
    * :doc:`Equations <guide/translation/equations>`
    * :doc:`Program syntax and spreadsheet functions <guide/translation/program_syntax>`
    * :doc:`Paths and example URLs <guide/translation/paths_urls>`
    * :doc:`What bits of HTML to translate <guide/translation/html>`
    * :doc:`Escaping <guide/translation/escaping>`
    * :doc:`Casual Language <guide/translation/casual_language>`
    * :doc:`Capitalisation <guide/translation/capitalisation>`
    * :doc:`Creating new words <guide/translation/creating_new_words>`
    * :doc:`Brand names <guide/translation/brandnames>`
    * :doc:`Program names <guide/translation/program_names>`
    * :doc:`Punctuation <guide/translation/punctuation>`
    * :doc:`Words that you should watch out for <guide/translation/problem_words>`
  * :doc:`british english`
  * :doc:`Testing Translations <testing>`

.. _../pages/guide/start#locales:

Locales
=======

  * :doc:`All about locales <guide/locales/about>`
  * :doc:`Resource for locale data content <locale_resource>`
  * Creating locale files
    * :doc:`guide/locales/glibc`
    * `OpenOffice.org <http://www.khmeros.info/tools/openoffice_locale_.htm>`_
    * CLDR
    * :doc:`KDE <kde locale>`
    * `Solaris <http://developers.sun.com/dev/gadc/faq/locale.html>`_
  * :doc:`Patching X11 to accept your locale files <locales_x11>`

.. _../pages/guide/start#tools:

Tools
=====

.. _../pages/guide/start#translation_tools:

Translation Tools
-----------------

  * Choosing a :doc:`translation editor <guide/tools/trans_editors>`
  * :doc:`Comparison Chart <guide/tools/comparison>`
  * :doc:`A list of available tools <guide/tools/list>`
  * :doc:`Online or web-based tools <guide/tools/online>`
  * :doc:`Using your spreadsheet to translate <guide/tools/spreadsheet>`

.. _../pages/guide/start#glossary_tools:

Glossary Tools
--------------

  * :doc:`Glossary creation and management <guide/tools/glossary>`
  * `TranslateIt <http://mac.gettranslateit.com/>`_ on OSX provides system-wide translation into single or multiple languages, as well as glossary creation

.. _../pages/guide/start#source_control:

Source Control
--------------

  * Using :doc:`cvs`
    * :doc:`tortoise` and :doc:`wincvs` --- CVS applications for Windows
    * `CrossVC <http://crossvc.com/>`_ -- cross-platform CVS GUI front-end
    * The `BBEdit <http://www.barebones.com/index.shtml>`_ text editor for OSX integrates CVS
  * `Using SVN <http://svnbook.red-bean.com/en/1.1/>`_
    * An `SVN Summary <http://wiki.gnucash.org/wiki/Subversion>`_ for people switching from CVS
    * :doc:`SVN Tips for Translators <svntips>`
    * `svnX <http://www.lachoseinteractive.net/en/community/subversion/svnx/features/>`_ -- intuitive SVN front-end for Mac OSX
    * `PathFinder <http://www.cocoatech.com/>`_ for OSX has an SVN pane, and a multi-tab terminal pane
    * The `BBEdit <http://www.barebones.com/index.shtml>`_ text editor for OSX integrates SVN
  * Using `Git <http://git-scm.com/>`_
    * A `Git-SVN Crash Course <http://git.or.cz/course/svn.html>`_ for people switching from SVN
    * How to use `Git <http://wiki.debian.org/Alioth/Git>`_ at Debian
    * How to use `Git <http://live.gnome.org/TranslationProject/GitHowTo>`_ at GNOME
  * Using `Bazaar <http://bazaar.canonical.com/DownloadBzr>`_
    * The `Bzr Wiki <http://bazaar.canonical.com/Bzr>`_
    * A `Bzr tutorial <http://bazaar.canonical.com/IntroductionToBzr>`_
    * `Bzr for SVN users <http://bazaar-vcs.org/BzrForSVNUsers>`_
  * `Using SSH <http://www.sshkeychain.org/mirrors/SSH-with-Keys-HOWTO/SSH-with-Keys-HOWTO.html>`_
    * `SSHKeychain <http://www.sshkeychain.org/>`_ on OSX manages your SSH keys
    * `SSHAgent <http://www.phil.uu.nl/~xges/ssh/>`_ on OSX allows seamless SSH logins
    * `SSH Tunnel Manager <http://projects.tynsoe.org/en/stm/download.php>`_ on OSX manages your SSH tunnels (e.g. to OpenOffice.org)

.. _../pages/guide/start#other_tools:

Other tools
-----------
  * :doc:`gettext hacks`
  * :doc:`statistics` generation
  * :doc:`Comparing Files <comparingfiles>` -- how to find changes in translations (diffing)

.. _../pages/guide/start#cat_tools_used_by_translators:

CAT tools used by translators
-----------------------------

  * Overview of :doc:`common cat tools`, and how they handle l10n files files

  * Wordfast
    * :doc:`introduction to wordfast`
    * :doc:`preparing files for wordfast`
    * Download :doc:`various macros for preparing wf files`
  * :doc:`preptags` ` <http://www.preptags.com>`_

  * :doc:`cafetran`
  * :doc:`open language tools`

.. _../pages/guide/start#fonts,_characters_and_rendering:

Fonts, characters and rendering
===============================

  * :doc:`unicode`
    * `Unicode Checker <http://earthlingsoft.net/UnicodeChecker/>`_ on OSX provides system-wide Unicode codepoint and conversion/normalization services
    * `Your Multilingual Mac <http://homepage.mac.com/thgewecke/mlingos9.html>`_ is a comprehensive Unicode resource
  * Fonts
    * `The Unicode Font Guide <http://www.unifont.org/fontguide/>`_
    * :doc:`foss fonts`
    * :doc:`Microsoft Core Fonts <ms_core_fonts>`
    * :doc:`other fonts`
  * :doc:`keyboards`
    * How to edit `X11 Keymaps <http://wiki.services.openoffice.org/wiki/X11Keymaps>`_ or create your own
    * Edit or create OSX keyboard layouts using `Ukelele <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=ukelele>`_
  * Rendering
    * :doc:`web-based font rendering`

.. _../pages/guide/start#other_localisation:

Other localisation
==================
  * :doc:`document translation`
  * Language Tools
    * :doc:`spelling checkers`
      * :doc:`evaluating spellcheckers` -- how to evaluate the performance of spell checkers
      * :doc:`spell checker case studies` -- Documenting a discussion on developing spellcheckers that meet the needs of different languages
      * `Enchant <http://www.abisource.com/projects/enchant/>`_
      * `Hunspell <http://hunspell.sourceforge.net/>`_
      * `Aspell <http://aspell.net/>`_
      * `CocoAspell <http://cocoaspell.leuski.net/>`_ integrates the Aspell dictionaries into the OSX system-wide spellchecker
    * :doc:`hyphenation`
    * :doc:`thesaurus`
    * :ref:`Automatic correction <../pages/guide/openoffice.org#autocorrect>`
    * :doc:`grammar` checkers
  * Other
    * A list of programs with :doc:`application specific`, non-translation, localisation requirements
    * :doc:`calenders`
    * :doc:`weather applications`
    * :doc:`kstars`

.. _../pages/guide/start#notes_to_programmers:

Notes to programmers
====================

  * Other guides
    * `KDE Programmer's i18n howto <http://developer.kde.org/documentation/library/kdeqt/kde3arch/kde-i18n-howto.html>`_
  * :doc:`Working with Gettext <guide/programmers/gettext>`
  * :doc:`Plurals <plurals (programmers)>`
  * :doc:`Variables <variables (programmers)>`
  * :doc:`translation comments`
  * :doc:`unicode normalization`
  * `intltool <http://www.freedesktop.org/wiki/Software/intltool>`_ - used by Gnome and others to localise .desktop, .xml, .glade and other file types.
  * :doc:`unfuzzying` typo/grammar fixes to original strings
  * :doc:`monolingual` formats create certain problems that need resolving for localization


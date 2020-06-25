
.. _../pages/guide/spelling_checkers#spelling_checkers:

Spelling Checkers
*****************

These are an important part of creating a complete language specific view of
the operating system.  Even English speakers prefer to see correct spell
checkers for their locale (UK vs US vs South African).  Certain languages by
their nature do not need or cannot use the traditional wordlist type
spellcheckers found on Linux.

Hunspell is the main spell checker on Linux [#f1]_.

There is a legacy of previous spell checkers on \*nix platforms and these are:

* ispell -- the original word based checker which includes affix compression.
* aspell -- an enhancement of ispell with better algorithms for suggestions
  (newer versions have adopted the myspell affix compression)
* myspell -- originally built for OpenOffice.org and previously also used by
  Mozilla it includes suffix compression (based on the ispell rules but in a new
  format) to produce smaller dictionary sizes.  It runs on all platforms
  supported by OpenOffice.org and Mozilla.
* hunspell -- an enhancement of myspell to allow more sophisticated language
  specific manipulation.  It can use myspell dictionaries thus offering a
  smooth migration path.  It is the default speller in OpenOffice.org, Firefox
  3, Thunderbird 3 and Fedora 9.

If starting from scratch your best bet is to focus on a hunspell checker and
make use of its language specific features if needed.  If you maintain aspell
and ispell checker you might want to migrate them.  If you maintain a current
myspell checker you should probably wait until hunspell infrastructure is
widely deployed.

.. _../pages/guide/spelling_checkers#resource:

Resource
========

* `Scandinavian spell checkers website with some useful tools
  <http://speling.org/>`_.
* `Debian Spellchecker packaging policies
  <http://dict-common.alioth.debian.org/dsdt-policy.html>`_ (`Website
  <http://dict-common.alioth.debian.org/>`_)
* `OpenOffice.org Lingucomponent
  <http://lingucomponent.openoffice.org/spell_dic.html>`_
* `Konjugator <http://www.rhedadur.org.uk/index.php?lg=en>`_ is a browser-based
  conjugator for Welsh verbs.  This might be useful for developing your own
  spelling and grammar checkers in your language.

For spell checker development on OSX, these links might be useful. Just check
that things are still current

* http://developer.apple.com/documentation/Carbon/Conceptual/UnderstandTextInput_TSM/tinptsm_intro/chapter_1_section_1.html
* http://developer.apple.com/samplecode/SpellingChecker-CocoaCarbon/listing3.html
* http://developer.apple.com/documentation/Cocoa/Conceptual/SpellCheck/Tasks/CreatingSpellServer.html

.. _../pages/guide/spelling_checkers#web_based_corpus_building:

Web based corpus building
=========================

A corpus is a body of text used by language researchers and spell checker
builder.  You can find missing or new words for your spell checker by scanning
the web.  There are free tools that you can use to build your own web-based
corpus. We developed :wiki:`CorpusCatcher <corpuscatcher/index>` for this
purpose.

Other possibilities: corpusbuilder and text_cat (FIXME How to use these).  The
former searches the web using a public search engine and the later uses a
statistical model to determine if the text found is indeed in your target
language.

Once you have a list of potential words you can use the *new-words* script in
src/wordlist in the Translate Toolkit SVN to identify words that are not in
your language. Review these words and add them to you master wordlist.

.. _../pages/guide/spelling_checkers#kevin_scannells_-_an_crúbadán:

Kevin Scannell's -- An Crúbadán
-------------------------------

* `An Crúbadán home page <http://borel.slu.edu/crubadan/index.html>`_
* `Geez Crawler <http://www.cs.ru.nl/~biniam/geez/>`_ -- a derivative of *An
  Crúbadán* that is crawling Tigrigna and Amharic

.. _../pages/guide/spelling_checkers#language_detection:

Language detection
------------------

This Python code could easily be used to develop language detection for a
webcrawler: http://aspn.activestate.com/ASPN/Cookbook/Python/Recipe/326576

.. _../pages/guide/spelling_checkers#other_crawlers:

Other Crawlers
--------------

* http://home.hccnet.nl/r.j.baars/ (broken link) -- used we think by the
  `OpenTaal.org <http://opentaal.org/english.php>`_ project

.. _../pages/guide/spelling_checkers#letter_frequencies:

Letter Frequencies
==================

The translate project has a simple python script that creates letter
frequencies that can be used in the MySpell affix files TRY line.  See
translate/src/wordlist/letter-frequency.py in the Translate Toolkit CVS

.. _../pages/guide/spelling_checkers#building:

Building
========

The easiest way to build your spellcheckers is to use our project spellchecker
build framework.  This will build MySpell and Aspell (Ispell temporarily
disabled)  spellcherckers from a common wordlist or wordlists. Look at the
Afrikaans and Zulu dictionaries for a template of the process.  Again this is
in SVN in the *dict* module of the zaf project.

.. _../pages/guide/spelling_checkers#in_more_detail:

In more detail
--------------

Checkout the dict/ module from Subversion::

  svn co https://zaf.svn.sourceforge.net/svnroot/zaf/trunk/dict dict

Directory layout:

* xx/ -- the various language dictionaries

  * Makefile -- various configurations for the spell checker building
  * myspell/ -- myspell dictionary

    * xx_YY.aff -- affix file
    * README_xx_YY.txt -- installation and copyright notices

  * aspell/ -- aspell dictionary

    * info.in -- various configuration settings for aspell
    * Copyright -- Copyright notice

* utils/ -- the various utilities, generic Makefile.languages, aspell build
  routines, myspell build utilities.

Simple make instructions:

* ``make`` -- makes all spell checkers
* ``make myspell`` or ``make aspell`` -- makes the respective dictionary
* ``make count`` -- gives spell checker word counts
* ``make clean`` -- removes all autogenerated files
* ``make wordlist`` -- create and packs the wordlists

.. _../pages/guide/spelling_checkers#making_it_work:

Making it work
==============

Make sure that your language is included in:
http://cvs.gnome.org/viewcvs/gnome-spell/gnome-spell/dictionary.c

So that Gnome applications such as Evolution can make use of your aspell
spellchecker.

.. _../pages/guide/spelling_checkers#publishing:

Publishing
==========

.. _../pages/guide/spelling_checkers#openoffice.org:

OpenOffice.org
--------------

To get the spellchecker onto the OpenOffice.org pages and thus downloadable
from within OpenOffice.org.  You will need to submit a bug report.  Here is and
example issue: http://www.openoffice.org/issues/show_bug.cgi?id=23201

.. _../pages/guide/spelling_checkers#aspell:

ASpell
------

FIXME

.. _../pages/guide/spelling_checkers#mozilla:

Mozilla
-------

Mozilla dictionaries must be tri-licensed (GPL/LGPL/MPL) for inclusion in the
source tree, which results in inclusion in a language build.  For many spell
checkers this will probably be a problem.

Alternatively you can create a dictionary extension and upload it to `Mozilla
Addons <http://addons.mozilla.com>`_.  Users who upgrade Firefox are directed
to the `dictionary download page
<https://addons.mozilla.org/en-us/firefox/browse/type/3>`_ ensuring rapid
adoption of your spell checker.

.. rubric:: Footnotes

.. [#f1] Many distributions consolidated spell checking around Hunspell to some
   extent, for example `Fedora
   <http://fedoraproject.org/wiki/Releases/FeatureDictionary>`_, Firefox,
   Thunderbird and OpenOffice.org use Hunspell.

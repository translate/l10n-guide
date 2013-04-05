
.. _../pages/guide/creating_glossaries#creating_glossaries:

Creating Glossaries
*******************
.. toctree::
   :maxdepth: 1
   :hidden:

   clunky_glossary_creation

When localizing computer software, especially into languages where IT
terminology is not available, new IT terms need to be created. If a glossary of
computer terms does not exist in that language, then one needs to be created as
these terms stand as a 'backbone' in the translation work.

Glossaries can also be created for specific projects (Here is a :doc:`clunky
way of doing it <clunky_glossary_creation>`).

.. _../pages/guide/creating_glossaries#resources:

Resources
=========

* `KiPot <http://www.it46.se/show_entry.php?id=128&lang=es>`_
* `How to make a simple glossary
  <http://www.christophermayo.com/articles/2004/makeglossary.html>`_

.. _../pages/guide/creating_glossaries#how_glossaries_are_created:

How glossaries are created
==========================

The process of creating new terms involves joint work of linguistic and
computer science experts. The development of new IT terms requires that the
linguistic expert fully understands the meaning of the IT term and its context
before trying to match or extend the meaning of a word in the destination
language.

In the words of Alberto of the KiLinux team: "After completing our first
Swahili IT Glossary of 700 terms we understood very quickly two things: the
first is that the glossary of 700 terms requires to be extended constantly and
second the extended glossary requires a constant and fluent communication
between our technical team and Swahili linguistic experts. Oral communication
was never an option since answers were required promtly. Email was not suitalbe
either, since we wanted all participants to have the possibility to take part
in the deveopment of all new tems, which would lead to an enormous amount of
mails sent back and fourth between the projects participants. We needed an
online communication tool that would facilitate the communication, and
therefore, `KiPot <http://www.it46.se/show_entry.php?id=128&lang=es>`_ was
developed."

.. _../pages/guide/creating_glossaries#hacking_a_glossary_from_existing_translation:

Hacking a glossary from existing translation
============================================

One option to create your first cut glossary is to use existing translations
and translatable applications.  

The first step is to create a list of potential glossary words. ::

    $ pogrep --search=msgid -e '^\w+(\s+\w+){0,1}$' -i templates -o short-words
    $ rename .pot .po `find short-words -name "*.pot"`
    $ pocompendium glossary.pot -d short-words/

Optional: edit the POT file to remove words that shouldn't be in the glossary.
See :ref:`toolkit:pogrep` and :doc:`short_strings_first` for more information
on the regex used to extract the words.

Now the glossary POT file is eady for populating.  The next step is to take
your existing translations and populate the POT file to create your first cut
language glossary.  ::

    $ pocompendium compedium-XX.pot -d XX/ # Create a compendium for the XX language
    $ cp glossary.pot glossary.po
    $ msgmerge --compendium=compendium-XX.po --update glossary-XX.po glossary.pot
    $ po2csv glossary-XX.po glossary-XX.csv

Your glossary is now in CSV format in the file glossary-XX.csv

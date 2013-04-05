
.. _../pages/guide/british_english#british_english:

British English
***************

Most programs are written using American English spelling.  It is a simple
process to change the spelling to British English to satisfy the eye of English
speakers in Canada, Australia, South Africa and other commonwealth English
speaking countries.

.. _../pages/guide/british_english#references:

References
==========

These are useful references to the difference between the various English
spellings.

  * http://www3.telus.net/linguisticsissues/BritishCanadianAmerican.htm
  * http://www.musicalenglishlessons.com/spelling-diffs.htm

.. _../pages/guide/british_english#tools:

Tools
=====

To initialise all the POT files to be fully translated:

::

    for pot in `cd templates; find . -name "*.pot"`
    do 
      mkdir -p en_GB/`dirname $pot`
      msginit --locale=en_GB --no-translator -i templates/$pot -o en_GB/`dirname $pot`/`basename $pot .pot`.po
    done 

To examine all potential American spellings use :doc:`toolkit/pofilter`:

::

    pofilter -t musttranslatewords --musttranslatefile=en_US-words-to-change en_GB en_GB-check

If a msgid contains any of the words listed in the files *en_US-words-to-change* then these will be extracted to en_GB-check. 
Correct them and then run:

::

    pomerge -i en_GB-check -o en_GB -t en_GB

.. _../pages/guide/british_english#caution:

CAUTION
=======

This will not check for bad grammar, sentence structure, humour, etc.  You need
a person to do that. But its a start.
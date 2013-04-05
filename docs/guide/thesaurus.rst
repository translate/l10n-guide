When the thesaurus function is activated in a program, it supplies the user
with possible replacements for the highlighted word or word group. It can
indicate the word types, synonyms, related words, abbreviations or complete
forms,  more desirable forms, etc.  

.. _../pages/guide/thesaurus#openoffice.org:

OpenOffice.org
==============
* Download MyThes
* create “dat” file with thesaurus information::

    ISO8859-1
    talented|1
    (adj)|gifted|untalented (antonym)
    talk|7
    (noun)|talking|conversation (generic term)
    (noun)|discussion (generic term)|discourse (generic term)
    (noun)|lecture (generic term)|lecturing (generic term)
    (noun)|lecture|public lecture|speech (generic term)
    (verb)|speak|communicate (generic term)
    (verb)|spill the beans|let the cat out of the bag|keep quiet (antonym)
    (verb)|lecture|teach (generic term)|instruct (generic term)

* run the indexing program that is part of MyThes
* add both the “dat” file and the “idx” file to the “dict” directory in the installation
* add a line like the following to “dictionary.lst”::

    THES en US th_en_US_v2

* restart OpenOffice.org (and the quickstarter in Windows, if used)

Select a word (like "talented" or "talk") and activate the thesaurus. The
thesaurus can be accessed under Tools->Language.

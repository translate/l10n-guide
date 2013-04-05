
.. note::
    A newer tool called :ref:`toolkit:poterminology` is now part of the
    `Translate Toolkit <http://toolkit.translatehouse.org>`_ and should work
    better for all users. This page is only left for reference.

xxx

.. _../pages/guide/clunky_glossary_creation#clunky_method_to_create_glossaries:

Clunky method to create glossaries
**********************************

This old method is for Windows users, but the principles can be applied in
Linux as well.  It is for creating a subject specific glossary in a specific
software translation project.  The idea is to get a list of commonly used
jargon from the project that can be translated beforehand.

.. note::
    Rather use :ref:`toolkit:poterminology` than following these instructions.

xxx

.. _../pages/guide/clunky_glossary_creation#1._extract_the_source_text:

1. Extract the source text
==========================

Take the PO file and do po2csv on it::

  python po2csv file.po file.csv

Open the CSV file in Excel or Calc.

Copy the "original" (or "source") column into a text editor, like `Babelpad
<http://www.babelstone.co.uk/Software/BabelPad.html>`_, and save the file as
text.txt.

.. _../pages/guide/clunky_glossary_creation#2._extract_commonly_occuring_words:

2. Extract commonly occuring words
==================================

Use `ExtPhr32 <http://publish.uwo.ca/~craven/freeware.htm>`_ to extract the
most used terms from it:

* Do not select a stoplist (click "Cancel" when asked)
* Go Options -> Minimum occurances, and select "1"
* Go Options -> Maximum words in phrase, and select "1"
* Go File -> Extract from, and select the file with source text

* In ExtPhr, change the "Minimum occurances" higher and higher until you have
  about 200 terms (or, about 5 occurances should do it).

* Save the result as 5ormore.txt.

.. _../pages/guide/clunky_glossary_creation#3._create_general_common_words_list:

3. Create general common words list
===================================

Create a file containing the 3000 most used words in English.  I used Ogden's
850 words, plus the 3000 words, adjectives, adverbs and pronouns from `here
<http://www.paulnoll.com/Books/Clear-English/>`_, but you could use `Kevin's
lists <http://wordlist.sourceforge.net/>`_ as well (actually, that would be
better because then you could legally distribute it).

.. _../pages/guide/clunky_glossary_creation#4._remove_general_words_from_extracted_common_words_list:

4. Remove general words from extracted common words list
========================================================

Use `Kastrul <http://www.esaro.se/index2.php?LANG=en>`_ to spellcheck the
"5ormore.txt":

* Go File -> Open dictionary, and select your 3000 most common words.
* Go File -> Check file, and select 5ormore.txt
* Copy the result, and save it as glossary.txt.

That is your glossary.  Remember to change it all to lowercase, and to ensure
that dud words are removed.


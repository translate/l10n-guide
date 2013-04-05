
.. _../pages/guide/unicode_normalization#unicode_normalization:

Unicode normalization
*********************

This mostly affects programmers wanting to have search functionality in their
application.

.. _../pages/guide/unicode_normalization#what_is_normalization:

What is normalization?
======================

A composed character in Unicode can often have a number of different ways of
representing the character.  E.g

* Precomposed Ḽ -> U1e3c
* Composed Ḽ = L + ^ -> U004c + U032d

You'll notice that if you where comparing the above two characters that indeed
Ḽ != Ḽ

In order to do correct comparison the characters need to be normalized, thus
they need to be reduced to the same character composition.

.. _../pages/guide/unicode_normalization#normalization_in_my_programming_language:

Normalization in my programming language
========================================

The following show how to normalize your data in various programming languages.

In most cases you don't want to alter the actual stored data but just want to
normalize when comparing data, then throw it away.

.. _../pages/guide/unicode_normalization#python:

Python
------

<code "python">
import unicodedata

string = unicodedata("NFC", string)
</code>

You can replace NFC with NFD, NFCK or NFDK.  Read the Python docs for the
`unicodedata <http://docs.python.org/lib/module-unicodedata.html>`_ module for
more detail on what those options mean.  For most cases it is enough to use the
above to bring the data into the same form and perform your comparison.


.. _../pages/guide/translation/plurals#plurals:

Plurals
*******

Believe it or not some languages have more than one plural form. This fact does
come as a surprise to many, especially programmers.

There are two aspects to plurals that you need to be aware of:

- Those embedded in existing string eg. "file(s)"
- Properly defined plurals forms

.. _../pages/guide/translation/plurals#plurals_embedded_in_strings:

Plurals embedded in strings
===========================

English adds **s** to the end of most words to form a plural.  Thus you will
see many instances where a programmer has simply add **(s)** to the word to
indicate that it can be both singular and plural.  Here is an example in
Tsonga, in this case plurals add/change text at the beginning of the word, not
the end.  This often simply looks ugly. ::

  "Show/Hide Axis Description(s)"
  "Kombisa/Fihla (ti)nhlamuselo ya tikhona"

Furthermore, the grammar in other parts of the sentence might need to agree
with either the singular or the plural case, but can't agree with both.

Here are the options available to you to deal with these type of plurals:

- If your language does not use plurals, you can just translate it disregarding
  the embedded plural.
- Use a similar construct if it works in your language.
- Abandon the singular and use only the plural form.  This is what is done in
  Xhosa where a singular/plural form often involves prefixes so you end up with
  "(i)ifayili" or worse.  So you simply use the plural "iifayili"
- Report the error to the programmer.  Only use this option if this is the case
  for a valid plural i.e. the translator has used some kind of variable e.g.
  "%n file(s)" or two strings follow each other "%n file", "%n files"

.. _../pages/guide/translation/plurals#properly_defined_plural_forms:

Properly defined plural forms
=============================

Programs do have the ability handle plurals correctly.  This is usually
achieved by using the Gettext library or some similar method.  When the
application runs it will determine which plural form to use based on the number
that is being displayed.  So in English it would display:

* 0 files
* 1 file
* 2 files
* 3 files
* etc.

.. _../pages/guide/translation/plurals#gettext_plurals:

Gettext plurals
---------------

Gettext uses the "Plural-Forms" header in the PO file to define:

* ``nplural`` --- the number of plural forms.
* ``plural`` --- an expression which when evaluated determines which form is
  appropriate for that number.  If a definition does not exist for your
  language then you will need to create one or get someone to help you.

Once this is defined then your PO editing tool will display the correct number
of fields for you to enter the plural forms.

A list with these settings in some languages is available :doc:`here
</l10n/pluralforms>`. To find out how to define these entries, see `Plural forms
(gettext manual)
<http://www.gnu.org/software/gettext/manual/html_chapter/gettext_10.html#SEC150>`_

.. _../pages/guide/translation/plurals#historical_kde_plurals:

Historical KDE plurals
----------------------

.. note::

    KDE now uses standard Gettext plurals. This section is just for historical
    reference.

xxx

The plural form for KDE is defined in the kdelibs.po file.  Choose one of the
options or ask for help on their mailing list.

You will recognise KDE plural messages as they all start with "``_n: ``" and
each form is separated by "``\n``".  in your translation you leave out the
"``_n: ``" and include as many translations as there are plural forms in your
language, with each one separated by a "``\n``"

.. _../pages/guide/translation/plurals#language_specific_notes:

Language specific notes
-----------------------
.. toctree::
   :maxdepth: 1

   arabic_plurals

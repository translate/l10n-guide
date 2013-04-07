
.. _../pages/guide/monolingual#monolingual_file_formats:

Monolingual file formats
************************
Monolingual files are files that contain only one language (either the source
language, or the translation). Most documents, including plain text files are
such documents. They are usually written for another purpose that only needs
the one language, and is then replaced entirely with a translated version.

Such files are sometimes used for localisation. It is found in:

* :doc:`The Mozilla project <mozilla>` (:ref:`toolkit:dtd`,
  :ref:`toolkit:properties`, and :ref:`others <toolkit:po2moz>`)
* Websites (:ref:`toolkit:html`) and often in :ref:`toolkit:wiki` pages
* Java projects (mostly :ref:`toolkit:properties` files)
* Applications for OSX and iOS using :ref:`strings <toolkit:strings>` files
* :ref:`Adobe Flex <toolkit:flex>` applications
* :ref:`.ini files <toolkit:ini>`, such as those used for the translation of
  Innosetup installation files
* :ref:`Video subtitles <toolkit:subtitles>`
* :ref:`Windows .rc files <toolkit:rc>`
* Document translation (such as for :ref:`toolkit:odf` or DocBook)
* :ref:`Symbian translation files <toolkit:symb2po>`
* :ref:`toolkit:php` files used for translations

Monolingual files are contrasted with multilingual files that contain the
original source text and the translation in one file. Examples include
:ref:`toolkit:po`, :ref:`toolkit:xliff`, and :ref:`toolkit:ts`.

.. _../pages/guide/monolingual#issues:

Issues
======
Monolingual files for translation present some issues that need to be solved in
any non-trivial translation task. 

.. _../pages/guide/monolingual#tool_support:

Tool support
------------
Many translation tools provide support for translation file formats such as
XLIFF, PO or others, but only some monolingual file formats that the product
chose to support. While many monolingual files can be edited in the tool that
originally created the file (such as a word processor), such a tool might not
be well suited for translation. Particularly, it might have limited or no
support for terminology, translation memory, quality checks, etc.

Furthermore, for any given translation format, there are probably a selection
of translation tools available, from which a translator or team can select the
most appropriate for the circumstances. For many monolingual formats, only the
original authoring tool is available, and provides no choice to translators who
might need specific tools for their language or team.

.. _../pages/guide/monolingual#format_issues:

Format issues
-------------
In the case where no tool or editor is available, translators are exposed to
the raw file format, which might be XML or some other format with extra
information. Such formats are often sensitive to mistakes which can render the
whole file useless and causes an unnecessary debug process just to get the file
in a usable order. Issues related to XML tags, escaping and correct formats are
not always known to translators, and any time spent on these issues just mean
less time for translation and review. Translators might now also have to worry
about line-endings, BOM markers -- things that are not even visible in normal
text editors.

Another consequence of such formats, is that they are usually extremely badly
suited for right-to-left languages like Arabic and Hebrew and provide an
extremely frustrating translation experience where the markup or identifiers
causes complexities with the text now being a mix of left-to-right and
right-to-left text.

Another issue for languages in other scripts than the Latin alphabet, is that
special fonts are required for their own language, but they might not
necessarily have good support for the source text, which can affect readability
of the source text.

.. _../pages/guide/monolingual#estimation:

Estimation
----------
If you don't have your translation work in a translation file format, it might
be hard to quickly get an idea of the size of work required to complete the
task. Tools might be able to count strings, words and more for the translation
formats that they support.

.. _../pages/guide/monolingual#file_updates:

File updates
------------
While you might be able to translate something the first time from the source
text, if the source text is changed, it becomes significantly harder to update
your translation to reflect all additions, removals and changes in the source
text. This is where a translation format or translation memory is required to
perform your update in reasonable time, and in fact, makes this a very easy
operation to perform repeatedly (even automatically).

.. _../pages/guide/monolingual#metadata:

Metadata
--------
Monolingual file formats translators encounter are seldomly intended for
translation, and therefore lacks support for a lot of meta-data that
translators find useful. Examples:

* Comments from a programmer or original author
* Comments from translators
* References to where the text is coming from
* Information about previous or alternate translations
* Translation state, such as "fuzzy", "reviewed" or similar

.. _../pages/guide/monolingual#quality_control:

Quality Control
---------------
While review and quality assurance is often possible for several translation
formats, it is hard to do any formal type of quality control for files that
don't have tool support. It might also be hard to compare your translation to
existing practices in any automated kind of way.

.. _../pages/guide/monolingual#reuse:

Reuse
-----
When using a custom tool, it is often difficult or impossible to reuse
translations from previous translations, and also to reuse your current
translations in other projects.

.. _../pages/guide/monolingual#solutions:

Solutions
=========
Working with monolingual file formats is very common and standard solutions
exist. The monolingual formats are obviously used in many cases as the
appropriate or only formats for documents, web pages, or certain localisation
systems.

.. _../pages/guide/monolingual#convert_to_translation_formats:

Convert to translation formats
------------------------------
This approach assumes that all translation activities will happen in a
translation format such as PO or XLIFF. In this way, a tool converts the
monolingual file to a translation format, and all activities happen in the
translation format. Afterwords the translated file is converted to a
monolingual file in the target language, possibly with help of the original
source file.

This has the advantage that it is easy to generate the target file even if the
translation isn't finished, without having to soil your translation with the
source text that you need to fish out later. For software localisation, this
means you can easily translate your program bit by bit, but keep testing it
even if you have only reached 20% so far.

This is the approach taken by the `Translate Toolkit
<http://toolkit.translatehouse.org>`_, with all the converters that convert to
PO or XLIFF formats. This way the powerful translation tools such as `Virtaal
<http://virtaal.translatehouse.org>`_, `Pootle
<http://pootle.translatehouse.org>`_ and all the tools in the Translate Toolkit
can work on rich translation formats that have all the functionality that
translators expect.

An added advantage is that the translation format can be saved in a version
control system for reference, and all meta-data can be saved along with the
translations.

.. _../pages/guide/monolingual#translation_memory:

Translation Memory
------------------
Although translation memory is a standard tool with translation in any
workflow, an approach taken by some tools to solve the problem of monolingual
file formats make extensive use of translation memory for the solution.

The solution involves "retranslating" the new monolingual file each time by
means of the translation memory that contains the previous translations. In
this case your translation memory needs perfect support for identifying the
correct segment to reuse, and possibly use techniques such as in-context-exact
matching.

This technique is not followed by the `Translate Toolkit
<http://toolkit.translatehouse.org>`_, although some other tools follow this
method. It is not clear to what extent this method allows for powerful
meta-data to be associated with translations for the benefit of translators in
future.

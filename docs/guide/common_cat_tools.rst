
.. _../pages/guide/common_cat_tools#common_cat_tools:

Common CAT tools
****************

Translators often translated documents using so-called CAT (computer aided translation) tools.  Some of the more common CAT tools include Wordfast, OmegaT, Trados, Déja Vù, Metatexis, Isometry, and others.  These tools are typically used to translate ordinary documents, but some of them can also be used to translate l10n formats like PO, CSV, XLIFF and other bilingual formats.

There are two types of CAT tools, namely those that work directly on the source text, and those that work indirectly on the source text by extracting the text from it.

.. _../pages/guide/common_cat_tools#some_cat_tools:

Some CAT tools
==============

.. _../pages/guide/common_cat_tools#omegat:

OmegaT
------

OmegaT is written in Java and is GPL.  It can translate OpenDocument files, well-formed XHTML, Java .properties files, key=value files and plaintext files, as well as a number of other formats.  OmegaT extracts the text from the source documents, and the translator translates the text within the OmegaT environment.  Text formatting is dealt with through special OmegaT tags.

.. _../pages/guide/common_cat_tools#déja_vù:

Déja Vù
-------

`Déja Vù <http://www.atril.com/>`_ is propriatory software (EUR 990 per licence).  It can translate many other propriatory formats and open formats, including Gettext PO.  It works, similar to OmegaT, by extracting text from source files so that the translator works within the program's own environment.

The disadvantage of programs like Déja Vù and OmegaT is that they can only handle existing, well-known text formats.  The advantage is that they usually handle these formats very well or comprehensively.

.. _../pages/guide/common_cat_tools#wordfast:

Wordfast
--------

Wordfast is a Visual Basic macro that runs inside Microsoft Word, and it is propriatory (EUR 250 per licence).  It translates any file that can be opened in Microsoft Word, Excel and PowerPoint.  It does not extract text, but instead it selectively allows the user to translate the portions of the file that needs to be translated.

.. _../pages/guide/common_cat_tools#trados_bilingual_rtf:

Trados (bilingual RTF)
----------------------

The way Trados handles files, is the same as the way Wordfast does it.  In fact, Trados and Wordfast can read each other's files -- that is, the bilingual RTF files.  This is the file type that is most useful for new or rare file formats.  Trados is proprietary

.. _../pages/guide/common_cat_tools#trados_tageditor,_ttx:

Trados (TagEditor, TTX)
-----------------------

A newer method used by Trados is called TagEditor (it produces TTX files).  TTX files are bilingual XML files that are opened translated in TagEditor, which is basically a user-friendly XML-viewer (but it can only view TTX XML files).  In this sense TTX is similar to XLIFF or PO, because it is a bilingual file which is generated from the original file.

.. _../pages/guide/common_cat_tools#features_of_cat_tools:

Features of CAT tools
=====================

CAT tools generally have additional features prized by translators, such as the ability to capture and use a translation memory, automatic on-the-fly fuzzy matching, automatic glossry recognition, various keyboard shortcuts to improve speed, and power reference search facilities.


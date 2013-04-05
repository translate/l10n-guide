
.. _../pages/guide/translation_comments#translation_comments:

Translation Comments
********************

Why do you need translation comments?

Consider this simple case; you have a menu item called "Manual".  You know what
it means, but when the translator sees this they will wonder did you mean:

- a document or help manual, or 
- a manual process?  

This is the simplest case where a translation comment such as "The installation
manual" helps to clarify the situation and makes a translator more productive.

.. _../pages/guide/translation_comments#more_examples_of_the_need_for_translation_comments:

More examples of the need for translation comments
==================================================

Real world examples are best.  This is a discussion over the use of the word
"Forward" in Northern Sotho:

"When you go forward. You go 'Pele', But when you forward the document, O
'Fetišetša pele', so if you just say forward, we don't know what you are
talking about, it is better if it is in a sentence. But in this case i think we
will use 'pele' because on the string no:86 and 88 there is "show previous page
in history" and "show next page in history"

Was there translators guess correct?  I think so, but it makes it so much
easier if they don't need to be super sleuths as well as translators.

.. _../pages/guide/translation_comments#what_should_be_commented:

What should be commented?
=========================

.. _../pages/guide/translation_comments#ambiguous_words:

Ambiguous words
---------------

Words that can be used as a noun or verb in English but may have different
names in another language

.. _../pages/guide/translation_comments#environment_variables,_config_files_entries:

Environment variables, Config files entries
-------------------------------------------

Is it really obvious that TERM should not be translated?

.. _../pages/guide/translation_comments#filenames:

Filenames
---------

Filenames that you do not want translated eg .Xauthority.  Especially if they
appear translatable.

.. _../pages/guide/translation_comments#program_names:

Program Names
-------------

Some sentences do not make it clear that the text refers to a program name
which you probably don't want to translate.

.. _../pages/guide/translation_comments#protocols:

Protocols
---------

Especially when they appear as URIs eg help:index.  Also protocol responses eg.
"Server returned HELO" very tempting to translate.  Or "KEEPALIVE response".
Should KEEPALIVE be translated?

.. _../pages/guide/translation_comments#types_of_comments:

Types of comments
=================

The types of comments depend very much on the localisation system implemented:

.. _../pages/guide/translation_comments#kde_style_comments:

KDE style comments
------------------

The appear to the translator like this:

::

    msgid ""
    "_: The installation manual\n"
    "Manual"

One advantage is that they can double as context strings.  In Gettext PO files
you can only have one translation of the source English word.  So if your
language translates an English word differently depending if it is a noun or a
verb then you will have a problem.  Context information in a KDE style comment
essentially means that the stings are different and thus allows you to
distinguish between verb and nouns spelled the same way in English.

.. _../pages/guide/translation_comments#gettext_comments:

Gettext comments
----------------

These appear in the # comments of a message block.  They are sometimes
overlooked by translators as usually the PO editing tool does not make them
obvious.

.. _../pages/guide/translation_comments#adding_comments:

Adding comments
===============

FIXME not sure how to do it please refer to the Gettext manual and KDE
programmers manual

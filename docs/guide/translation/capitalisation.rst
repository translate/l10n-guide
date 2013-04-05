
.. _../pages/guide/translation/capitalisation#capitalisation:

Capitalisation
**************

What should you do about capitals that you see in the English source translations?  You will notice that English makes use of *Title Case*:

  Save As...
  Find Next
  Bookmark This Page...

Note how almost every word starts with a capital letter.  This is a style often used in English software, especially for titles, buttons and menus. This is also sometimes called "header capitalisation"

What do you do in your language?

.. _../pages/guide/translation/capitalisation#choosing_your_style:

Choosing your style
===================

The first thing to remember is that you should be adapting the software to the conventions of your culture and language.  You do not need to slavishly follow English title case.  By all means if your language follows this convention then use it.  But if is doesn't, then please use the normal case style used in your language.  Very few languages actually use the style of title case as much as English do. Rather just follow the normal rules for capitalisation in your language.

.. _../pages/guide/translation/capitalisation#starting_capitals_or_the_lack_thereof:

Starting capitals or the lack thereof
=====================================

You will notice that certain sentences do not start with a capital.  Try to match these capitals as they are often done for a reason.  Sometimes they represent phrases that will be joined at runtime (this is a bad practice and should be reported to the programmer for correction).

To check your staring capitals use :doc:`toolkit/pofilter`

  pofilter -t startcaps input output

.. _../pages/guide/translation/capitalisation#what_to_do_with_ok:

What to do with 'OK'
====================

In English the **``OK``** or affirmative button is all in capitals.  It is thus tempting to provide a fully capitalised translation in Xhosa that woul dbe **``KULUNGILE``**.  But this looks strange.  Rather abandon the English capitals and use normal capitalisation for your translation ie 
**``Kulungile``**

.. _../pages/guide/translation/accelerators#accelerator_keys:

Accelerator Keys
****************

An *accelerator key* is a key on your keyboard that you can press to quickly
access a menu or function. It is also sometimes called a *hot key*, *access
key* or *mnemonic*.

.. _../pages/guide/translation/accelerators#what_is_an_accelerator_key_and_an_accelerator_marker:

What is an accelerator key and an accelerator marker
====================================================

If you look at the menu bar on any application you will see that the first
letter of each entry in underlined.  Notice that *F*ile, *E*dit and *V*iew each
have the first letter underlined.  To quickly open the File menu press Alt+F.
You will notice that most of the menu entries also have accelerator keys, to
access *O*pen simply type **o** after typing Alt+F.

An *accelerator marker* is the special character we use to mark accelerator
keys when we translate.

.. _../pages/guide/translation/accelerators#identifying_the_accelerator_key:

Identifying the accelerator key
===============================

In translations accelerator keys are shown by various characters:

==========================  =========  =============  ======================  =================  =============================
 Application                 Marker     Name           Source Text Example     Displays As        Note                        
==========================  =========  =============  ======================  =================  =============================
 KDE                          &         ampersand      Save &As...             Save __A__s...                                 
 GNOME                        _         underscore     Save _As...             Save __A__s...                                 
 OpenOffice.org               ~         tilde          Save ~As...             Save __A__s...                                 
 Mozilla                      &         ampersand      Save &As...             Save __A__s...     Using :ref:`toolkit:moz2po`  
 Windows :ref:`toolkit:rc`    &         ampersand      Save &As...             Save __A__s...              
==========================  =========  =============  ======================  =================  =============================

In all of the above examples pressing **A** would take you to the *Save As*
dialogue box.

What happens if you want to use the & character without making it an
accelerator?  In this case the accelerator is usually escaped by using && (for
KDE) or &amp; (for Mozilla). E.g. "Mail && News" or "Mail &amp; News".  As a
translator you would be free to drop the & and use the equivalent of "and" in
your language.

.. _../pages/guide/translation/accelerators#selecting:

Selecting
=========

How do you select an accelerator key for your languages? Keep these principles
in mind:

#. Try to keep it similar to the English. This makes it easier for users to
   switch to localised interfaces.
#. Accelerators should not degrade readability too much.
#. Avoid duplication. Ideally, in any menu, window or dialogue box, a letter
   should only be used as an accelerator for one string. If the letter 'T' is
   used for two menu entries, it is usually not a big problem, but the software
   isn't as usable as it could be.
#. Review accelerators in the running application.

We usually follow these simple rules.

#. Try to keep the same position as the original.  E.g. "&File" -> "&Ifayile"
#. Try to keep the same letter as the original. E.g. "&File" -> "I&fayile"
#. Select an uncommon letter.  In Xhosa the letter I occurs frequently so we try
   to avoid using it too much.
#. Avoid adding accelerators under characters with descenders such as lower case
   g, p, q or y.  The character goes below the base line and could cause the
   character to look odd and the accelerator not to be immediately
   recognisable.  E.g. in KDE &g would appear as *g* which looks messy. It is
   best to confirm with an actual test, since some rendering systems actually
   support underlining clearly when the letter contains a descender.
#. Try to avoid letter next to a descender for similar reasons as above.
#. Avoid narrow letters like i and l.
#. Make sure the character is actually available on the user's keyboard.
   Accented characters such as ä might or might not be present on a keyboard in
   the language.
#. If your language uses diacritics under certain letters such as ț, ḓ or ọ,
   avoid these characters as well, as the underline might run through the
   diacritic.  Avoid letters with diacritics entirely unless you are very sure
   that they will be usable by the end-users.
#. No available character.  Usually in Asian languages where a keyboard is
   Western. Translate the word into your language and use the original English
   accelerator. Ie "&File" -> "XXXX(&F)".  In Mozilla you can safely ignore
   defining the accelerator in which case it will default to the English
   version (FIXME: validate this :)
#. Non-letters like numbers and punctuation marks can be used if they are
   present on a standard keyboard as is common amongst the speakers of your
   language. This will usually only be a relevant choice if it was chosen for
   the source text as well.

.. _../pages/guide/translation/accelerators#accelerator_clashes:

Accelerator Clashes
===================

If we have two accelerator keys using the same letter then we say that we have
a clash.  Assume that the following list are the top three entries in a menu:

* **A**uthor 
* **A**ddress
* Available **A**ctions...

You will notice that all the accelerators use the **A** key --- this is a
clash.  Fortunately most applications will cycle through the options as you
press A repeatedly.  But what would happen if the 3rd item appeared first? (The
third item uses the ellipses (...) to indicate that a dialogue box will open.
This if this appeared first you would never be able to access the other items.

Here is a better choice of accelerators for the same menu:

* **A**uthor 
* A**d**dress
* Available A**c**tions...

We now use **A**, **d** and **c** --- there are no conflicts.

.. _../pages/guide/translation/accelerators#examples:

Examples
========

===========================  ===================================  ===============================  ============================================================================================================================================================================================================================================================================================================================================================================================================================
 English                      Bad                                  Good                             Why?                                                                                                                                                                                                                                                                                                                                                                                                                         
===========================  ===================================  ===============================  ============================================================================================================================================================================================================================================================================================================================================================================================================================
 __X__ Axis...                __K__hona ya X...                    Khona ya __X__...                This accelerator appears nicely on the letter X in the English.  The translator slavishly followed the first rule of keeping the accelerator in the same position.  Yet the good version, which follows rule 2, is much better as it keeps the same letter and it also works for the next string which is //"__Y__ Axis..."//                                                                                                
 __8__00x600 pixels           __d__ikarolwana tse 800x600          dikarolwana tse __8__00x600      This follows the previous example.  The translator has continued to use the first letter of the translation even though the number work well in the translation so there was no need to change the accelerator.  It also work with the surrounding translations that cover 1024x768, etc.  With the option chosen by the translator all of these translations would use the __d__ as the accelerator which wouldn't work.    
 URL for __P__erl scripts     URL bakeng sa __m__aqephe a Perl     URL bakeng sa maqephe a Perl     You will notice that Perl is untranslated this is because in Sotho it was decided not to translate the names of computer languages, they're really like brand names.  So here the accelerator appears in English associated with Perl.  Perl appears in the translation and therefore we could simply have transferred it without any worry about accelerator conflicts.                                                     
 An ~example                  Bad~translation                      Good ~translation                This example shows a common error of leaving out a space between words.  Because the accelerator sometimes in your mind looks like a space its easy to forget to place the space between words in the translation.                                                                                                                                                                                                           
===========================  ===================================  ===============================  ============================================================================================================================================================================================================================================================================================================================================================================================================================

.. _../pages/guide/translation/accelerators#checking:

Checking
========

The :ref:`toolkit:pofilter` tool has an accelerator test.  This will check for missing
accelerators as well as accelerators that shouldn't be in the translation.  The
tool can tell the difference between the various accelerator keys used. ::

  pofilter --mozilla -t accelerators <original> <accelerator-errors>

This will check for Mozilla PO style accelerators (&) in the 'original'
directory and output any errors to a new directory called 'accelerator-errors'

Please check the :ref:`toolkit:pofilter` documentation for more details on how
to use this tool.

.. _../pages/guide/translation/accelerators#errors:

Errors
======

What happens if you select the same accelerator key for two different
components?  How do you check this?

Firstly, it is not a big problem.  Once the application is fully translated
these conflicts should sort themselves out over time.

.. _../pages/guide/translation/accelerators#application_specific_notes:

Application Specific Notes
==========================

.. _../pages/guide/translation/accelerators#kde:

KDE
---

FIXME There are settings that can be used in KDE to check for accelerator
conflicts.  Not sure if any testing is possible in Gnome, OpenOffice or
Mozilla.

.. _../pages/guide/translation/accelerators#openoffice:

OpenOffice
----------

OpenOffice.org seems to have a system that will automatically determine missing
accelerator keys.  What would work best with this system is to mark the
accelerators that you would like to remain static and allow the others to be
automatically determined.  So keep "File", "Edit", "View" accelerators constant
but allow all others to be determined at runtime.

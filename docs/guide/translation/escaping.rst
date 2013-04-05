
.. _../pages/guide/translation/escaping#escaping:

Escaping
********

Escaping is a method that allows us to tell a computer to do something special
with the text we supply or to ignore the special function of a character.  To
tell the computer that it should expect an escape character we use a special
escape marker, we usually make use of the backslash (\).  So an escaped
sequence consists of the escape marker followed by another character.

Although many of these are hidden from you in some tools (such as `Virtaal
<http://virtaal.translatehouse.org>`_), you might still encounter them from
time to time.

In most cases you will see from the original source text when these should be
used, and in many cases you can follow the example of the source text closely.

.. _../pages/guide/translation/escaping#types_of_escape_characters:

Types of Escape Characters
==========================

Each escape sequence has a special meaning:

==================  =========================  ====================================================================================================================================================================================================================================
 Escape Sequence      Effect                    Description                                                                                                                                                                                                                          
==================  =========================  ====================================================================================================================================================================================================================================
 \n                  newline                    Adds a newline at that place in the text (similar to pressing Enter). It might be shown with the ¶ in your translation program.                                                                                                      
 \t                  tab                        Add a tab marker at that spot in the text. This is sometimes used to align text in columns.                                                                                                                                          
 \r                  carriage return            Return without advancing the line This is usually used with \n in software for Windows.                                                                                                                                              
 \\\\                Print a real backslash     If you need a real backslash then you need to escape the backslash. The computer will only print one backslash.                                                                                                                      
 \"                  double quote (")           In some cases a double quote has a special meaning, and should be escaped if you really want a double quote.                                                                                                                         
 \uxxxx              Unicode character          Sometime you want to refer to Unicode characters using normal ASCII.  Many programs and programmers use \u to refer to the Unicode character.  Where xxxx is the hexadecimal or decimal value for the specific Unicode character.    
 &apos;               apostrophe (')            In some XML documents, you might need to represent the apostrophe and some other characters with XML entities. For example '<a href="index.html" title="Rock &apos;n Roll">link</a>'                                                 
==================  =========================  ====================================================================================================================================================================================================================================

.. _../pages/guide/translation/escaping#escape_characters_in_your_translations:

Escape Characters in Your Translations
======================================

====================================  ===============================================================================================================================================  =================================================================================================================================================================================================================================================
 What you see                          What it means                                                                                                                                    What you do                                                                                                                                                                                                                                       
====================================  ===============================================================================================================================================  =================================================================================================================================================================================================================================================
 ...server active.\\nDo you want...     This is easy to recognise as the newline appears between two sentences.  When the program runs the sentences will appear on different lines.     The best option is to place your \n escape in the same place                                                                                                                                                                                      
 ...jobs and/or\\nOLE actions...        This is harder to recognise.  There will be a line break between "and/or" and "OLE".                                                             Look at the structure of the whole translation, in a case like this the author is using newlines to balance the text (i.e. make the lines appear to be equal in length).  If that is the case then balance your translations in a similar way.    
====================================  ===============================================================================================================================================  =================================================================================================================================================================================================================================================

.. _../pages/guide/translation/escaping#dos_and_donts:

Dos and Don'ts
==============

* DO

  * Copy the escape exactly as you see it.
  * Move the placement of escapes if they are being used to balance sentences
  * Make sure you have exactly the same number of escapes as in the original
  * Drop \" or \' escapes if your language does not use the "double" or
    'single' quote method of emphasis that English uses.  Be aware that the
    quality checks by some tools might complain, although the *doublequote* and
    *singlequote* tests of :ref:`toolkit:pofilter` should be aware of your
    language's written rules. Let us know to try to take your language's rules
    into account.
  * Place " or ' around the same **concept** as the English i.e. around the
    same word or words that the English had surrounded.

* DON'T

  * Change the escape in any way.  Do not use **/n** instead of **\n** just
    because you can't find **\\** on your keyboard
  * Confuse sentences like this "File \ Open \ New" as an escape.  If they are
    not in the above list then they are most likely not escape characters.
  * Add or delete spaces around the escape.  If it's there, keep it. If not,
    don't add it.


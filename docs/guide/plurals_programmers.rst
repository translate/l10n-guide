
.. _../pages/guide/plurals_programmers#plurals:

Plurals
*******

What is a plural?  1 file, 2 files, 3 files: file is singular, files plural.
In this simple example we see the English plural form.  Other languages
have simpler or even more elaborate plural forms.
Both KDE and Gettext have a method of managing plurals for PO files so that 
plurals can be used in languages that do not follow the English convention.

.. _../pages/guide/plurals_programmers#why_do_you_need_this_system:

Why do you need this system?
============================

Why not just write a piece of code like this:

::

    if ( n == 1 ) then
    	print "1 file"
    else
    	print "%d files", n

Well the simple answer is that not all languages follow the pluralisation
format of English.  Some use the singular form for both 0 and 1.  Others have
no singular/plural form.  And yet others have complex systems that have at
least 4 plural forms.  For English speakers think of it as the different
suffixes you see here: "1st, 2nd, 3rd, 4th ... 21st, 22nd, 23rd, 24th..."

So in order to cater for the various plural forms a system was developed.

.. _../pages/guide/plurals_programmers#when_to_use_plurals_in_your_application:

When to use plurals in your application
=======================================

If you have numbers in the singular and plural form then use the plural
construct:

  "%n file"
  "%n files"

However, if you do not have number in the construct then rather keep them as
separate strings:

  "Save the file"
  "Save the files"

.. _../pages/guide/plurals_programmers#what_do_plurals_look_like_in_the_po_file:

What do plurals look like in the PO file?
=========================================

On KDE with a 3 plural form language:

::

    msgid ""
    "%n file\n"
    "%n files"
    msgstr ""
    "%n form 1\n"
    "%n form 2\n"
    "%n form 3"

Gettext with a two form language:

::

    msgid "%n file"
    msgid_plural "%n files"
    msgstr[0] "%n form 1"
    msgstr[1] "%n form 2"

Also in Gettext style plurals the PO file header has an entry for the plural
form which defines the number of plurals as well as the mathematical function to
determine which one to use depending on the input number.  Here is an example
which would work for English:

::

    Plural-Forms: nplurals=2; plural=n == 1 ? 0 : 1;

.. _../pages/guide/plurals_programmers#how_to_use_the_plural_construct:

How to use the plural construct
===============================

.. _../pages/guide/plurals_programmers#kde:

KDE
---

FIXME this looks set to change for KDE4 with the Gettext method most probably being adopted

::

    i18n( "One item", "%n items", count); 

Note that because KDE uses a \n to split the different plural forms you cannot
use \n in the actual message.  To work around this you can use KDE's RichText
features and the 
 tag.

.. _../pages/guide/plurals_programmers#gettext:

Gettext
-------

FIXME unsure how this is used
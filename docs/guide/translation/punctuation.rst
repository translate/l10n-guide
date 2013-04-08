
.. _../pages/guide/translation/punctuation#punctuation:

Punctuation
***********

Punctuation is used to indicate various things in program menus e.g.:

* Ellipses (...) -- a dialogue box will appear for further input e.g. "Save
  As..."
* Colon (:) -- usually in a list of entry fields e.g. "Name: "

And sometimes it is simply there for style.

.. _../pages/guide/translation/punctuation#simple_policy:

Simple Policy
=============

Want a simple answer to punctuation?

If your language uses similar punctuation symbols to English, **follow the
English punctuation exactly**

.. _../pages/guide/translation/punctuation#specific_punctuation_issues:

Specific Punctuation Issues
===========================

.. _../pages/guide/translation/punctuation#ellipses_...:

Ellipses (...)
--------------

Ellipses are usually used to indicate that a dialogue box will appear and the
user will be required to give further input.  Compare the menu entries **Save**
with **Save As...**.  You'll notice that 'Save' has no ellipse, the computer
will immediately save the current file and needs no further input from the
user.  While 'Save As...' has an ellipse indicating that the user will be
presented with a dialogue box, this time the Save dialogue box so that they can
supply a new filename.

Make sure that you include all ellipses in your translation.  You might find
that a programmer has used 2 or 4 dots instead of 3: use 3 dots in your
translation and report the error to the programmers.

| \.. --> ...
| .... --> ...

The ellipse always occurs at the end of a message to indicate continuation.
Even if you need to change the word order for your language make sure that the
ellipses occurs at the end of the sentence.

| Blah blee... --> Flee... flah is **WRONG**
| Blah blee... --> Flee flah... is **CORRECT**

.. _../pages/guide/translation/punctuation#fullstops_.:

Fullstops (.)
-------------

We all learnt that sentences should always end in a fullstop.  However, when
translating add a fullstop only if one appears in the English.  If you do not
see a fullstop then do not add one.  The reason for this is simply style, there
is a most probably a reason why the fullstops have been left out, it looks
better.  If during testing you notice that it doesn't work or that there should
be a fullstop then correct appropriately and report the bug.  But in the first
translations simply follow the English.

.. _../pages/guide/translation/punctuation#colons:

Colons (:)
----------

Colons are usually followed by a space and are used to indicate that this is a
label for the adjacent text input box.  Please make sure that you include the
colon and the space is required.

.. _../pages/guide/translation/punctuation#french_style:

French Style
============

It seems to be tradition that the French and Vietnamese place a space between a
word and :;!# e.g.::

  You will delete all your files ! 
  Name :

French also uses a space before ? -- a question mark. Most languages do not
follow this style, so be sure to use the accepted punctuation style in your
language.

One exception is when the last word is a variable::

  Are you sure you want to access %S ?

Which might display as::

  Are you sure you want to access http://example.com ?

In this case it is good that the question mark is separate as it ensures that
you do not think that the question mark is part of the URL or file name filled
into the variable during runtime.

.. _../pages/guide/translation/punctuation#full-width_punctuation:

Full-width punctuation
======================
Some languages, notably Chinese and Japanese, sometimes use full-width
punctuation marks instead of the ones normally used for other languages. It is
also common to **not** use spaces after such symbols, since the full-width
punctuation is usually displayed to be properly spaced. The following table
shows some possible examples where the punctuation is changed, and the space is
removed after the punctuation mark. The way it displays could be influenced by
the fonts used to display this.

============  =============
 English       Full width    
============  =============
 word. word    词语。词语         
 word; word    词语；词语         
 word: word    词语：词语         
 word! word    词语！词语         
 word? word    词语？词语         
============  =============

.. _../pages/guide/translation/punctuation#checking:

Checking
========

You can check your start and end punctuation using :ref:`toolkit:pofilter` ::

  pofilter -t startpunc -t endpunc <input> <output>

Other useful tests are::

  brackets
  startwhitespace
  endwhitespace

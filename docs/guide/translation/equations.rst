
.. _../pages/guide/translation/equations#translating_equations:

Translating Equations
*********************

These are not equations in the mathematical sense but here we refer to items in
the translation that have an equals sign. 

+------------+--------------------------------------------------------------+
| English    | Form contains enctype=%S, but does not contain method=post.  |
|            | Submitting normally with method=GET and no enctype instead.  |
+------------+--------------------------------------------------------------+
| Afrikaans  | Vorm bevat enctype=%S, maar bevat nie method=post nie.  Dien |
|            | soos gewoonlik in met method=GET en sonder enctype in plaas  |
|            | daarvan.                                                     |
+------------+--------------------------------------------------------------+

Usually these equations refer to real values that appear in a programs
configuration file or they refer to items that would appear in the header of
some protocol or email message.  Therefore in the example above neither method=,
enctype=. POST nor GET would be translated.

Lets say that again.  The computer will understand method=POST but will know
nothing about your translation "metode=POS".  Also a user trying to get to the
bottom of an email problem or to find a value in a configuration file will find
method=POST they will not find "metode=POS".

However, it may be acceptable to offer a translation of the values to a user in
brackets if you believe this will add clarity.

.. _../pages/guide/translation/equations#when_should_i_translate_the_right_hand_side_of_an_equation:

When should I translate the right hand side of an equation?
===========================================================

This will be on a case by case basis.  In the example above you would not
translate the right hand side (RHS) as it is a variable value.  However if the
following was presented.

.. code-block:: ini

  Description=A program for highlighting widgets

then you would translate the RHS as is is clearly language specific text.  You
would not translate the LHS no matter how tempting.

.. _../pages/guide/translation/equations#kde_.desktop_files:

KDE .desktop files
==================

Another special case of translating the RHS are the translation of KDE .desktop
files.  These contain only equation like entries.  They all start with "Word="
where word is usually one of "Name, Description,Keyword, etc".  As above do not
translate the LHS but do translate the RHS.


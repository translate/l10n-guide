
.. _../pages/guide/variables_programmers#variables_and_the_localiser:

Variables and the localiser
***************************

To a programmer they're easy, to a localiser well you'll see...
For a great article on these issues see [[http://www.multilingual.com/FMPro?-db=archives&-format=ourpublication%2ffeaturedarticlesdetail.htm&-lay=cgi&-sortfield=magazine%20number&-sortorder=descend&-op=eq&Ad%20Type=reprint&-recid=33324|Text Fragmentation and
Reuse in User Interfaces]] by Richard Ishida

.. _../pages/guide/variables_programmers#commenting:

Commenting
==========

A message that lists 3 variables but doesn't tell anything to the translator
about what the strings will contain does not help a translator.  Even if you
think the contents of the variable are self explanatory think again.

Here is an example of a poorly commented message:

::

    msgid "%s returned %s after %s"

Your guess is as good as mine as to what each of those contain.  Yes the previous and next string might help to determine
what it means.  But we want it translated so lets help the localiser.

A better implmenetation would have the following:

::

    # %s - a URL
    # %s - the error message
    # %s - time as HH:MM:SS since the command was executed
    msgid "%s returned %s after %s"

This explains exactly what each variable will contain.

.. _../pages/guide/variables_programmers#allowing_reordering:

Allowing reordering
===================

English speakers assume that language order will not change.  In many languages
the order of sentences will be different from that of English.  Many systems
allow for variables to be reoordered.  Please ensure that your variables can be
reordered.

A fictitious translation of the above examples may appear like this:

::

    msgid "%s returned %s after %s"
    msgstr "Returning %2s was %1s after %3s"

As you can see by allowing reordering the translator can convery the message in
the structure of their language.

Check with the implementation of Gettext (or other localisation framework) on how to allow for reordering.

.. _../pages/guide/variables_programmers#0_or_o_zero_or_oh:

0 or O (zero or oh)
===================

Don't confuse translators, choose numbers or letters that cannot be confused with other letter or numbers.  In OpenOffice.org
there is a section that has a variables %O (% oh) which almost all translators translate as %0 (% zero) as that is the more logical
option for them, they're used to %1, %2, etc.  If they do not have a font that makes it clear that this is a letter then
they won't see it and they break the translation.
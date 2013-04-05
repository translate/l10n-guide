
.. _../pages/guide/programmers/gettext#working_with_gettext:

Working with Gettext
********************

This is not a replacement of the Gettext `manual <http://www.gnu.org/software/gettext/manual/html_chapter/gettext_toc.html>`_.  

As translators we have written these pages to highlight feature of Gettext that, if used, make our 
lives so much easier.  So please read this realising that if you follow
these ideas you help us improve the localisation of your application.  
And we'll bug you less!

.. _../pages/guide/programmers/gettext#report-msgid-bugs-to:

Report-Msgid-Bugs-To
====================

.. _../pages/guide/programmers/gettext#reason:

Reason
------

As a translator you often have no idea where, how or to whom to report an error found in the source string.
Sometimes we need to tell you to correct spelling or grammar.  We need to ask what the context 
is or we need your help in defining a term we do not understand.  Without a correct email or URL here we have
to guess how to communcicate and spend a large amount of time on the wrong lists trying to
help make the software better.  Please fill it in.

.. _../pages/guide/programmers/gettext#usage:

Usage
-----

The gettext documentation says:

   Report-Msgid-Bugs-To
     This has already been filled in by `xgettext'.

The developer thus needs to pass the option:

::

    --msgid-bugs-address=...

to ``xgettext``. With recent gettext infrastructure this is a field in
``po/Makevars`` that the developer fills in; the rest is automatic.


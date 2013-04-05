
.. _../pages/guide/testing#testing_translations:

Testing Translations
********************

How do you test the translations that you have created?  In some cases it is
almost impossible to quickly test since you need to compile the application.
The following are guides for various systems to allow you to quickly test your
translations.

.. _../pages/guide/testing#cannot_test:

Cannot test
===========

These cannot be quickly tested:

* OpenOffice.org - requires the application be recompiled
* Mozilla Firefox and Thunderbird - requires the creation and installation of
  an XPI

.. _../pages/guide/testing#gettext:

Gettext
=======

This works on Linux or any system where there is a default location for the
compiled PO files.

::

    $ mkdir -p $HOME/.local/share/locale/$your_language_code/LC_MESSAGES
    $ pocompile $your_application.po $HOME/.local/share/locale/$your_language_code/LC_MESSAGES/$your_application.mo

Substitute $your_language_code for your iso639 language code e.g. zu for Zulu.
And substitute $your_application for the application that you are translating
(actually this is the name of the text domain which might be slightly different
from the application name but is usually the same as the PO filename).

Now we have a local repository for storing our custom .mo file.  And we have
compiled one and placed it in the correct location.  You can substitute
``pocompile`` with ``msgfmt`` in the above example.

::

    $ export LANGUAGE=../../../$HOME/.local/share/locale/$your_language_code:$your_language_code
    $ $your_application

This will firstly force us to look into our custom location for MO files and
use those first then fallback to those in the system location.  Now when you
run the application you will see your translations and can quickly test them.


.. _valid_accelerators:

Valid Accelerators
******************

Accelerators are used to allow quick access to items in menus and dialogs.
Usually the user accesses them by pressing :kbd:`Alt+X` where :kbd:`X` is a
character found on their keyboard.

In certain locales a keyboard can accept various characters including those
with diacritics, therefore it is important to gather data for those locales so
that the :ref:`toolkit:pofilter` accelerator check can work well for those
locales.

This mechanism could also be used in locales with multiple keyboards to ensure
that only characters that appear on all keyboards are used in the locale in
which case you might specify a list that is shorter then the normal English.

.. note:: Please enter the full set of characters for your language including
   lower and capital letters.  Start with common Latin characters and add your
   specific diacritics at the end.  Please provide a reason so that future
   language users know why you have chosen the given set if needed.

+-----------+-------------------------------------------------------------------------+-----------------------+
| Language  | Characters                                                              |  Reason               |
+===========+=========================================================================+=======================+
| English   | abcdefghijklmnopqrstuvwxyz ABCDEFGHIJKLMNOPQRSTUVWXYZ 1234567890        |                       |
+-----------+-------------------------------------------------------------------------+-----------------------+
| Finish    | abcdefghijklmnopqrstuvwxyz ABCDEFGHIJKLMNOPQRSTUVWXYZ 1234567890 äöÄÖ   | Bug :bug:`289 <289>`  |
+-----------+-------------------------------------------------------------------------+-----------------------+

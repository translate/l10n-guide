
.. _../pages/guide/gettext_hacks#gettext_hacks:

Gettext Hacks
*************

A few useful Gettext hacks.

.. _../pages/guide/gettext_hacks#branch_merge:

Branch merge
============

Needs to merge translations from a branch back onto HEAD?  ::

    msgmerge -C HEAD.po BRANCH.po HEAD.pot > NEW-HEAD.po
    mv NEW-HEAD.po HEAD.po

Use *HEAD.po* as a compendium to make sure you get any translations that might
have been done in HEAD.  Then migrates *BRANCH.po* to be up-to-date with
*HEAD.pot*.  The output *NEW-HEAD.po* should then be moved to *HEAD.po* if the
merge happened as planned.


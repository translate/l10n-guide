
.. _../pages/guide/kde_locale#kde_locales:

KDE Locales
***********

:doc:`KDE <kde_desktop>`, because it runs on platforms other than Linux, has
created its own locale information environment.  The data stored is similar to
other locales, including date and time formats, etc.

.. _../pages/guide/kde_locale#resource:

Resource
========

* `README for KDE locale files and all the fields in the entry.desktop file
  <http://websvn.kde.org/trunk/KDE/kdebase/l10n/README?view=auto>`_
* `Direcory of all current KDE country locales
  <http://websvn.kde.org/trunk/KDE/kdebase/l10n/?#dirlist>`_
* `South African locale as an example
  <http://websvn.kde.org/trunk/KDE/kdebase/l10n/za/entry.desktop?view=auto>`_

.. _../pages/guide/kde_locale#entry.desktop_file:

entry.desktop file
==================

Most of the entries are self explanatory.  All of the initial **Name[xx]**
entries are supplied by translators for those languages and are most probably
already complete.

Note that **Languages** defines what languages are used in this locale.  Make
sure that the first entry is the language that you want to be the default for
your country.

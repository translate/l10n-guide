
.. _../pages/guide/mozillacvs#translation_for_mozilla_products_based_on_cvs:

Translation for Mozilla products based on CVS
*********************************************

.. _../pages/guide/mozillacvs#introduction:

Introduction
============

Mozilla provides `instructions on starting a localisation <http://wiki.mozilla.org/L10n:Starting_a_localization>`_.

Starting with Firefox 1.0, and later with Firefox 1.5 and Thunderbird 1.5, Mozilla Foundation has the policy to allow only localizations from registered teams. The localizations must be based on their CVS tree, that has an specific structure, and the localization must be given back in their same proper structure, and uploaded in the CVS. The installers and packs are automatically generated via their own tools.

Mozilla Foundation always welcomes contributors, but expects (maybe "requires") that new localizations are based on the newest tree, or not based in old trees (at this time, the 1.0 and 1.5 trees are considered old, and they don't accept new localizations for those trees). Make sure you know what the best target is to base your work on . More info at the Mozilla Wiki: `1 <http://developer.mozilla.org/en/docs/Creating_en-X-dude>`_
`2 <http://wiki.mozilla.org/Draft:L10n:Creating_a_new_Localization>`_.

This document aims to have some bash scripts that, with the translate toolkit installed, automate all the tasks, so you don't have to worry about the inner directories needed for the translation.

.. _../pages/guide/mozillacvs#getting_the_source:

Getting the source
==================

For a better overview, the current composition of the tree for handling these products is:
  * Firefox specific directories
  * Thunderbird specific directories
  * Shared directories (aka "toolkit")

So, for a full Firefox localization, you need the firefox specific components plus the shared components, and the same concept applies for Thunderbird. For that purpose, and to make as easy as possible, here's a bash script that, with proper customization, allows to specify which components to pull, along with the branch version. I call this script ``cvsco.sh``:

::

    #!/bin/bash

    # Custom parameters
    CVSROOT=:pserver:anonymous@cvs-mirror.mozilla.org:/cvsroot
    # CVS tag for 1.5
    TAG=MOZILLA_1_8_BRANCH

    # Set to "" or comment for NOT downloading Firefox needed files
    FF="1"

    # Set to "" or comment for NOT downloading Thunderbird needed files
    TB=""

    # Set to "" or comment for NOT downloading common shared files
    COMMON=""

    # End of custom parameters

    ffox="mozilla/browser/locales/en-US mozilla/extensions/reporter/locales/en-US mozilla/other-licenses/branding/firefox/locales/en-US"
    common="mozilla/dom/locales/en-US mozilla/netwerk/locales/en-US mozilla/security/manager/locales/en-US mozilla/toolkit/locales/en-US"
    tbird="mozilla/editor/ui/locales/en-US mozilla/mail/locales/en-US mozilla/other-licenses/branding/thunderbird/locales/en-US/"

    cvs -d $CVSROOT co ${TAG:+-r $TAG} -P ${COMMON:+ $common} ${FF:+ $ffox} ${TB:+ $tbird}

This script works as is only for the 1.5 version of the products, where the CVS tag is "MOZILLA_1_8_BRANCH". It creates a directory called ``mozilla``, with the selected components. As is, the script only pulls the Firefox specific components. Set the variables as needed for the components you wish, but I suggest to do that in separate source directories, to know later which file belongs to which component. I have a ``firefox/1.5/`` directory for Firefox, and ``thunderbird/1.5`` for this version, having each a copy of this script with already customized variables.

.. _../pages/guide/mozillacvs#creating_pot_files:

Creating pot files
==================

Now we have the necessary files for creating the templates. Run the following to create your POT files:

  make -f tools/l10n/l10n.mka create-en-US
  moz2po -P l10n/en-US pot

Currently we don't convert HTML and XHTML well (this will change over time).  You maight want to use another tools to translate the HTML.

.. _../pages/guide/mozillacvs#dealing_with_translation:

Dealing with translation
========================

If there is some previous work for your locale, or you want to take a look at what files are and how the directory structure looks like, I have another script for this, that I call ``cvscol10n.sh``:

::

    #!/bin/bash
    if [ "$1" = "" ]; then
     exit 0
    fi

    # Set to "" or comment for NOT downloading Firefox needed files
    FF="1"

    # Set to "" or comment for NOT downloading Thunderbird needed files
    TB=""

    # Set to "" or comment for NOT downloading common shared files
    COMMON=""

    CVSROOT=:pserver:anonymous@cvs-mirror.mozilla.org:/l10n
    TAG=MOZILLA_1_8_BRANCH
    ffox="l10n/$1/browser l10n/$1/extensions/reporter/ l10n/$1/other-licenses/branding/firefox/"
    common="l10n/$1/dom/ l10n/$1/netwerk/ l10n/$1/security/manager/ l10n/$1/toolkit/"
    tbird="l10n/$1/editor/ui/ l10n/$1/mail/ l10n/$1/other-licenses/branding/thunderbird/"

    cvs -d $CVSROOT co ${TAG:+-r $TAG} -P ${COMMON:+ $common} ${FF:+ $ffox} ${TB:+ $tbird}

This script needs as argument the locale code you intend to use. It will create a ``l10n/ab-CD`` destination directory with the specified locale. If you're the owner of a locale and/or have a CVS account, make sure you set the $CVSROOT variable with your data when you pull your locale, because if not, you won't be able to upload your changes (without extra actions on your side that require some knowledge). Also, this script performs a checkout, what means that it will likely try to overwrite anything in the destination directory. As long as you don't need to get anybody else's changes on your locale, you don't have to worry about this.

.. _../pages/guide/mozillacvs#converting_files_to_po_for_localization:

Converting files to po for localization
=======================================

If you have not yet created the l10n/en-US files do that as follows:

  make -f tools/l10n/l10n.mk create-en-US

Now to create PO files from your existing translations do:

  moz2po -t l10n/en-US l10n/xx po/xx

This is combine the files in *l10n/en-US* with your localisation of the *xx* language found in *l10n/xx* and place them in *po/xx*.

.. _../pages/guide/mozillacvs#exporting_your_work:

Exporting your work
===================

For exporting your work, you have to run:

  po2moz -t l10n/en-US/ -i po/$lang -o l10n/$lang

Where $lang is your languages.  It will place the exported files in l10/$lang, where you can update and/or commit your changes.

.. _../pages/guide/mozillacvs#updating_from_cvs:

Updating from CVS
=================

Every time you perform an update from CVS (with the ``cvsco.sh`` script), you need to update POT files and/or your translation files.  You can use :doc:`toolkit/pomigrate2` to update your PO files based on these new POT files.

.. _../pages/guide/fedora#translating_fedora:

Translating Fedora
******************

Fedora Core is the community version of Red Hat Linux.  They are both popular Linux
distributions.

.. _../pages/guide/fedora#resources:

Resources
=========

  * :doc:`Mailing list <https///listman.redhat.com/mailman/listinfo/fedora-i18n-list>`
  * `Bugzilla <http://bugzilla.redhat.com/bugzilla/>`_
  * `CVS account request form <http://i18n.redhat.com/cgi-bin/i18n-signup>`_
  * `Translation stats <http://elvis.redhat.com/cgi-bin/i18n-status>`_ (`2 <http://carolina.mff.cuni.cz/~trmac/fedora-i18n.html>`_)
  * `Translation FAQ <http://fedora.redhat.com/participate/translation-faq/>`_

.. _../pages/guide/fedora#what_to_translate_first:

What to Translate First
=======================

Fedora uses the PO format for translation which makes it quite standard. For your language to be 
included you need to reach 90% on the essential files.  The essential file list includes these packages:

  * anaconda/anaconda-online-help/gui (help-screens-C)
  * anaconda/anaconda-po (anaconda)
  * comps-po
  * firstboot
  * rhgb
  * redhat-config-packages (It seems that this has been removed from the essential file list)
  * redhat-artwork
  * redhat-menus

Also look at the :doc:`bootup` process to see other packages that might be important.

.. _../pages/guide/fedora#release_schedule:

Release Schedule
================

Fedora follows a six monthly release schedule which can be viewed `here <http://fedora.redhat.com/participate/schedule/>`_.

Red Hat releases are more conservative and will draw on translations found in
the Fedora Core files.

.. _../pages/guide/fedora#starting:

Starting
========

As usual check on the mailing list to see if anyone is translating your language.  If someone is then work out
a way to combine forces.  If not you will probably become the translation coordinator for your language.  Either way you might want `CVS access <http://qooxdoo.org/fedora#getting_cvs_access>`_.  In order to translate you don't need CVS access.  But you will as soon as you want the data in the applications. 

.. _../pages/guide/fedora#getting_cvs_access:

Getting CVS access
==================

Browse to http://i18n.redhat.com/cgi-bin/i18n-signup where you will have to supply your ssh public key. Use:

  $ sh-keygen -t dsa

if you don't have one. This key is found in 

  $HOME/.ssh/id_dsa.pub

just copy and paste it into the form.

.. _../pages/guide/fedora#getting_the_files_via_cvs:

Getting the files via CVS
=========================

To check out the translate module

  $ cvs -d :ext:YOURUSERNAME@elvis.redhat.com:/usr/local/CVS  co translate

Note: the CVS directory is structured in the GNU way.  Ie you have a POT file and all of the $LANG.po files in one directory.  You may want to make a few scripts to allow PO and TEMPLATE directories per language if that is the way you are used to.  

All files are in HEAD except system-config-packages which uses the
redhat-config-packages-1_1_x branch for Fedora Core 3.

.. _../pages/guide/fedora#per_language_checkout_and_update_scripts:

Per Language Checkout and Update scripts
----------------------------------------

Tools use to update POT and PO files for Fedora on a per langauge basis which
is nicer as otherwise everything is thrown at you.

  * http://mystery.lviv.net/~lvm/fedora-cvs/fedora-cvs-0.3.tar.gz

The tools look like they are from the early days of the Fedora so they might need updating
to be relevant to the latest layout in CVS.

.. _../pages/guide/fedora#enabling_installation_in_your_language:

Enabling installation in your language
======================================

Once you've completed about 90% of the essential modules you can ask for your
language to be included in the installation process.

File an enhancement request to get your language accepted as an anaconda install language.

Here is an example:
https://bugzilla.redhat.com/bugzilla/show_bug.cgi?id=118028

You need to make changes to ``lang-table`` and ``lang-name``

.. _../pages/guide/fedora#checking:

Checking
========

Red Hat treats translations as part of a component not as a global resource.  So you will probably have to check that each item you have translated is included in the final RPM.  You can either install the application and validate or download the beta SRPMS and check.  Installing is easier but requires a large amount of bandwidth.  Downloading the SRPM requires some RPM building experience or at least the ability to read an RPM spec file to check the contents or the ability to check the tarball within the SRPM to validate that your languages are included.

.. _../pages/guide/fedora#additional:

Additional
==========

You might want to check on the following items which relate to localisation:

  * redhat-config-languages
    - check that your language is listed in locale-list.
    - see http://bugzilla.redhat.com/bugzilla/show_bug.cgi?id=107450
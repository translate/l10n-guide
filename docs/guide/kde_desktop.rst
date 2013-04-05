
.. _../pages/guide/kde_desktop#kde:

KDE
***

The KDE Linux desktop is easily localisable and has a very mature localisation
project.

.. _../pages/guide/kde_desktop#resources:

Resources
=========

  * `Localisation Project website <http://i18n.kde.org>`_

.. _../pages/guide/kde_desktop#suggested_priorities:

Suggested Priorities
====================

These are the `priorities <http://i18n.skulelinux.no/prioritering.html>`_ as suggested by the SkuleLinux project.

There is no priority within each of these groups

FIXME this is probably out of date since the move to SVN version control

==========  ===================  =============  ==================
 First       Second               Third          Fourth             
==========  ===================  =============  ==================
 kdebase     kdeaccessibility     kdeaddons      kdeextragear       
 kdelibs     kdeadmin             kdeartwork     kdeextragear-1     
 kdepim      kdeedu               kdegames       kdeextragear-2     
 koffice     kdegraphics          kdetoys        kdenonbeta         
             kdekiosk             docs           others             
             kdemultimedia                                          
             kdenetwork                                             
             kdesdk                                                 
             kdeutils                                               
==========  ===================  =============  ==================

Of course you will probably want to move some applications found in the
kdeextragear modules up.  Or translate them when requested.  Suggested
candidates for bumping up include:
amaroK, kbabel, superkaramba, Scribus, Kopete, Quanta+, 
Kaffeine, Juk, KDevelop, digiKam, kdebluetooth, kontact
and kimdaba

.. _../pages/guide/kde_desktop#compiling_your_language:

Compiling your language
=======================

FIXME update for SVN

If you have made changes or wish to install the latest translations for your
language from CVS do the following after checking out the kde-i18n module from
CVS.

::

    $ cd kde-i18n
    $ echo XX > inst-apps # Where XX is your language's ISO code
    $ make -f Makefile.cvs
    $ ./configure # or ./configure --prefix=/usr if you do not want files installed is /usr/local
    $ make
    $ su -c "make install"

.. _../pages/guide/kde_desktop#updating_all_translations_manually:

Updating all translations manually
==================================

You can update all translations manually instead of waiting for KDE's automatic
update bot called scripty.

::

    $ cd kde-i18n
    $ cvs up templates
    $ VERBOSE=yes make -f Makefile.am.in merge

If you specify your language in a file called "inst-apps" then it will probably only update
your language, which is a good thing.  Have not checked this though.

.. _../pages/guide/kde_desktop#comitting_to_cvs:

Comitting to CVS
================

FIXME fix for SVN

Always check the PO files by running:

::

    $ cd kde-i18n
    $ check_po_files xx

Where xx is your language code.  Also running msgfmt in check mode

::

    $ msgfmt --check -o /dev/null some-file.po

.. _../pages/guide/kde_desktop#checking_accelerators:

Checking accelerators
=====================

You now need to add the following to your kdeglobals in order to use the F12 
accelerator check feature:

[Development]
CheckAccelerators=F12


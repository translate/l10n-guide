
.. _../pages/guide/locales_x11#locales_on_x11:

Locales on X11
**************

X11 it seems does not define its own locales but makes use of the system
locale.  It may only work for a subset of your systems locales because it needs
to know about your locale.  You need to make a few additions to ensure that X11
will recognise your glibc locales.

.. _../pages/guide/locales_x11#various_servers:

Various Servers
===============

There are currently two Xservers for the Free Software world: `XFree86
<http://www.xfree86.org>`_ and `X.org <http://xorg.freedesktop.org/wiki/>`_.
XFree86 is rapidly falling out of favour but in order to cover all of the Linux
distributions you will probably want to patch both of these.

.. _../pages/guide/locales_x11#where_to_find_the_files_to_change:

Where to find the files to change
=================================

You can view these files using CVS web for `XFree86
<http://cvsweb.xfree86.org/cvsweb/xc/nls/>`_ and `X.org
<http://cvs.freedesktop.org/xorg/xc/nls/>`_

We have used the Kinyarawanda example here to illustrate what needs to be
changed.  You can read the bugzilla report for `adding Kinyarawanda to XFree86
<http://bugs.xfree86.org/show_bug.cgi?id=1494>`_.  Here is another example `for
X.org <https://bugs.freedesktop.org/show_bug.cgi?id=1544>`_

.. _../pages/guide/locales_x11#what_needs_changing:

What needs changing
===================

.. _../pages/guide/locales_x11#locale.alias:

locale.alias
------------

The file locale.alias is usually found here::

  /usr/X11R6/lib/X11/locale

This needs to be updated to add all the locale permutations.  Look at a
language similar to yours and add the various permutations.  Here are the lines
that were added to get Kinyarawanda working::

  rw_RW:                 rw_RW.ISO8859-1
  rw_RW.iso8859-1:       rw_RW.ISO8859-1
  rw_RW.ISO88591:        rw_RW.ISO8859-1
  rw_RW.ISO-8859-1:      rw_RW.ISO8859-1
  rw_RW.utf8:            rw_RW.UTF-8

If you are not sure what character sets will be valid then look here to
determine what will work:

* http://www.inference.phy.cam.ac.uk/dasher/download/alphabets/ALPHABETS.html
* http://www.eki.ee/letter/	

.. _../pages/guide/locales_x11#compose.dir:

compose.dir
-----------

::

  iso8859-1/Compose:     rw_RW.ISO8859-1

and also ::

  en_US.UTF-8/Compose:                 rw_RW.UTF-8

Although it looks like the UTF-8 ones do not currently work

.. _../pages/guide/locales_x11#locale.dir:

locale.dir
----------

::

  iso8859-1/XLC_LOCALE:                   rw_RW.ISO8859-1

and also ::

  en_US.UTF-8/XLC_LOCALE:                 rw_RW.UTF-8

.. _../pages/guide/locales_x11#xc/programs/xserver/xpconfig/imakefile:

xc/programs/Xserver/XpConfig/Imakefile
--------------------------------------

This only seems to be relevant to X.org - this defines if your should inherit
paper size from C or en_US.  Add your locale and its permutations to the
correct list.

.. _../pages/guide/locales_x11#new_locales_known_problems:

New Locales: known problems
===========================

.. _../pages/guide/locales_x11#gdm:

gdm
***
Your locale works in any terminal you open from the desktop, but won't be used
in the desktop itself. This happens because of a copy of locale.alias that gdm
holds in /etc/X11/gdm (at least in gentoo).

Add you locale to this file or it will be ignored by gdm.


.. _../pages/guide/direction/profiling#using_profiling_to_aid_direction_setting:

Using profiling to aid direction setting
****************************************

In computer programming the term profiling is used to indicate when a program
is analysed to see where it spends most of its time.  The theory being that
that is where you should put in effort to optimise the code and thus improve
speed and responsiveness.

A similar concept can be applied to translation.  If you translate only the
messages that people actually see then you can optimise the effort that you
expend on translation.

It also helps focus the translation effort onto programs that are actually
being used, not those that you guess might be being used.

.. _../pages/guide/direction/profiling#how_profiling_works_on_linux:

How profiling works on Linux
============================

The gettext libraries are called by a program with a request for the
translation of a given string.  Gettext looks up the string and returns the
translation to the program.

When profiling this call to gettext is intercepted and the message requested is
output to a file.  This file is then later processed and contains all strings
that should be translated.

.. _../pages/guide/direction/profiling#problems_with_profiling:

Problems with profiling
=======================

* Many **UI design tools** and newer UI code calls all strings when
  initialising the UI.  That means that you see many messages that in fact were
  never seen by the user.
* **Spurious files**.  Many GUI program call command line tools to retrieve
  data.  When the command line tool is called those messages are logged but
  were never seen by the user.
* Profiling depends on the **usage profile of the user**.  An end-user and a
  system administrator will use different tools.  To work best you need a group
  of people using your target applications.

.. _../pages/guide/direction/profiling#solutions:

Solutions
---------

* The UI design tools would require changes to only call strings for windows
  that are visible.  But this would only happen if translators can indicate a
  strong case for the fact that they use and find profiling effective.
* You can circumvent the calling of spurious command line tools by GUI tools by
  using::

    export LC_ALL=C

.. _../pages/guide/direction/profiling#using_profiling:

Using profiling
***************

.. _../pages/guide/direction/profiling#gettext:

Gettext
=======

This is the prefered method but it only creates one file.  The gettext manual
has a `good description
<http://www.gnu.org/software/gettext/manual/html_node/Prioritizing-messages.html>`_
of the process.

The simplest first steps are repeated here for clarity::

    $ LD_PRELOAD=/usr/local/lib/preloadable_libintl.so
    $ export LD_PRELOAD
    $ GETTEXT_LOG_UNTRANSLATED=$HOME/gettextlogused
    $ export GETTEXT_LOG_UNTRANSLATED

Use the application, unset the variables and then::

  $ msguniq $HOME/gettextlogused > missing.po

To remove duplicates.  Various domains for each of the applications logged will
be available.  To sort and extract the domains that you wish to edit you should
read the manual pages.

.. _../pages/guide/direction/profiling#gettextlog:

Gettextlog
==========

The Gettextlog tool is available here:

``` <http://sourceforge.net/projects/gettextlog/>`_``

An RPM is also available:

``` <http://prdownloads.sourceforge.net/gettextlog/gettextlog-0.6-1.i386.rpm?download>`_``

Once installed...

  export LD_PRELOAD=/file/to/gettextlog.so

You can place this in your ``.bash_profile`` to log continuously or in
``/etc/profile.d/`` add a ``gettextlog.sh`` script to initialise LD_PRELOAD

You can run it against individual programs with the
``run-with-gettextlog`` program

Your profiles will be output to::

  $HOME/gettextlog/$PROGRAM.po



.. _../pages/guide/golden_rules#the_golden_rules:

The Golden Rules
****************

These are the Golden Rules of localization direction setting initially used by
Translate.org.za.  They are born out of the goal of wanting to have the
greatest potential impact on language speakers with localised Free Software.

There are three rules, software that we translate must be:

- End-user Focused
- Free Software
- Cross-Platform

With these basic rules in mind you can more intelligently select your software
targets.

.. _../pages/guide/golden_rules#end-user_focused:

End-user Focused
================

The person who will most benefit from localized software is the desktop bound
end-user.  It is not the sysadmin or programmer.  These are the people most
likely to have less command of English while sysadmins have probably in the
course of their work had to come to terms with English on the computers that
they use.

This also means that you need to examine what type of software is generally
used by an end-user.  This would include: office suites, email programs and
web-browsers, instant messaging and even games.

.. _../pages/guide/golden_rules#free_software:

Free Software
=============

Again if you want to make the most impact on the most people you need to remove
barriers.  Free Software removes two barriers:

- being Free is the very reason why you can localize the software with relative
  ease (No NDAs, etc), and 
- your localised software is then available to a broad community with easy
  sharing and community based sharing dramatically reducing the cost of
  acquisition.

.. _../pages/guide/golden_rules#cross-platform:

Cross-platform
==============

The reality is that most computer users are using Microsoft Windows.  Until
that changes a heavy focus should be on cross-platform products.  Thus you can
provide a solution to Windows user while at the same time providing an avenue
for them to move to a Free operating system.

It is much easier to provide a localised office suite solution that does not
require a complete retooling of the users operating environment.

.. _../pages/guide/golden_rules#how_translate.org.za_applied_the_golden_rules:

How Translate.org.za applied the Golden Rules
*********************************************

These are the Golden Rules applied to the target selection at Translate.org.za:

- OpenOffice.org
- Mozilla
- A linux desktop
- Installers

Here is the explanation for this choice.  OpenOffice.org is a leading Free
Software, End-user focused and cross-platform piece of software and so meets
all of the 3 requirements.  However, so is Mozilla (and its offspring,
Thunderbird and Firefox).  We place OpenOffice.org before Mozilla because when
using OpenOffice.org you are immersed in the language because you are probably
editing an Afrikaans document while using an Afrikaans interface.  While a
web-browser gives you an Afrikaans window frame onto an English Internet.  the
argument does not apply as well to an email reader such as Thunderbird in that
you are creating content in an email program.  This is when you need to make a
call.

Mozilla is localized before we look at any Linux desktops simply because people
use Windows and Mozilla fills a gap in the needs of the end-user.

Translate.org.za has not made any firm decisions about desktops.  We have
localized both KDE and GNOME in the past and continue to do various depending
on conditions and funding.  The project sees this as an important step in
creating a fully localised Free Software environment but is at a lower priority
while there are still low hanging fruit in the cross-platform area.

We relagate Linux installer and distribution specific localisation to a lower
rung.  Distribution specific configuration programs are problematic in that
they have limited impact to the distribution as apposed to a whole sea of Free
Software users.  But they are important for a seemless end-user experience.
Some of them are also only used once, for example during software installation
making localisation of them wasteful of resources.

Not listed are the localisation of kernel messages and command line tools.
This is moving far beyond the realm of the average end-user and until a growth
is seen in usage in this area they will remain off our radar.

.. _../pages/guide/golden_rules#what_to_do_as_a_single_person_or_a_small_team:

What to do as a single person or a small team
*********************************************
The programs mentioned above are very big, and you might not have enough time
to attempt such large projects yet. It is also good to start with something
smaller, which will give you the satisfaction of completing a project, and give
you something with which to encourage others to help you.

Here are some ideas of projects to look into:

- `Tuxpaint <http://tuxpaint.org>`_ -- A drawing program for children. This is
  a very small translation (less than 1000 words) and the program is not
  dependent on any libraries or GUI toolkits that need to be translated.
- `Pootle <http://pootle.locamotion.org/>`_ -- A online system for translation
  and translation management. This is not such a high priority program to
  translate, but it is easy to do it, and provides lots of help. Translating
  Pootle can therefore also help to train new translators in your team.
- `GCompris <http://www.gcompris.net/>`_ -- Educational software for children.
  This is quite a large translation (more than 10 thousand words), but it is
  fairly easy to prioritise the effort either by targeting specific activities,
  or by doing the :doc:`short_strings_first`. GCompris is not dependent on any
  libraries or GUI toolkits that need to be translated.
- `xdg-user-dirs <http://l10n.gnome.org/module/xdg-user-dirs>`_ -- Translations
  for the common directories on Linux type systems (Documents, Desktop, Videos,
  Music, etc.) It is a very small translation (less than 50 words) and the
  effects should be visible in most "Open" and "Save" dialog boxes on Linux
  systems. Also see `the project page
  <http://freedesktop.org/wiki/Software/xdg-user-dirs>`_.
- `GTK+ <http://l10n.gnome.org/module/gtk+>`_ (look for the UI translations,
  not the properties). This is the GUI toolkit used by all programs in GNOME,
  as well as many cross platform programs like GIMP, Pidgin, Abiword, Dia,
  GnuCash and Gnumeric. Although all the UI translations in GTK+ are more than
  3000 words, you can start by doing only the "stock" translations (look for
  "stock" in the #: comments) which is just over 100 words. These "stock"
  messages are things like "OK", "Cancel", "Open", "Save", "Print", "Warning",
  "Undo", "Preferences", etc. These are used by many applications, so
  translating them will give an initial boost to the localised feel of all your
  programs using GTK+.
- `Pidgin <http://pidgin.im/>`_ -- A chat program for several protocols. This
  translation is quite big (more than 15 000 words), but it is easy to avoid
  translations that deal with certain obscure protocols (check the #:
  comments). Pidgin uses GTK+, so at least a partial translation of GTK+ will
  be needed to have Pidgin 100% translated.
- `Audacity <http://audacity.sourceforge.net/>`_ -- An audio editor. This
  translation is not that big, but it contains a lot of technical terms that
  might make it a bit more difficult. Audacity depends on the wxWidgets
  toolkit. For Linux this means that GTK+ should be translated as mentioned
  above. For Windows, wxWidgets need to be translated specifically, but it
  should also be possible to limit your work to the most important messages.

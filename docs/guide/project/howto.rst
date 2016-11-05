
.. _../pages/guide/project/howto#friendly_howto_for_translators:

Friendly howto for translators
============================== 

XXX
---

XXX
^^^

.. _../pages/guide/project/howto#working_with.po_files_and_the_translation_project:

Working with.po files and The Translation Project
"""""""""""""""""""""""""""""""""""""""""""""""""

I’ve written this to try and meet a need I certainly had, as a translator
starting with the TP. :-)

Sections marked **!** are Translate Tips!

----

.. _../pages/guide/project/howto#our_translation_toolbox:

Our translation toolbox
-----------------------

A true craftsperson respects his or her tools. We are very fortunate in having
some excellent localization tools nowadays. In order to translate a .po file,
you need:

.. _../pages/guide/project/howto#the_latest_version_of_gettext:

The latest version of gettext
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Check this with::

``gettext --version``

Currently, the answer is::

``gettext (GNU gettext-runtime) 0.16``

but since this entry will age, it’s worth checking the latest version anyway.
Whether you have an older version, or no version at all, you will need to
install the current version of gettext. Fink doesn’t always list the latest
version, so please check:

http://ftp.gnu.org/gnu/gettext/

and download and install the latest version there.

**?** *gettext manual:*  `completing gettext installation
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC8>`_

.. _../pages/guide/project/howto#a_translation_tool:

A translation tool
^^^^^^^^^^^^^^^^^^
You can simplify your task considerably by using a dedicated .po editor. These
are currently:

* `Virtaal <http://virtaal.translatehouse.org>`_ (Windows+Linux)
* `kbabel <http://docs.translatehouse.org/projects/localization-guide/en/latest/guide/kbabel.html>`_ (KDE)
* `gtranslator <http://gtranslator.sourceforge.net/>`_ (GNOME)
* `emacs <http://www.gnu.org/software/emacs/emacs.html>`_ (various platforms,
  including Mac OSX GUI)
* `poedit <http://www.poedit.org/index.php>`_ (various)

.. _../pages/guide/project/howto#people:

People
^^^^^^ 
People have put a lot of effort into helping us with our task. We also have
available:

* The `Translate Toolkit <http://toolkit.translatehouse.org>`_, which contains
  a number of really useful tools
* Translate Documentation, including this doc
* The web-based .po editor `Pootle <http://pootle.translatehouse.org/>`_: excellent
  for sharing the load
* `po4a <http://po4a.alioth.debian.org/>`_, a Debian effort which includes many conversion tools

The first three are available from `Translate
<http://translatehouse.org/products.html>`_ at Github.

**!** With po4a and the Translate Toolkit, you can turn practically anything into
or out of the .po format, possibly including organic forms… :-)

**?** **also see** other sections of this wiki, for key resources and helpful
information on many aspects of translating. Experienced translators have spent
a lot of time contributing to this wiki, to save all of us time and hassles.
Please feel free to add your experiences at any time: this is our shared
resource. :-)

Let’s have a look at the translation task…

----

.. _../pages/guide/project/howto#so_you_want_to_translate_a_.po_file:

So you want to translate a .po file
-----------------------------------

A PO file (Portable Object) is a format created especially for what we need to
do: grab the info, and move it about. You can put it through any text editor,
use just about any encoding (although utf-8 is safest for other reasons), feed
it to your dog, but it will come out the other end as exactly what it was to
start with … a text file. 

**!** The only thing that differentiates a .po file from a normal .txt file is
the headers, and the structure of each string block. This is checked by the TP
robot program when you submit the file, so knowing what to get right can save
you re-submitting it (and being talked down to by a robot, which can be a bit
exasperating. :-\ )

.. _../pages/guide/project/howto#headers:

Headers
^^^^^^^

Here is a blank set of .po file headers:

.. code-block:: po

    # SOME DESCRIPTIVE TITLE.
    # Copyright (C) YEAR THE PACKAGE’S COPYRIGHT HOLDER
    # This file is distributed under the same license as the PACKAGE package.
    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.
    #
    #, fuzzy
    msgid ""
    msgstr ""
    "Project-Id-Version: PACKAGE VERSION\n"
    "POT-Creation-Date: 2003-07-24 09:35+0200\n"
    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"
    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"
    "Language-Team: LANGUAGE <LL@li.org>\n"
    "MIME-Version: 1.0\n"
    "Content-Type: text/plain; charset=CHARSET\n"
    "Content-Transfer-Encoding: 8bit\n"

You will usually find a complete blank set, like this, in a file which has not
yet been translated at all, a .PO Template file, with the file extension .pot. 

**!** All you need to do to change a .pot to a .po is fill in the headers and
change the name of the file to .po. It’s as easy as that.

You may find some of the headers still blank, or not up-to-date, when you are
updating a partially-translated, or out-of-date file. 

**!** So you always need to check the headers: do this first, do it last (before
submitting the completed file), and you’ll save yourself hassle.

There are two headers which may or may not appear in that block, but it’s
better if they *do* appear. You can add them yourself:

.. code-block:: po

    "Report-Msgid-Bugs-To: \n"

and

.. code-block:: po

    "Plural-Forms: nplurals=INTEGER; plural=INTEGER\n"

so here we have a complete set (note the positions of those two additional
headers):

.. code-block:: po

    # SOME DESCRIPTIVE TITLE.
    # Copyright (C) YEAR THE PACKAGE’S COPYRIGHT HOLDER
    # This file is distributed under the same license as the PACKAGE package.
    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.
    #
    #, fuzzy
    msgid ""
    msgstr ""
    "Project-Id-Version: PACKAGE VERSION\n"
    "Report-Msgid-Bugs-To: \n"
    "POT-Creation-Date: 2003-07-24 09:35+0200\n"
    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"
    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"
    "Language-Team: LANGUAGE <LL@li.org>\n"
    "MIME-Version: 1.0\n"
    "Content-Type: text/plain; charset=CHARSET\n"
    "Content-Transfer-Encoding: 8bit\n"
    "Plural-Forms: nplurals=INTEGER; plural=INTEGER\n"

Each header has a job to do, so let’s go through them one-by-one:

.. _../pages/guide/project/howto#the_title_header:

The title header
""""""""""""""""

.. code-block:: po

    # SOME DESCRIPTIVE TITLE.

is there to give quick information as to the title of this package. Here you
input the *name* of the program (not the version number). I’ll use the program
Tuxpaint (an excellent art program for young children), and my language,
Vietnamese, as the example in this section.

.. code-block:: po

    # Vietnamese translation of TuxPaint.

**!** Note that all these headers have *a # sign and one space* before the
information. The robot is very picky about this, as it is gettext’s way of
signifying an informative header. gettext actually parses this information, and
the whole file, so by getting the format right, we save ourself time spent
fixing the errors, when the file won’t parse.

.. _../pages/guide/project/howto#the_copyright_header:

The copyright header
""""""""""""""""""""

.. code-block:: po

    # Copyright (C) YEAR THE PACKAGE’S COPYRIGHT HOLDER

In the case of packages sent to the Translation Project, the software is
usually open-source, free software, so the information here is usually (I’ll
use this year):

.. code-block:: po

    # Copyright © 2005 Free Software Foundation, Inc.

If you can access the copyright sign © fairly easily from a keyboard layout or
special characters’ input feature, it does look more professional. ;-) (It’s
typed Right :kbd:`Alt+C` on a qwerty international keyboard.)

Occasionally, a file will come with a proprietary copyright header: somebody
has created, and claims copyright over this file (for example):

.. code-block:: po

    # Copyright © 2001-2005 Nguyễn Thị Hoa.

In this case, you respect the header already there. Do not change it.

**!** If your file has a proprietary copyright header, and is rejected by the TP
robot for not having a FSF copyright header, simply write to the TP
co-ordinator at:

translation@iro.umontreal.ca

because that is their problem, not yours, although it’s rather annoying to get
your file rejected for something that isn’t under your control. The
co-ordinator needs to set an option for these files so they won’t be rejected
next time you, or another translator submits them. Again, by contributing what
we can at the time, we all help each other. ^_^

.. _../pages/guide/project/howto#associative_copyright_header:

Associative copyright header
""""""""""""""""""""""""""""

.. code-block:: po

    # This file is distributed under the same license as the PACKAGE package.

This header (not always present, although it should be) releases the
translation under the same copyright as the original file. This saves queries
about the copyright of translations, and if you are volunteering for the TP
(Translation Project), you will have already filled out a disclaimer which
assigns your copyright to the FSF. This saves a lot of hassle, simplifying the
copyright issues for everybody.

All you need to do here is insert the package name again:

.. code-block:: po

    # This file is distributed under the same license as the TuxPaint package.

.. _../pages/guide/project/howto#the_list_of_translators:

The list of translators
"""""""""""""""""""""""

.. code-block:: po

    # FIRST AUTHOR <EMAIL@ADDRESS>, YEAR.

This will only be blank if you are the first person to translate this file at
all. If it has been translated, even partially, before, the names of any
previous translators will each occupy one header exactly like this. So if there
is only one translator (I’ll use my name):

.. code-block:: po

    # Clytie Siddall <clytie@someserver.net.au>, 2005.

However, if there have been previous translators, there will be more than one
translator header, for example:

.. code-block:: po

    # pclouds <pclowds@anotherserver.com>, 2002.
    # Tran Minh Thanh <tmt@yahhooo.com>, 2004.
    # Clytie Siddall <clytie@someserver.net.au>, 2005.

So in theory, you could have a lot of these headers, one after the other, but
in practice, there are one to five translator headers. 

**!** Don’t change any of the older translator headers, just insert your own
below the newest one. These headers ensure that everybody who has put effort
into translating this file, gets both some recognition, and must take
responsibility, for their work. 

.. _../pages/guide/project/howto#the_blank_header:

The blank header
""""""""""""""""

::

    #

You may have a blank header line between the two sections of the file header.
This makes it easier to read. You don’t need to do anything here. ;-)

.. _../pages/guide/project/howto#the_fuzzy_header:

The fuzzy header
""""""""""""""""

.. code-block:: po

    #, fuzzy

Note the comma after the # sign. This indicates that this header is read by
gettext as *information* on the string blocks. If this header is present, there
are incomplete or incorrect strings in this file. Your .po editor may remove it
when you finish those strings, or, if you’re using a text editor not designed
to handle .po headers, you may remove it yourself. Just delete the whole line.

*Fuzzies* are strings which are incomplete or incorrect. gettext makes this
judgement, for example, on whether the quotation marks, any variables and
line-breaks match, or not. It will also base this judgement on whether any
compendium (glossary) strings suggested by msgmerge match the original string
completely, or not. Each *fuzzy* string is marked with the fuzzy header, and
needs careful checking. More on that further down. 8-)

*The gettext manual:* `fuzzy strings
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC46>`_ 

.. _../pages/guide/project/howto#the_string_pair:

The string pair
"""""""""""""""

.. code-block:: po

    msgid ""
    msgstr ""

This blank string pair indicates to gettext, I imagine, the structure of the
strings in the file. The msgid string is the original text, and the msgstr is
the translation. 

**!** The output file must contain both, and they must be surrounded by quotation
marks. Do not alter this header.

.. _../pages/guide/project/howto#the_package-version_header:

The package-version header
""""""""""""""""""""""""""

.. code-block:: po

    "Project-Id-Version: PACKAGE VERSION\n"

Here, the version of the package is important: it’s a header you need to watch out for when updating a file. 

**!** The TP robot requires the name of the program to be separated from the
version by a space, not a hyphen or underscore. So this header may vary in that
way, from the original file-name.

Original file-name: tuxpaint-2.1pre

.. code-block:: po

    "Project-Id-Version: Tuxpaint 2.1pre\n"

**!** Remember to change this header when you update a file.

Use all the information in the version part of the filename: 0.03a2, 2.01b,
0-03.2pre2, this is all useful information about the stage of development of
this package. 

* **a** means alpha, a very early release, usually quite unstable, for testing
  purposes only; 
* **b** means beta, a later testing release, often quite stable, but not
  guaranteed or supported. You can learn a lot and help software development by
  testing beta software, especially for language support. :-)  
* **pre** means pre-release, the last version(s) before a full release version:
  finished testing. It probably means the full version isn’t far away, so
  you’ll need to update the file again then. 

If you’re using the programs you translate, remember to check the version data
to decide if the program is stable or needs further testing. If you decide to
help test a program, that’s great, as long as you don’t expect it to be
completely stable or have tech support. On the other hand, the developers and
other people contributing, as you are, by testing, will be very happy to
discuss the program and support each other on the program’s mailing list. ;-)

.. _../pages/guide/project/howto#the_report-string-bugs_header:

The report-string-bugs header
"""""""""""""""""""""""""""""

.. code-block:: po

    "Report-Msgid-Bugs-To: \n"

This header is often omitted, or not filled-out, and this is a nuisance for us,
because it’s the contact address for us to use when an original string is
incorrect (typo, missing bracket, missing words, bad grammar or spelling), or
when we don’t understand a string well enough to translate it.

It wastes our time if we need to go back to our team page, click on the
file-name to go to its textual domain, then look for the homepage of the
program or some other contact information; often you have to Google for quite
some time, in order to find it at all.

When you find that contact address, please fill it in in your file, so the next
person, quite possibly you :-) , won’t need to waste time looking for it. It’s
a good idea to encourage your developers to fill in this header.

**?** One handy thing I’ve found out about these contact addresses is: 

* all GNU packages have the contact address:

bug-PACKAGE_NAME@gnu.org

* all GNOME bugs are reported via `Bugzilla <https://bugzilla.gnome.org/>`_
* all Debian bugs are reported via email to:

owner@bugs.debian.org 

with the filename as the subject line, and the body starting with:

::

    Package: FILENAME
    Version: VERSION_NUMBER
    Severity: wishlist
    Tags: l10n, patch

.. _../pages/guide/project/howto#the_creation_date_of_this_file:

The creation date of this file
""""""""""""""""""""""""""""""

.. code-block:: po

    "POT-Creation-Date: 2004-07-24 09:35+0200\n"

The .pot is the original, untranslated file, so that was when this version of
it was created by gettext. Updated files will have .po creation dates. 

This information is unimportant to you (you don’t change it), except: 

**!** you will have to make sure your revision date (the date of your changes to
this file) is *after* the creation date, otherwise the TP robot will say "I
object!" and you really can’t blame it. We translators have not yet found out
how to make time go backwards. LOL

.. _../pages/guide/project/howto#the_last-change_date_header:

The last-change date header
"""""""""""""""""""""""""""

.. code-block:: po

    "PO-Revision-Date: YEAR-MO-DA HO:MI+ZONE\n"

This is blank in an original .pot file, since no changes (translations) have
occurred. In an updated file, a date will be present. All we need to remember,
is: 

**!** to update this date before submitting our completed file. 

A .po editor program may do this automatically. You can do it manually at any
stage. In BBEdit, you can create a glossary item using strftime variables (you
can just save it and use it without having to understand how it works):

.. code-block:: po

    "PO-Revision-Date: #LOCALTIME %F %R%z#\n"

which, anytime you select that whole header, will replace it with your local
time and UTC offset. In my case, that is, as I write this sentence:

.. code-block:: po

    "PO-Revision-Date: 2005-05-16 14:58+0930\n"

**!** Note the order of the date: year-month-day, the year being four numbers,
the month two, and the day two. This means including leading zeros when the
number is less than 10, as in the current month: 05 (May).

Note the UTC offset: +0930. This says that my timezone (Adelaide, Australia,
Central Australian normal time, not daylight saving) is 9.5 hours, 9 hours and
30 minutes, after GMT or UTC time (00:00). 

**!** You need to fill in your timezone here, and note that there is no space
before it in this header. Remember the leading zero if, as in my case, you’re
less than ten hours before or after UTC. (BBEdit’s glossary item, or your .po
editor, may do all this for you.)

.. _../pages/guide/project/howto#the_most_recent_last_translator_header:

The most recent (last) translator header
""""""""""""""""""""""""""""""""""""""""

.. code-block:: po

    "Last-Translator: FULL NAME <EMAIL@ADDRESS>\n"

Where you have been the *only* translator, your name will appear both in the
First-Translator header, and here in the Last-Translator header, which may
result in you feeling like the Only-Possible-Translator. LOL  

All you need to do is fill in your name and address here, again, but don’t
include the year, as in the First-Translator header, because the
PO-Revision-Date: header supplies that.

If a previous translator’s name is filled in here, you need to edit that to
show your name. Make sure that previous translator is mentioned in the top part
of the headers (first, second, third, however many translators there have
been).

So in my case, this header will show:

.. code-block:: po

    "Last-Translator: Clytie Siddall <clytie@someserver.net.au>\n"

.. _../pages/guide/project/howto#the_language-team_header:

The language-team header
""""""""""""""""""""""""

.. code-block:: po

    "Language-Team: LANGUAGE <LL@li.org>\n"

Here is where your language team is given credit for all the hard work you do.
It also supplies an alternative contact address for people writing to you about
your translations. This is particularly useful when email addresses become
outdated, as people move around or change their details.

Your language team will be the name of your language, and sometimes of the
project. The address will often be the team mailing-list. So in my case, this
header will be:

.. code-block:: po

    "Language-Team: Vietnamese <gnomevi-list@lists.thatserver.net>\n"

or

.. code-block:: po

    "Language-Team: Gnome-Vi <gnomevi-list@lists.thatserver.net>\n"

.. _../pages/guide/project/howto#the_mime-version_header:

The MIME-version header
"""""""""""""""""""""""

.. code-block:: po

    "MIME-Version: 1.0\n"

This will usually come filled-in. You don’t need to worry about it. Isn’t that
great? :-D

.. _../pages/guide/project/howto#the_content-type_header:

The Content-Type header
"""""""""""""""""""""""

.. code-block:: po

    "Content-Type: text/plain; charset=CHARSET\n"

**!** This is really important. It sets the character set for your language.
UTF-8 is the best choice, but if your language requires another charset
(character set), please input it here. I imagine this header will soon be
filled in automatically as UTF-8. For my language:

.. code-block:: po

    "Content-Type: text/plain; charset=UTF-8\n"

God bless Unicode! It’s such a relief to be able to shrug off all those clumsy,
tortuous legacy encodings…  Now we just need better Unicode support in all
systems. 8-O

.. _../pages/guide/project/howto#the_content-transfer-encoding_header:

The Content-Transfer-Encoding header
""""""""""""""""""""""""""""""""""""

.. code-block:: po

    "Content-Transfer-Encoding: 8bit\n"

This should also come already-set. If not, please input **8-bit**, which can
handle UTF-8 and other complex charsets in transit. You don’t want your hard
work to be messed up in submitting the file, or when it is sent on to your
developers.

.. _../pages/guide/project/howto#the_plural-forms_header:

The Plural-Forms header
"""""""""""""""""""""""

.. code-block:: po

    "Plural-Forms: nplurals=INTEGER; plural=INTEGER\n"

This is often not included, but it *should be*. When you encounter plural
(describing more than one person or thing) strings in your files, this plural
header makes sure you have the correct number of fields to fill in with the
translation. This varies considerably from one language to another. For my
language:

.. code-block:: po

    "Plural-Forms: nplurals=1; plural=0\n"

because Vietnamese has no plural forms in that sense. One book, two book.  But
you should see our pronoun collection… 8-)

Some languages have several plural forms. A plural msgid looks like this:

.. code-block:: po

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."

Since English, the original language, *does* have plural forms in this sense.
If your language behaves like English in this way, you will have two msgstr
fields to fill in, like this:

.. code-block:: po

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."
    msgstr[0] ""
    msgstr[1] ""

but in my case, it should be:

.. code-block:: po

    msgid "Found and replaced %d occurrence."
    msgid_plural "Found and replaced %d occurrences."
    msgstr[0] ""

If your plurals header is set correctly, you will have the appropriate number
and kind of msgstr fields to fill in. So it’s a big help. 

**!** Find out what yours is, and make sure you fill it in for all your files: it
will save you hassle.

If you are unsure of the plurals header that should be set for your language,
please consult your team leader – and if s/he is unsure, you can discuss this
on the `TP mailing list
<https://lists.sourceforge.net/lists/listinfo/translation-i18n>`_, an excellent
place to ask questions and share experience.

And those are all the headers you need to complete! These headers all save
time and trouble in the process of localizing an application. You can set them
in your .po editor, or simply keep a copy of them to paste over the out-of-date
or original headers. 

**!** By getting them correct, and finding your own way to deal with them, you
become a better translator, because the true craftsperson makes the best use of
his or her tools. The .po format is one of our tools.

**?** *the gettext manual:* 

`the po format
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC9>`_

`filling in the header entry
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC35>`_

----

.. _../pages/guide/project/howto#where_do_we_get_our_files:

Where do we get our files?
-------------------------- 

Your `team page <http://translationproject.org/html/welcome.html?team=index>`_
((If your language does not have a team yet, please contact the TP co-ordinator
about creating one.)) at the TP will list the files available to be translated.
You need to ask your team leader which files need translating, or ask to
translate particular files, and s/he will notify the TP co-ordinator that you
are assigned to that file. Your name will appear next to it on your team page.
What does becoming a TP translator involve?

.. _../pages/guide/project/howto#to_be_a_tp_translator:

To be a TP translator
^^^^^^^^^^^^^^^^^^^^^

You need to register with `the TP
<http://translationproject.org/html/welcome.html>`_. This is simple, although
it involves one hold-up: the disclaimer.

* Your team-leader may email the TP co-ordinator 

S/he will advise the co-ordinator that you want to join the project, or s/he
may ask you to do it with his/her permission, but it is important that you are
*part of the team*, so that’s where the team leader comes in. 

A language team can support each other, and ensure a consistent approach to the
task. It’s confusing, and much less effective, to have people working
separately on the same language, not communicating or co-operating. The TP
requires changes to go through your team co-ordinator, so there should be no
conflicts or confusions over who does what, how and why. 8-)  

**!** Check with your team-leader, who will be a big help to you, join the team
mailing-list, and join the TP.

* Once you have registered with the TP 

(yourself with your team-leader’s permission, or through your team-leader), you
need to fill out `the TP disclaimer
<http://www.iro.umontreal.ca/translation/HTML/disclaim.html>`_, sign it, and
fax or post it to the FSF. (If you have any difficulty understanding the
information, or with submitting the disclaimer, your team leader is there to
help you.) You can also print the disclaimer form, sign it, scan it and email
it. One way or another, this disclaimer needs to arrive at the Free Software
Foundation, and be logged under your name. When this has occurred, your name on
your team page will show:

+-------------+--------------+
|             |  Disclaimer  |  
+=============+==============+
|  Your name  |     Yes      |
+-------------+--------------+

The difference the disclaimer makes (apart from simplifying copyright issues as
mentioned above, which is its reason for existence) is that most TP files are
not available for translation unless your disclaimer is logged with the TP.
When you go to a file’s textual domain page (by clicking on its link on your
team page), check down the page whether a disclaimer is required.

**!** Until your disclaimer is logged with the FSF, you can only translate
non-disclaimer files, but there are quite a few of them, so don’t hold back.
;-D

.. _../pages/guide/project/howto#how_do_we_get_the_most_current_files:

How do we get the most current files?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The files listed on `your team page
<http://translationproject.org/html/welcome.html?team=index>`_ *should* be the
most current files. Developers send them in to the TP to be translated, and
they should be sent in automatically, each time they are updated. It is
extremely important to translate the current file, otherwise, your translation
may not be used at all, or won’t be used by the majority of users. Downloading
your file from your team page at the TP should ensure you get the latest, most
current file.

**!** If it turns out that this file is not the most current (rare, but
possible), please email the TP co-ordinator so this can be fixed.

Methods of establishing and maintaining currency include CVS, SVN and private
repositories. The TP saves you the trouble of learning how to handle these
versioning systems, by keeping the most current files available. All you need
to do is download them from your team page. Click on the file, and that will
take you to its textual domain. Click on the file link, you have a file! ;-)

.. _../pages/guide/project/howto#automatic_update:

Automatic update
^^^^^^^^^^^^^^^^

If you have asked the TP to send you updates to your assigned files
automatically, these will simply arrive in your Inbox. You don’t need to
download them. :-D 

Updating is usually quick work, so it’s great to have them arrive
automatically: a file could be uploaded at the TP with a couple of new or
changed strings, sent out to the translator, edited and returned all in the
same day. *That’s* currency. 8-)

**?** Other projects have their own howtos on getting current files: ask your
team leader.

----

.. _../pages/guide/project/howto#a_new_file:

A new file
---------- 

You have a clean start: nobody has edited this file before you. ;-)

.. _../pages/guide/project/howto#edit_the_headers:

Edit the headers
^^^^^^^^^^^^^^^^ 

as shown above.

.. _../pages/guide/project/howto#not_repeating_yourself:

Not repeating yourself
^^^^^^^^^^^^^^^^^^^^^^

The good news, now, is that you don’t have to type every single string into
that new file, yourself, if you have any compendium files. A compendium is a
glossary created by gettext. Your team-leader should be able to point you to
current glossaries in whatever form, although we need *compendia* for the
command-line process below. 

It’s best to use the same glossaries as the rest of your team, as a consistent
vocabulary is important. It confuses the user much less, and gives him/her less
new terms to handle. When you are starting out in computing, or using a new
program (we’re always learning new things), you don’t want to have to worry
about differing ways of saying the same thing.

A **compendium** is a text file built by gettext, by merging the contents of
completed .po files. You may want to keep different compendia for different
types of files: I have different compendia for main program files, games,
iso-files and calculator programs. You can apply any number of compendia to a
file.

When you apply a compendium to a new file, called *initializing* the file,
gettext tries to match the original strings with strings and translations
recorded in the compendium. If the match is exact, gettext will fill in the
msgstr completely, for you. If the match is close ((in gettext’s judgment, and
there are debates about how close it needs to be :-))), then it fills in the
translated string, but applies the fuzzy tag to that string block. That means:
"Check this one, I’m not sure." Even if that string is not completely
translated, it may save you time: perhaps a capital letter or punctuation mark
is different, or part of the sentence … or it may be completely off-target, but
usually it is close, and that’s a big help.

**!** How do we do that? Here is the command (record it somewhere handy):

::

    msgmerge --compendium compendium.po -o file.po /dev/null file.pot

This says:

*Program msgmerge* (gettext’s merge program), *I want you to use the
information in a compendium file, its name* (in this case) *is compendium.po*
(it can be anything.po), *I want you to output* (-o) *the combined data from
the compendium and the file to a file named file.po, at /dev/null* (because you
don’t want the combined data, you want the data that matches, /dev/null is like
saying, throw it away), *and the file I want you to initialize is called
file.pot.*

So, that command could be:

::

    msgmerge --compendium glossary1.po -o file.po /dev/null gnubiff.pot

Parts of that command:

**msgmerge** – the program you’re asking to do the job

**--compendium** – the option that says "make a glossary file out of this data"

**glossary1.po** – the filename of your existing glossary file, or the filename you want for a new one

**-o** – output the combined two files

**file.po** – to this file

**/dev/null** – and lose it, because I don’t want the two files combined

**gnubiff.pot** – but put any matching strings into this file (the one you want to translate)

So all you really need to do is to type the name of your glossary file, your
compendium, instead of *compendium.po* here, and type the name of the file you
want to translate, instead of *gnubiff.pot*. 

**!** Remember that the path, any directories that msgmerge needs to travel
through to find a file, is part of its file-name. The two files in our example
might be:

::

    Documents/glossaries/glossary1.po

and

::

    Documents/TP/gnubiff-2.1.3/gnubiff.pot

**!** When typing filenames in the Terminal, use the Tab key to fill in the rest
of a name, once you’re past any letters that match other names at that level.

Using this msgmerge command may get a lot of matches, or it may not: it depends
on how much data you have in your compendium which is relevant to your new
file. You can list compendia, one after the other, if you want to apply more
than one:

::

    msgmerge --compendium glossary1.po glossary2.po glossaryA.po -o file.po /dev/null gnubiff.pot

Most of all, when you translate a number of files which do similar tasks, or
you decide the next time someone asks you to translate the "OK" button, you’ll
scream and throw things, msgmerge can save you a lot of hassle. It’s another of
our useful translation tools. (This whole task was very messy before gettext.)

----

.. _../pages/guide/project/howto#an_incomplete_file:

An incomplete file
------------------ 

Firstly, update the headers, as shown above. The version number, translator
details and revision date are the key areas when updating.

With an incomplete file, you can use the msgmerge command again: it will simply
try to match any strings which are not yet translated.

Before we get down to editing our file, here are a few more time-saving words
on building your own compendia.

----

.. _../pages/guide/project/howto#our_own_glossaries:

Our own glossaries
------------------

Creating your own glossary files, compendia, is is a simple process, which some
of the .po editors have built-in. In LocFactoryEditor, for example, I can
create, merge and apply any number of glossaries in various formats (I usually
use .tmx).

If using the command line, you can still do it like this, each time you
complete a file and want to add its translations to a compendium file:

::

    msgcat -o compendium.po file1.po file2.po

This command says: *program msgcat* (gettext’s catalogue program), *I want you
to put all the output* (-o) *from this task in a file called compendium.po.*
(If there is already a file with that name in that location, it will merge with
it -- handy for updating your compendium). *Take all the data from these files:
file1.po and file2.po*

so it could be:

::

    msgcat -o glossaryA.po gnubiff.po

if you are adding only one file to glossaryA, or

::

    msgcat -o glossary_kids.po tuxpaint.po gcompris.po

if you’re adding those two files to your kids’ program compendium.

The compendium process is a real time-saver for us, so please take the time to
use it. You can always ask for help, or ask questions, on the `TP mailing list
<https://lists.sourceforge.net/lists/listinfo/translation-i18n>`_, as mentioned
above. 

**!** I recorded these two commands in a handy place, so whenever I need them, I
can copy them in. If you use them often, you may find they stick in your mind.
8-)  My mind is not particularly sticky nowadays. More like sludge, I think.
:-/

*the gettext manual:*

`invoking the msgmerge program
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC37>`_

`using translation compendia
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC54>`_

----

.. _../pages/guide/project/howto#translating_a_file:

Translating a file
------------------

You’ve got the headers sorted out, you’ve used your compendia to supply any
likely strings, and you can’t wait to see what weirdnesses our developers have
foisted on us now – uh, time to translate. ^_^

Your .po file, apart from the headers, consists entirely of string blocks. Each
string block represents one string which will be displayed in translated form
in the program from which the .po file was generated. It might be text on a
button, on a toolbar, in an error message or tip window, wherever it pops up in
the program, it’s a string block in our .po file. All God’s chillun got string
blocks. :-D

Here is the structure of a string block:

.. code-block:: po

    #.Type: boolean
    #.Description
    #:../exim4-base.templates.master:4
    msgid "Remove undelivered mails in spool directory?"
    msgstr ""

This is a particularly well-structured string-block, from the Debian Installer
translation project. Note the two #. lines: the # and a full stop/period .
which denote:

.. _../pages/guide/project/howto#a_developer_comment:

A developer comment
^^^^^^^^^^^^^^^^^^^

.. code-block:: po

    #.I am a developer comment. :)

Developers can save us a lot of hassle by inserting comments which explain the
string, or give instructions on how to format it. Most .po files have no
helpful developer comments yet, so this one stands out. You may like to
encourage your developers to insert comments, as well as the
Report-Msgid-Bugs-To header. 8-)

Here is an absolutely superb example of the developer comment, again from the
Debian installer project:

.. code-block:: po

    #.Type: select
    #.Choices
    #.Translators beware! the following six strings form a single
    #.Choices menu. - Every one of these strings has to fit in a standard
    #.80 characters console, as the fancy screen setup takes up some space
    #.try to keep below ~71 characters.
    #.DO NOT USE commas (,) in Choices translations otherwise
    #.this will break the choices shown to users
    #:../exim4-config.templates.master:9
    msgid "internet site; mail is sent and received directly using SMTP"
    msgstr ""

You can’t go far wrong with that sort of help. 

Back to our first example, which still explains the string a lot better than
the average .po document:

.. code-block:: po

    #.Type: boolean
    #.Description
    #:../exim4-base.templates.master:4
    msgid "Remove undelivered mails in spool directory?"
    msgstr ""

the two developer comment headers tell you:

- The string is a boolean type, i.e., it will have an answer of Yes or No (1 or
  0 from the computer’s point-of-view).
- The string describes things for the user.

The next line describes where the string fits in in its program. Sometimes
these lines can help us understand what the string needs to do, but not often.
:-/

While we’re on the comments topic, we translators can insert comments, too. 

.. _../pages/guide/project/howto#translator_comments:

Translator comments
^^^^^^^^^^^^^^^^^^^

.. code-block:: po

    # I am a translator comment. ;)

**!** This can be particularly handy when more than one translator works on a
file. 

In any case, other translators may work on this file in the future, so it’s
worth inserting a comment if things need to be remembered. Translator comments
must be inserted at the very top of the string block, after the gap from the
previous block (the "white space"): note the whole line before each quoted
translator comment here. They have a # mark then a space: no punctuation mark.
Thus, I have often inserted comments like this:

.. code-block:: po

    # Don’t translate this: it’s a variable. Đừng dịch chuỗi này vì là biến.

So we might have:

.. code-block:: po

    # Don’t translate this: it’s a variable. Đừng dịch chuỗi này vì là biến.
    #. login window data
    #:../exim4-base.templates.master:4
    msgid "(${NAME})"
    msgstr "(${NAME})"

or you might suggest a certain way of explaining or formatting something. Don’t
feel shy about inserting translator comments: they’re not seen by the user of
the program. You may wonder if some developers know their comments field is
meant for talking to us: some programs only contain developer comments where
they are talking to each other, even insulting the user. This is disappointing.
:-(

**!** As you work your way through each string block, don’t feel that you have to
know everything. 

Some strings (maybe many of them) will be confusing or even abstruse: many
developers do not have good explanatory skills, even in their own language.
Feel free to improve the structure, when creating the translated string, and to
explain it in a way that will work best for your language group. 

**!** The aim is not to translate the exact word or term, since computing terms
are mostly chosen for brevity.

Words like "icon" and "text" were not in general use in the English language
before personal computing, so you can choose a brief word or expression which
serves to carry the meaning. For example, the word "icon" in Vietnamese is
"biểu tượng", which is considerably longer. Where space is important, in a menu
item or on a button, or as the title for a table column, I would use a word for
"picture": "hình" or "ảnh", because they are much the same size as the word
"icon", and in that context, where people are expecting a small picture, they
carry the appropriate meaning. Computing vocabulary is growing and developing
in all languages: you have the opportunity to help create and refine it for
your language group.

Most likely your language group will have an ongoing glossary project for
computing terms, where you can suggest, find and discuss the appropriate terms.
We have one `here <http://vnoss.org/evgs/index.php?action=search>`_. 

**!** Your input is important: the aim is to communicate effectively with the
user, not to mirror exactly what people are doing in English. 

This is even more of a challenge where your culture is very different from the
Anglo culture, so give yourself the chance to think carefully about what each
string is supposed to achieve, and how to communicate it to your language
community.

For example, in Vietnamese, we show emphasis more with the words chosen, than
by exclamation marks. Quotation marks interfere with meaning, since we use so
many accents, so I use «guillemots» instead. English language to the user from
the computer is nearly always wrong for Vietnamese: I need to find the
appropriate way to express what the string is really saying. For example:

.. code-block:: po

    msgid "Choosing a simple root password is a really dumb idea."

is insulting in Vietnamese, and completely inappropriate, so my sentence in
Vietnamese says something more like:

.. code-block:: po

    msgstr "It is not a good idea to choose a simple root password."

since that form is much stronger in Vietnamese than in English, quite strong
enough to gain the user’s attention at the right level.

**!** Remember, while the developer may be the expert on how that program works,
you and your team-mates are the ones who understand your language and culture,
so *you* need to make the choices about how to express meaning, and the most
appropriate way to talk to the user.

.. _../pages/guide/project/howto#obsolete_strings:

Obsolete strings
^^^^^^^^^^^^^^^^

.. code-block:: po

    #~ msgid "I am an obsolete string. Nobody loves me. Boo-hoo. :("
    #~ msgstr "Tôi là một chuỗi cũ. Không có ai thương tôi. Hu-hu. :(" 

Strings starting with the hash # and tilde ~.

.. code-block:: po

    #~ msgid "Forward _Quoted"
    #~ msgstr "Chuyển tiếp _trích dẫn"

Some files will have a number of strings at the end of the file, where the
msgid and msgstr string pair start with the hash character, and often the tilde
character as well, which signifies the user directory on your hard drive, for
example. *It doesn’t mean that here.*

**!** In a .po file, strings starting with #~ are not currently being used by the
program. 

So why keep them, you may ask? Indeed you may, I’ve asked the same question
myself. These strings may be re-used one day, so you are not advised to delete
them. However, you may make your own decision on how much of your energy you
are going to devote to these obsolete strings. There is definitely a fault in
the process: I’ve encountered files with nearly all the file obsolete strings!

Your .po editor may keep these strings out of your way. Most PO editors (like
Virtaal) will hide them from you.

*the gettext manual:* `obsolete strings
<http://www.gnu.org/software/gettext/manual/html_mono/gettext.html#SEC48>`_

----

.. _../pages/guide/project/howto#style_tips:

Style tips
----------

In order to save time debugging (removing mistakes from) this file later on,
there are several things you need to remember as you progress through the file. 

**!** You must never edit the original string, the msgid. 

This information belongs to the program, and if you change it in any way, by so
much as a space or moving a word up or down a line, this will cause problems
when the file is re-integrated into the original program. 

**!** If there are errors in the msgid, please report them to the developer.

You do this via the Report-Msgid-Bugs-To address in the header, or, if that’s
not filled in or present, you go to the textual domain for this file, (the page
on the TP site from which you downloaded it, linked from your team page) and
follow the links to find a contact address. Once you have found it, please fill
in the Report-Msgid-Bugs-To header, so no future translator, or you yourself
later on, will have to waste time hunting for it again. ;-)

Remember, when you write to the developer, be polite and friendly. It’s very
easy to get impatient, when you’re cleaning up the nth messy .po file, but
please remember that these people are also volunteering their time, and may not
have great English skills, or even understand how the gettext process works.
Make friends: it’s a great opportunity. :-D

**!** Each string must "begin and end with a double quotation mark".

* Many files still have the older structure where each line break means
  stopping and starting the quotation marks again. This results in:

.. code-block:: po

    #: ../gedit/gedit-document.c:1964
    msgid ""
    "The disk where you are trying to save the file has a limitation on file "
    "sizes.  Please try saving a smaller file or saving it to a disk that does "
    "not have this limitation."

This style is now deprecated (not recommended, we’re trying to get away from
it), so although you must never edit the original strings, you can format the
*translation* in the current style: one quotation mark at each end. So, in my
file:

.. code-block:: po

    #: ../gedit/gedit-document.c:1964
    msgid ""
    "The disk where you are trying to save the file has a limitation on file "
    "sizes.  Please try saving a smaller file or saving it to a disk that does "
    "not have this limitation."
    msgstr "Đĩa được dùng để lưu tập tin có giới hạn về kích thước tập tin.  Hãy lưu một tập tin nhỏ hơn hoặc lưu tập tin này vào đĩa không đặt ra giới hạn trên."

As far as I can work out, you can only remove the extra quotation marks where
there is no formal line-break (\n). Where the \n character is present, I’ve
found I have to leave quotation marks at the beginning and end of each line in
the string, as formatted in the msgid. 

.. code-block:: po

    # Do not translate the upper-case quoted terms: they are values for the configuration. Đừng dịch kỹ thuật đã trích dẫn bằng chữ hoa vì là giá trị cho cấu hình.
    #: ../data/gedit.schemas.in.h:77
    msgid ""
    "Style for the toolbar buttons. Possible values are \"GEDIT_TOOLBAR_SYSTEM\"\n"
    "to use the system's default style, \"GEDIT_TOOLBAR_ICONS\" to display icons\n"
    "only, \"GEDIT_TOOLBAR_ICONS_AND_TEXT\" to display both icons and text, and\n"
    "\"GEDIT_TOOLBAR_ICONS_BOTH_HORIZ\" to display prioritized text beside icons.\n"
    "Note that the values are case-sensitive, so make sure they appear exactly as\n"
    "mentioned here."
    msgstr "Kiểu dáng cho nút thanh công cụ. Giá trị có thể là \"GEDIT_TOOLBAR_SYSTEM\"\n"
    "cho kiểu mặc định của hệ thống, \"GEDIT_TOOLBAR_ICONS\" nếu chỉ hiện thị các\n"
    "biểu tượng, \"GEDIT_TOOLBAR_ICONS_AND_TEXT\" nếu hiện cả biểu tượng và chữ.\n"
    "Và \"GEDIT_TOOLBAR_ICONS_BOTH_HORIZ\" để hiển thị chữ ưu tiên cạnh biểu\n"
    "tượng. Chú ý là phải viết hoa các giá trị để đảm bảo chúng được hiển thị\n"
    "đúng như đã nói."

Which looks like a multiple shopping-trolley collision. :-/

**!** Lines ending in a line-break (\n) in the msgid must also end with one in
the msgstr. 

This doesn’t mean you have to maintain the same number of lines: you can have
more or less lines in the translation than in the msgid. However, any line that
had to be broken with a \n in the original string, must do the same in the
translation. Let’s have a look at a few examples:

.. code-block:: po

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab."

This is correct, because my translation was shorter, so I *didn’t* need to
break the line.

.. code-block:: po

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab, và một số từ thêm nữa không cần thiết."

This is not correct, because I *did* need to break the first line, as the
original did, and I didn’t use a \n as it did.

So this would be correct:

.. code-block:: po

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab, và một\nsố từ thêm nữa không cần thiết."

and even this:

.. code-block:: po

    #: ../data/gedit.schemas.in.h:74
    msgid ""
    "Specifies the number of spaces that should be displayed instead of Tab\n"
    "characters."
    msgstr "Xác định số khoảng trắng được hiển thị thay vì ký tự Tab, và một\nsố từ thêm nữa không cần thiết. Hơn nữa, tôi có thể nói chuyện bằng cách\nnày được mấy ngày."

The result has to be the same layout as the msgid. If it needs to break each
line at a certain number of characters (roughly), then you do the same,
regardless of how many lines are involved.

You will have noticed the backslash \ used in the line-break. This is a special
character in .po files (and in many others). \n means a line-break. 

**!** The other most common use of \ in .po files is to *escape* quotation marks.

As you will have seen, quotation marks already have a job to do in the string
block. They say, *The msgid or msgstr string starts **"here**, and ends
**there."*** So when the gettext parser checks through the .po file, it knows
not to try and read what’s in between those quotation marks as commands. It
gets to loaf off until the next quotation mark tells it that lazy time is over,
and it had better pay attention again. :-) 

This is all very well, but what if the string itself contains a quotation mark?
Oops… let’s have a look:

.. code-block:: po

    #:../src/window-commands.c:162
    msgid "See the "Quick Help" for a list of commands."
    msgstr "" 

What’s going to happen? Well, we know that the parser is going to treat the
second quotation mark as the end of the string. Not so good. Then it will try
to read everything after that as commands … until it hits another quotation
mark, which it may think is the beginning of another string. Very messy. You’ll
see how mixed up it gets in this situation, when you forget a quotation mark or
insert an extra one. :-D

Fortunately, we can *escape* this situation, by using the handy backslash. The
backslash tells the parser to ignore what these quotation marks normally do. We
end up with this, instead:

.. code-block:: po

    #:../src/window-commands.c:162
    msgid "See the \"Quick Help\" for a list of commands."
    msgstr "" 

It looks a bit funny, but it’s just a backslash *escaping* each quotation mark.
All you need to do is to remember to do that any time you use a quotation mark
in your strings, as you might in translating the string I’ve quoted. Then
again, you might use «guillemots», as my language does, and they have no job to
do in .po files, so they don’t need escaping. So there. ;-)

Another option is to use the curly quote signs Unicode provides: “”.  they have
no special significance either, and look better, at the same time!

**!** The number and kind of variables in the original and translation must
match. 

Variables tend to follow certain forms, primarily strftime and printf, but a
good general guide is that anything that isn’t a piece of normal language is
probably a variable. Variables must **not** be changed, because they are
placeholders for the program: it has been told, for example, when you see the
variable %s in string c:219, it should substitute the user name of the current
user. In which case, the string in the .po file:

.. code-block:: po

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to gnubiff, %s!\n"

when used by the program, will display:

***Welcome to gnubiff, Clytie!***

if that is my username on that system. 

So simply translating it, and leaving the variable where it is, would probably
work:

.. code-block:: po

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to gnubiff, %s!\n"
    msgstr "Chúc mừng vào gnubiff, %s!\n"

Note that this string breaks the line, although it’s quite short. There will be
display reasons for this line-break, so we simply do the same.

Although we can copy the language in the string, and the variable…

**!** You achieve a translation of a much higher quality if you take some time to
think about what the string is going to do in the program. 

This can be difficult without developer comments explaining the string.
However, with a string like this, you will become aware that programs often
talk to the user in this anthropomorphic way (cute word, huh? it means
‘pretending to behave like people’: some of us have had anthropomorphic
ex-partners :-D ). Where was I? Oh, yeah… um, programs do this “Hi there,”
stuff, so it’s a likely occurrence. In which case, I would do better in my
language by eliminating the exclamation mark, which is not appropriate,
choosing the verb “using” instead of “entering”, and putting the username
variable before the implicit verb (using), thus:

.. code-block:: po

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to gnubiff, %s!\n"
    msgstr "Chúc mừng %s dùng gnubiff.\n"

**Welcome, Clytie, to using gnubiff.**

You can change the position of the variable, as I have here, as long as you
don’t change the **order** of variables. Some strings have more than one
variable: a string might say:

.. code-block:: po

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to %s, %s!\n"

and the program be instructed to fill in first, the name of the current part of
the program, and secondly, the username of the current user:

**Welcome to gnubiff configuration widget, Clytie!**

Since, from the reasons explained above, I would be putting the username
variable after "Welcome to (using)", I would be changing the order of the
variables:

.. code-block:: po

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to %s, %s!\n"
    msgstr "Chúc mừng %s dùng %s.\n"

**Welcome, gnubiff configuration widget, to Clytie.**

:-X

So I need to indicate the change in order:

.. code-block:: po

    #: src/gbiff2.c:219
    #, c-format
    msgid "Welcome to %s, %s!\n"
    msgstr "Chúc mừng %2$s dùng %1$s.\n"

by placing the 2$ (which says ‘second variable’) and 1$ (‘first variable’)
between the % and s of the variable. This tells the program that variable %2$s
might be first in the string, but it’s actually the second variable in the
program. %1$s might be second, but it’s identified as the first variable. The
program happily substitutes the current values and I see:

**Welcome, Clytie, to using gnubiff configuration widget.**

:-)

**!** So, keep the same number, exact appearance and order of variables in
strings. If you need to change the order, use the process above.

----

.. _../pages/guide/project/howto#checking_your_file:

Checking your file
------------------

If you miss any of these things, or confuse them in any way, do not despair,
because when you finish the file (or at any other time), you can run a check on
common mistakes, using this command:

::

    msgfmt -cv /dev/null FILENAME

This says, *program msgfmt, check* (-c) *the language rules (outputting any
results to /dev/null because I don’t want to keep a copy) in this file.*

msgfmt will list any remaining errors, with line numbers and descriptions, so
you can fix them. It will tell you if there are any remaining fuzzy entries,
and what types of errors you have. msgfmt is a big help. :-)

Running that check on a file I’m editing now:

::

    Pearl:~/gnome/HEAD clytie$ msgfmt -cv gedit/po/vi.po

Note that I’m two levels down from my home (user) directory, inside the HEAD
folder which is inside the gnome folder, and I need to tell msgfmt that the
file vi.po is two levels down from where I am, inside the po folder which is
inside the gedit folder. All clear? Hope so. Here we go…

::

    Pearl:~/gnome/HEAD clytie$ msgfmt -cv gedit/po/vi.po
    gedit/po/vi.po:504: parse error
    gedit/po/vi.po:643: missing `msgstr' section
    gedit/po/vi.po:644: keyword "t" unknown
    gedit/po/vi.po:1385: keyword "C" unknown
    gedit/po/vi.po:1386: keyword "C" unknown
    gedit/po/vi.po:1402: keyword "C" unknown
    gedit/po/vi.po:1403: keyword "C" unknown
    gedit/po/vi.po:1409: keyword "C" unknown
    gedit/po/vi.po:1468: missing `msgstr' section
    gedit/po/vi.po:1469: keyword "n" unknown
    gedit/po/vi.po:1483: missing `msgstr' section
    gedit/po/vi.po:1484: keyword "ang" unknown
    found 12 fatal errors

Fatal errors don’t actually kill you, but they will prevent your file from
being submitted as complete. Note the helpful line numbers. I’ll have no
trouble finding what’s wrong with those: from experience, I’d say I’m missing a
few quotation marks, that’s why the parser (a program that reads grammar, in
this case the grammar of commands) is trying to read the string as a command,
and doesn’t understand the keyword, the first word in the string, as far as a
parser is concerned.

You can check your file repeatedly (the up-arrow repeating the last command),
until you get a result like this:

::

    msgfmt -cv dasher/po/vi.po
    133 translated messages.

Then you can submit your file. ;-)

----

.. _../pages/guide/project/howto#submit_your_file:

Submit your file
----------------

In order to submit a completed translation file ((see your team leader for help
with any files you can’t complete)), all you need to do is email them to the TP
robot program. 

**!** Make sure your msgfmt check comes up clean, with no errors, before sending.

**!** Make sure the details in the subject line of the email are exact, or your
file will not be accepted. 

**!** Make sure you have changed the name of your file to languagecode.po, in my
case, **vi.po** **Note**: you may wish to keep the complete filename, e.g. (in
my case, and for the file gnubiff-2.3pre1) **gnubiff-2.3pre1.vi.po** to avoid
confusing files with the same name. Another useful precaution is to gzip your
file before attaching it to the email: this prevents the encoding being
scrambled in transit.

**Email address for submitting files:** ::

  robot@translationproject.org

**Subject line of the email:** ::

  PACKAGE_NAME.LANGUAGE_CODE.po

For example, with gnubiff in Vietnamese::

  gnubiff-2.1.3.vi.po

**!** Make sure the package name is exact, a hyphen between the program name and
the version number, and full stops/periods in the version number.

**!** Make sure there is one full stop/period between the version number and the
language code, and between the language code and the po extension.

I’ve made a template in my mail program, so whenever I have a file to submit, I
only have to fill in the package details. This saves me making mistakes with
the rest of it, because it’s easy to slip up on a space or a full stop. You
might like to set up something similar. For my email program Mail in Mac OSX, I
used `Mail Template <http://www.abracode.com/MailTemplate/moreinfo.html>`_, an
excellent program to save time and trouble in repeated, even reactive mailings.

----

.. _../pages/guide/project/howto#where_to_from_here:

Where to from here?
-------------------

I hope you have found this information, which I’ve scraped together by making
probably every conceivable mistake :-D, useful. Please feel free to add to it.
I look forward to seeing your experiences here.

**?** If there is any part of this document which you find hard to understand,
please leave a note here, and I will try to explain it.

**?** We would welcome translations of this document, or any similar howto, in
your language.

Enjoy your translating time in the exciting and welcoming Free Software
community.

from Clytie

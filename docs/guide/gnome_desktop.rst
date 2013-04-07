
.. _../pages/guide/gnome_desktop#gnome:

GNOME
*****

GNOME is a feature rich Linux graphical desktop environment.  The project has
quite an established localisation initiative.

Since this page has been created, many things in GNOME has changed, and they
have good documentation and infrastructure to help translators. 

The most important documentation for translating GNOME is therefore at the
GNOME website: http://live.gnome.org/TranslationProject/

The rest of this document is kept in place for the time being, but a lot of it
is now out of date and not 100% accurate any more.

.. _../pages/guide/gnome_desktop#essential_reading:

Essential Reading
=================

Please familiarise yourself with these before proceeding:

* `Gnome Translation Project <https://live.gnome.org/translationproject/>`_
* `Localisation Guide
  <https://live.gnome.org/translationproject/localisationguide>`_
* `Join the Gnome Translation Project
  <https://live.gnome.org/translationproject/joiningtranslation>`_

.. _../pages/guide/gnome_desktop#useful_urls:

Useful URLs
===========

* `Status Page <http://l10n.gnome.org/releases/gnome-3-4//>`_
* `Resources Page <http://l10n-status.gnome.org>`_

.. _../pages/guide/gnome_desktop#translating:

Translating
***********

This is a roughly sequential outline of the steps you need to take to translate
GNOME into your language.

.. _../pages/guide/gnome_desktop#joining_the_mailing_list:

Joining the mailing list
========================

Subscribe to the `gnome-i18n mailing list
<http://mail.gnome.org/mailman/listinfo/gnome-i18n/>`_

.. _../pages/guide/gnome_desktop#gnome_glossary:

GNOME Glossary
==============

Start with `GNOME Glossary
<http://developer.gnome.org/projects/gtp/glossary/>`_ to create consistency
across future GNOME localisations.  

Start with the latest versions in of `GnomeGlossary.csv
<http://cvs.gnome.org/viewcvs/gnome-i18n/glossary/GnomeGlossary.csv?view=log>`_
in CSV format and convert to PO using the csv-to-pot.sh script.  The layout is
slightly different from the layout created by :ref:`po2csv <toolkit:po2csv>` so you
cannot convert the created POT file to a `Translate Toolkit
<http://toolkit.translatehouse.org>`_ style CSV file.

If you need to translate using CSV instead of PO then rather edit the
GnomeGlossary.csv and manipulate it into a PO file later.

However, please note that the glossary itself is several years old and **not
maintained** anymore (confirmed by last maintainer), so don't depend heavily on
it. Instead, use it as a reference, and build all necessary glossary term as
needed.

.. _../pages/guide/gnome_desktop#what_files_first:

What files first
================

Advice from Christian Rose on the GNOME team.

=======================  ==========  =======================================================================================================================================================================
 Application               Strings    Description                                                                                                                                                             
=======================  ==========  =======================================================================================================================================================================
gtk+                          1126    toolkit, very largish, but many messages are developer-oriented and can safely be ignored to begin with, but some few messages here are very visible to the end user    
 libgnomeui                    305    many user-visible menus and stuff                                                                                                                                       
 gnome-mime-data               350    user-visible file type desc. etc                                                                                                                                        
 libbonoboui                    96                                                                                                                                                                            
 gnome-vfs                      80    file size formatting etc                                                                                                                                                
 yelp                           71    help browser                                                                                                                                                            
 gedit                         640    text editor                                                                                                                                                             
 nautilus                     1449    file manager, also very largish, but not all messages here are immediately visible to the end user, even though many are                                                
 gnome-desktop                  88                                                                                                                                                                            
 gnome-panel                   587                                                                                                                                                                            
 gnome-session                 103                                                                                                                                                                            
 gnome-control-center      649                                                                                                                                                                                
 gdm2                         629     login manager                                                                                                                                                           
 eog                          170     image viewer                                                                                                                                                            
=======================  ==========  =======================================================================================================================================================================

... and then the rest in desktop + developer-libs.

FIXME use :ref:`toolkit:podebug` to get a better targeting on these files.

.. _../pages/guide/gnome_desktop#getting_a_cvs_account:

Getting a CVS account
=====================

You will need a CVS account to commit translations.  Read the `account policy
<http://developer.gnome.org/doc/policies/accounts/requesting.html>`_ so that
you know what information to provide. Most probably you will only get one if
you have supplied translations already or are a new team leader.

Read the `CVS guide aimed at translators
<http://developer.gnome.org/doc/tutorials/gnome-i18n/translator.html>`_ to
ensure that you commit correctly.  The steps are well laid out and very clear,
you can't go wrong if you follow it carefully. So old time users of CVS you
must read it.

Your translated PO files are placed within the package in GNU style, ie in the
po/ directory unlike the KDE system of all languages in one module.  This means
that you will have to checkout and add files to the various modules that you
use.  Eg to add translations of gnome-mime-data you will need to checkout the
module by that name.

**Note for people new to CVS**

This is not as complicated as it may seem.

Firstly, you need an account. Then, you have to set some environment variables
for your system. All that means is that you set some short-cuts, so the Gnome
CVS server and your system play nice together (none of those frosty silences ;)
). Everything you need to know is explained in `Getting the Most our of CVS in
Gnome <http://developer.gnome.org/tools/cvs.html>`_, as well as in `CVS guide
aimed at translators
<http://developer.gnome.org/doc/tutorials/gnome-i18n/translator.html>`_.

Take it one step at a time, and if you don't understand, email cvsmaster AT
gnomeD0T org

and if you come up with a dumb question I didn't ask on my journey into using
CVS, I think you get a prize. :D

We all learn in our own way, at our own pace, so don't worry about it, take one
step at a time, and ask questions.

The big secret about CVS, or it was to me, is how it does its magic. How on
earth can a server at gnome.org know what to do with a file on my computer?
Answer: that little "CVS" folder in the same directory. Any directory or file
you've checked out via CVS will have this magic folder. If it's not there,
forget about CVS: it simply won't work. (This also applies to SVN, a more
recent version control system.)

So first, you need to check out something. If you're translating, that will be
the "application_name/po" directory, e.g. "gedit/po", or your PO file and the
ChangeLog from that directory ("gedit/po/vi.po, gedit/po/ChangeLog"). You need
the ChangeLog, to record what changes you've made. Everybody does that, making
the ChangeLog a sort of "Who Did What, When and Why?" for that file.

Once you've checked out a file or directory, that magic CVS folder just sits
there, keeping track of things for the CVS server. If the application being
translated has just "branched", creating another version of itself (defeating
software birth control), then you need to check out that branch of the same
folder/files (e.g. "gnome-2-14/gedit/po"). That will create a "tag" file in the
CVS folder, which tells the CVS server to which version the file belongs. No
"tag" file, no "branch": in that case, the file belongs to HEAD (the newest
version of anything).

Once you have a copy of your directory or file, you can keep it "current" by
updating it. Each time you "update" your directory or file, it gets brought up
to date with its twin on the CVS server. Each time you add to your translation,
you "commit" it to the CVS server, which updates the file at the other end.

The whole aim of a system like CVS or SVN is not to have any conflicts, no
nasty arguments between these related files. The best way to avoid these
problems is to update your file before you make any changes. That way, you
should have the latest information.

It's also essential to check your translation for errors (via "msgfmt -cv")
before committing it. A PO file with errors can break the whole application,
when the file is re-integrated. The CVS server also runs the msgfmt check, so
it will reject your file if it still has errors. This can be handy if you've
forgotten to do it yourself.

So, all you need to do, once you've got your CVS account and set your
environment variables, is check out the files you're translating, keep them up
to date, and commit them when you've changed them, making sure they're free of
errors first. You may use the command-line to run CVS (which is simply a
program on your machine, and on the Gnome CVS machine at the other end), or you
may find, as I did, that a GUI front-end makes it easier to see what's going
on. Less typing, too. ;)  I use LinCVS for Mac OSX. There will most likely be a
GUI CVS client for your system, so give it a go. It can simplify things a lot.

CVS is just like keeping a shopping list. When you need new things, you add
them to the list. When things aren't needed any more, you cross them off. The
only difference between an ordinary shopping list and CVS, is that CVS
maintains two lists in different places. It's just like syncing your PDA.
Except other people can add to the list, or take things off it, so there are a
lot of checks to make sure everyone ends up with the same list.

Your translation file is that shopping list. Check out the original copy, keep
it up-to-date, and commit it when you change it. That's really all there is to
it.

So panic later. ;)  Read the CVS docs, take it one step at a time, and you'll
find it works very well. After all, if I could work it out, anybody can!

by Clytie, Vietnamese translator, gnome-vi

.. _../pages/guide/gnome_desktop#targeting_a_release:

Targeting a release
===================

Gnome follows a regular 6 monthly development cycle with even numbered stable
releases and odd number development releases.  The `release schedule
<http://www.gnome.org/start/unstable/>`_ will help you decide which release to
target.

If your team is moving quickly it might be good to target a stable minor
release.  This will also be the platform that most users will be on.  It also
presents the chance to have multiple releases as you move through each minor
release.  Otherwise, it would be more realistic to spend translators' effort on
next major stable release.

.. _../pages/guide/gnome_desktop#translation_status_page:

Translation Status Page
=======================

The `translation status page <http://l10n-status.gnome.org/>`_ keeps up to date
statistics on the progress of each language, your language should appear as
soon as your first file is committed to CVS.

.. _../pages/guide/gnome_desktop#setting_up_your_bugzilla_component:

Setting up your Bugzilla Component
==================================

FIXME I think this information is probably completely wrong or Ie misunderstood
it completely it was a long time ago ... DB

You need a Bugzilla component so that users of your language can report errors,
follows these `instructions
<http://developer.gnome.org/projects/bugsquad/maintainers.html>`_ to create one
for your language.

This information courtesy of Christian Rose.  You should return these details
to him at: menthos at gnome oeg.

You need to supply:

* language code
* language name (in English)
* language name (spelled in the language itself. We actually don't use this
  info in Bugzilla but on the http://www.gnome.org/i18n/ page. Please replace
  non-ASCII characters with proper HTML escape sequences. See the HTML source
  code of that page for examples)
* default owner (must be a valid bugzilla account). The default owner is the
  person who should be assigned the bugs by default. If he or she doesn't have
  a bugzilla account, he or she can create one at
  http://bugzilla.gnome.org/createaccount.cgi.
* default qa contact (must be a valid bugzilla account). The default QA contact
  is usually the person who should make sure the bug was fixed properly by the
  assignee. If the qa contact person doesn't yet have a bugzilla account, he or
  she can create one at http://bugzilla.gnome.org/createaccount.cgi. This field
  is optional, you don't need to decide on a default qa contact if you don't
  want to.
* component description. Usually of the form "Here you can place your bugs
  about $LANGUAGENAME [$LANGUAGECODE] translations". Example: "Here you can
  place your bugs about Swedish [sv] translations". If you have the
  possibility, try also to translate this into ASCII-only English, and we'll
  use the translation as well.

You have the option of assigning this the bug reports to a mailing list:

If you want, there's also the possibility to use a mailing list instead of an
individual for the default owner and/or default qa contact fields.  It's a bit
more complicated; among other things you need access to the mailing list
configuration. Here is what you should do if you want a mailing list in one or
both of the fields above:

- Create a bugzilla account for your mailing list, i.e. a Bugzilla account with
  your list's address as account name.
- Subscribe the bugzilla deamon address (bugzilla-daemon@widget.gnome.org) to
  your mailing list, but also disable *ALL* mail from the mailing list to this
  address (If it's a Mailman mailing list you can change
  bugzilla-daemon@widget.gnome.org's mailing list options to NOMAIL).

.. _../pages/guide/gnome_desktop#application_specific:

Application Specific
====================

There are some applications that need specific treatment.  These are those:

.. _../pages/guide/gnome_desktop#gdm2:

gdm2
----

The login manager needs patches to gui/gdmlanguages.c and config/locale.alias
to add your languages. Email your patch to "George" 

Suggested bug report and related email for adding English (Canadian), use as a
reference:

* http://mail.gnome.org/archives/gnome-i18n/2004-February/msg00256.html
* http://bugzilla.gnome.org/show_bug.cgi?id=135053

Also Arabic issue highlights how it all fits together:

* http://mail.gnome.org/archives/gnome-i18n/2004-March/msg00177.html

Actual CVS diffs to add Afrikaans, Northern Sotho and South African English

* http://cvs.gnome.org/viewcvs/gdm2/config/locale.alias?r1=1.38&r2=1.39
* http://cvs.gnome.org/viewcvs/gdm2/gui/gdmlanguages.c?r1=1.41&r2=1.42

.. _../pages/guide/gnome_desktop#translating_documentation:

Translating Documentation
=========================

**Update**

A large number of Gnome docs are now available for translation, via the
gnome-doc-utils package, in both XML and PO format. This number is increasing
steadily. We can look forward to having all Gnome docs available in both
formats. Here is the current list:

http://kvota.net/doc-l10n/by-modules.html

The modules are listed alphabetically. You can see the POT (template file, all
original strings but no translations yet) at the top of each module listing.
Then the current translations are listed. Thus you can start with the POT, if
there isn't a translation for your language yet, or update the current file.
(Making sure you co-ordinate this with the `translation team
<http://l10n.gnome.org/teams/>`_ for your language, so effort is not
duplicated.) As the original documentation is updated, so is the POT, and so
are the existing translations. Just like the application PO files listed under
your language on the Gnome l10n status pages.

**Older information**

On the Gnome-i18n mailing list Christian Rose says, "At the moment, we don't
translate documentation the same way we translate the user interfaces (i.e.
with "po" files). However, we hope to do so at some point, since po files
provide several essential advantages compared to maintaining translations of
plain XML. One such advantage is that it divides documents into smaller pieces
(messages), allowing you to see exactly what parts have an inconsistent
translation and need updating."

"For the moment, what you may want to do is to use the "xml2po" utility in the
"gnome-doc-utils" package/module. This will allow you to transform the
XML/DocBook source of a document into a pot file that you can translate and
maintain. Also, it allows you to reverse the process and create a translated
XML file out of the po file later on."

.. _../pages/guide/gnome_desktop#finding_po_files:

Finding PO files
================

Technical notes on finding PO files via http://l10n-status.gnome.org/ from
Simos Xenitellis on the translate-pootle list:

You can get .po files from the statistics pages. Have a look at
http://l10n-status.gnome.org/gnome-2.10/index.html Click on individual language
pages and they will lead you to the .po files. These files are updated daily,
so the "resolution" of freshness is just one day (not bad).

You can also look at all the PO and POT files for a branch in the PO/
subdirectory like this: http://l10n-status.gnome.org/gnome-2.12/PO/

We use the following scripts while making a translation memory IN-A-GLANCE::

    % wget -O desktop.html http://l10n-status.gnome.org/gnome-2.10/el/desktop/index.html
    % wget -O developer-libs.html http://l10n-status.gnome.org/gnome-2.10/el/developer-libs/index.html
    % grep 'el\.po' desktop.html developer-libs.html | awk -F\" '{print $6}' | sort | uniq |awk -F\/ '{print $4}' | awk '{printf "wget -O GNOME210-%s http://l10n-status.gnome.org/gnome-2.10/PO/%s\n", $1, $1}' | sh

David Fraser has also created a script that pulls the files out of CVS after
finding them on the l10n-status web page

.. code-block:: bash

    #!/bin/bash
      lang=$1
      branch=2.10
      export CVSROOT=:pserver:anonymous@anoncvs.gnome.org:/cvs/gnome
      if [[ $lang == "" ]]
       then
        echo syntax $0 lang
        exit
       fi
      [[ -d $lang ]] || mkdir $lang
      cd $lang
      [[:f_desktop.html]] && rm -f desktop.html
      [[:f_developer-libs.html]] && rm -f developer-libs.html
      wget -O desktop.html http://l10n-status.gnome.org/gnome-$branch/$lang/desktop/index.html
      wget -O developer-libs.html http://l10n-status.gnome.org/gnome-$branch/$lang/developer-libs/index.html
      pofiles=`grep ${lang}'\.po' desktop.html developer-libs.html | awk -F\" '{print $6}' | sort | uniq | awk -F\/ '{print $4}'`
      for pofile in ${pofiles}
       do
        basefile=`basename $pofile .${lang}.po`
        actualbranch=""
        for possiblebranch in HEAD gnome-${branch}
         do
          branchext=`echo $possiblebranch | sed 's/[.]/-/g'`
          isbranch=0
          echo $basefile | grep $branchext >/dev/null && isbranch=1
          if [[ $isbranch == 1 ]]
           then
            basefile=`basename $basefile .$branchext`
            actualbranch=$branchext
           fi
         done
        # this would get it straight off the web page:
        # wget -O ${pofile} http://l10n-status.gnome.org/gnome-$branch/PO/${pofile}
        # this checks it out of CVS:
        if [[ $actualbranch == "" ]]
         then
          cvs -z3 co $basefile/po/$lang.po
         else
          cvs -z3 co -r $actualbranch $basefile/po/$lang.po

        fi
       done


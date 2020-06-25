
.. _../pages/guide/gnome_desktop#gnome:

GNOME
*****

`GNOME <https://www.gnome.org/>`_ is a feature rich Linux graphical desktop environment.  The project has
quite an established localisation initiative.

Since this page has been created, many things in GNOME has changed, and they
have good documentation and infrastructure to help translators. 

The most important documentation for translating GNOME is therefore at the
GNOME website: http://wiki.gnome.org/TranslationProject/

The rest of this document is kept in place for the time being, but a lot of it
is now out of date and not 100% accurate any more.

.. _../pages/guide/gnome_desktop#essential_reading:

Essential Reading
=================

Please familiarise yourself with these before proceeding:

* `GNOME Translation Project <https://wiki.gnome.org/TranslationProject/>`_
* `Localisation Guide
  <https://wiki.gnome.org/TranslationProject/LocalisationGuide>`_
* `Join the GNOME Translation Project
  <https://wiki.gnome.org/TranslationProject/JoiningTranslation>`_

.. _../pages/guide/gnome_desktop#useful_urls:

Useful URLs
===========

* `Status Page <http://l10n.gnome.org/releases/>`_

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

.. _../pages/guide/gnome_desktop#committing_translations:

Committing translations
=======================

Translations can be committed directly from `Damned lies
<https://l10n.gnome.org/>`_ in most cases. In the rare occasions where this 
won't work, you can ask on the `gnome-i18n mailing list
<http://mail.gnome.org/mailman/listinfo/gnome-i18n/>`_ and someone should be
able to do it for you. If you really need a git account, you should read the 
git related pages listed on the `wiki
<https://wiki.gnome.org/TranslationProject>`_


.. _../pages/guide/gnome_desktop#targeting_a_release:

Targeting a release
===================

GNOME follows a regular 6 monthly development cycle with even numbered stable
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

The `translation status page <http://l10n.gnome.org/>`_ keeps up to date
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
- Subscribe the bugzilla daemon address (bugzilla-daemon@widget.gnome.org) to
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

A large number of GNOME docs are now available for translation, via the
gnome-doc-utils package, in both XML and PO format. This number is increasing
steadily. We can look forward to having all GNOME docs available in both
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
your language on the GNOME l10n status pages.

**Older information**

On the gnome-i18n mailing list Christian Rose says, "At the moment, we don't
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

Technical notes on finding PO files via http://l10n.gnome.org/ from
Simos Xenitellis on the translate-pootle list:

You can get .po files from the statistics pages. Have a look at
http://l10n.gnome.org/gnome-2.10/index.html Click on individual language
pages and they will lead you to the .po files. These files are updated daily,
so the "resolution" of freshness is just one day (not bad).

FIXME The following script won't work anymore.
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



.. _../pages/guide/openoffice.org#openoffice.org:

OpenOffice.org
**************

OpenOffice.org is the leading cross-platform Office suite.  Its a large project and a large localisation undertaking, but it is an important
component of a localised desktop.

.. _../pages/guide/openoffice.org#resource:

Resource
========

  * KhmerOS --- These pages prepared by Javier SOLA are by far your best resource for localising OpenOffice.org
    * `Localisation Guide to OpenOffice.org 2.0 <http://www.khmeros.info/tools/localization_of_openoffice_2.0.html>`_
    * `Making OpenOffice.org 2.0 locale files <http://www.khmeros.info/tools/openoffice_locale_.htm>`_
    * `Creating your languages collation sequence for OpenOffice.org 2.0 <http://www.khmeros.info/tools/Collation_in_ooo_2.0.html>`_
    * `Some localisation tips for OpenOffice.org 2.0 <http://www.khmeros.info/tools/localization_tips.html>`_
  * `Current and in progress localisations <http://l10n.openoffice.org/languages.html>`_

.. _../pages/guide/openoffice.org#what_is_your_languages_lcid:

What is your language's LCID
============================

Microsoft defines LCIDs for various locales.  You need to know this so that OpenOffice.org can work well on Windows and also so that documents you create can move seamlessly between MS Word and Office Writer as the language identifier is correct.

There are a number of places that you can use to identify the LCID.  For most languages they will all agree but in some cases (See 1072/Sutu/Sesotho) it helps to look at all list to help clarify what exactly Microsoft meant.

  * `List of Locale ID (LCID) Values as Assigned by Microsoft <http://www.microsoft.com/globaldev/reference/lcid-all.mspx>`_
  * `Microsoft Word 2000 <http://support.microsoft.com/kb/q221435/>`_
  * `Windows XP/Server 2003 <http://www.microsoft.com/globaldev/reference/winxp/xp-lcid.mspx>`_ includes XP service pack 2
  * `National Language Support Constants <http://msdn.microsoft.com/library/default.asp?url=/library/en-us/intl/nls_238z.asp>`_ much clearer layout and mentions codepage.  Doesn't seem completely up to date though.

.. _../pages/guide/openoffice.org#what_to_do_first:

What to do first
================

This is a very large application.  If you can do a smaller section of the total and still have a useful product then that will help.  We created this :doc:`rough targeting guide <project/ooo/whatfirst>` using OpenOffice.org 1.1.3 and :doc:`toolkit/podebug`

.. _../pages/guide/openoffice.org#localisation:

Localisation
============

Read the localisation documentation on the OpenOffice.org website:
http://wiki.services.openoffice.org/wiki/Category:Localization

Things are now very easy since they are using `Pootle <http://qooxdoo.org/pootle/index>`_. You can translate online on Pootle, or download the files to work offline with something like `Virtaal <http://qooxdoo.org/virtaal/index>`_.

.. _../pages/guide/openoffice.org#gsicheck:

gsicheck
--------

The OpenOffice.org guys have a tool for checking the SDF file called gsicheck.  But of course you don't want to build the whole of OpenOffice.org simply to get one tool. :doc:`toolkit/pofilter` will pick up most errors that gsicheck does but its nice to know that your SDF is good before submitting it. Read more and download from the OpenOffice.org website:

http://wiki.services.openoffice.org/wiki/Gsicheck

Then install it and use it

  tar xvzf gsicheck-1.7.8_2.0m122.tar.gz
  cd gsicheck-1.7.8_2.0m122
  ./gsicheck -c <GSI/SDF file>

Now go and fix the errors that it detected.  You should correct these in your PO files.

.. _../pages/guide/openoffice.org#autocorrect:

AutoCorrect
===========

The OpenOffice.org AutoCorrect file is a zip file called for example, acor_en-US.dat.  :doc:`Søren Thing Pedersen <stp@things.dk>` has created `csv2acor.py <http://da.openoffice.org/files/documents/122/2851/csv2acor.py>`_ which generates an AutoCorrect file from CSV sources.  
The autocorrect file contains 3 XML files:

  * DocumentList.xml - pairs of mistyped words and their correct spelling
  * SentenceExceptList.xml - abbreviations that end with a fullstop that should be ignored when determining the end of a sentence
  * WordExceptList.xml - Words that may contain more than 2 leading capital eg. CDs

When using csv2acor.py your need to have 3 files with the same name as above but with a .csv file extension.  WordExceptList.csv and SentenceExceptList.csv contain just a list of entries one per line surrounded by double quotes (").  DocumentList.csv is a comma separated list with the mistyped word in the first column and the correct word in the second column, all also surrounded by double quotes.

The translation program `Virtaal <http://qooxdoo.org/virtaal/index>`_ also makes use of these files, so consider contributing it to this project as well.

.. _../pages/guide/openoffice.org#wordexceptlist.xml:

WordExceptList.xml
------------------

If you have an existing spell checking wordlist then use the following to extract potential words:

::

    egrep "^[A-Z][A-Z][a-z]" spell-wordlist > WordExceptList.new

This extracts all words that start with two capitals followed by a lower case letter.  Add all the characters valid in your language.

.. _../pages/guide/openoffice.org#sentenceexceptlist.xml:

SentenceExceptList.xml
----------------------

If you have an existing spell checking wordlist then use the following to extract potential words:

::

    egrep "\.$" spell-wordlist > SentenceExceptList.new

This extracts all entries that end in a fullstop.

.. _../pages/guide/openoffice.org#documentlist.xml:

DocumentList.xml
----------------

If you have an existing DocumentList.xml you can convert it to CSV using the following:

::

    sed "s/<block-list:block block-list:abbreviated-name=\"/\"\\n\"/g;s/\" block-list:name=\"/\",\"/g;s/\"\/>//g" < DocumentList.xml > DocumentList.csv

Your'll need to edit DocumentList.csv to remove some of the remaining XML data.  

A cleaner method is to use the following XSLT - this way you don't have to clean any XML data (so this is suitable for batch mode):

::

    <?xml version="1.0" ?>

    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
     version="1.0"
     xmlns:block-list="http://openoffice.org/2001/block-list">

     <xsl:output method="text" encoding="utf-8"/>

    <xsl:template match="//block-list:block">
      <xsl:text>"</xsl:text>
      <xsl:value-of select="@block-list:abbreviated-name"/>
      <xsl:text>"</xsl:text>
       <xsl:text>,</xsl:text>
       <xsl:text>"</xsl:text>
       <xsl:value-of select="@block-list:name"/>
       <xsl:text>"</xsl:text>
       <xsl:text>&#x0a;</xsl:text>
      </xsl:template>

    </xsl:stylesheet>
    </xml>

Run this script through any XSLT processor, e.g., for Saxon, type:

::

    java -jar saxon8.jar DocumentList.xml <name-of-xslt> >DocumentList.new

.. _../pages/guide/openoffice.org#generating_your_new_autocorrect_file:

Generating your new AutoCorrect file
------------------------------------

Then run csv2acor.py acor_xx-YY.dat where xx-YY is your language and country code.

.. _../pages/guide/openoffice.org#spell_checker_and_hyphenation_in_the_official_build:

Spell Checker and Hyphenation in the official build
===================================================

In order to add your spell checker and hyphenation file to OpenOffice.org CVS you need to do the following:

  * Ensure your license is compatible
  * Fill in the form at http://external.openoffice.org/
  * Fill out an Issue assigned to mh who needs to process the approval for inclusion

.. _../pages/guide/openoffice.org#holidays:

Holidays
========

  * wizards/source/schedule/LocalHolidays.xba

Looks like a StarBasic program that allows you to specify holidays, etc.  FIXME need to check this more carefully

.. _../pages/guide/openoffice.org#child_workspace:

Child Workspace
===============

OpenOffice developers use what they call child workspaces to make fixes and commit changes.  These are usually linked to related bugs in IssueZilla.

Here some instructions to help you track your changes and see if they have been integrated/fixed:
  - go to: http://eis.services.openoffice.org/
  - log on with your openoffice account. Example coni@openoffice.org, and password
  - click Childworkspaces
  - click Search
  - enter localisation% in the Name field
  - wait....

Now you see which l10n CWS have been integrated and which not. By 
clicking on the CWS name you see the list of the bugs registered to that 
CWS. Once approved by QA you'll exactly know in which milestone the CWS 
has been integrated.
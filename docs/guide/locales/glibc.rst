
.. _../pages/guide/locales/glibc#glibc_locale_files:

Glibc locale files
******************

Locale files define the culural conventions of a language and region. The Glibc locale files are used on all GNU/Linux systems so are needed for software that will run on Linux.

.. _../pages/guide/locales/glibc#data:

Data
====

When creating loclale data for South African locales the data files are stored in 
version control.  While these files are in development the reference version is the one contained there.  
When the files are suitably mature they are submitted to glibc and those 
become the reference versions while those located in version control will then contain 
any development work if needed.

In the mature stage the locale data can be abandoned and development made against versions in glibc.

It is suggested that you follow a similar model.

.. _../pages/guide/locales/glibc#tools:

Tools
=====

The following are tools located in the the Translate.org.za Subversion repository.  They are 
useful for building and testing glibc locales:

| `missing <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/missing?view=markup>`_       | determines if a locale file has a certain locale field or not.  |
| `error <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/errors?view=markup>`_         | displays any compilation errors detected                        |
| `install <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/install?view=markup>`_       | performs a test install (use -r for a real install - must be root)  |
| `definition <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/definition?view=markup>`_    | prints the value of a locale field (installed locales only)     |
| `locale-escape <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/locale-escape?view=markup>`_ | converts your locale into <UNNNN> format                            |
| `check-dates <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/check-dates?view=markup>`_   | prints a list of the LC_TIME defined date formats for the locale    |

.. _../pages/guide/locales/glibc#editing:

Editing
=======

If you edit your locale file using `vim <http://www.vim.org>`_ then you can make use of the 
fdcc file highlighter.  Newer versions of vim should already have this file installed and will detect
the filetype automatically.  If your file is not automatically highlighted then you will need to 
`download <http://www.vim.org/scripts/download_script.php?src_id=2894>`_ the file 
and follow `these instructions <http://www.vim.org/scripts/script.php?script_id=917>`_

It is preferable to edit your locale in UTF-8 and then use `locale-escape <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/locale-escape?view=markup>`_ to encode your work in the
<UNNNN> format used in glibc locale files.  Use locale-escape as follows:

::

    cat unescaped-locale | ./locale-escape > escaped-locale

You can also use the iconv tool to achieve the same escaping (this will only work if your version of iconv supports the --unicode-subst option):

::

    $ echo ÐÑÑÑÐÐÐ |
      iconv -f UTF-8 -t ASCII --unicode-subst='<U%04X>'

    <U0420><U0443><U0441><U0441><U043A><U0438><U0439>

.. _../pages/guide/locales/glibc#%_charset:

% Charset
---------

All locales should contain a comment like

  % Charset: UTF-8

at the beginning.

The recommendation is not to use ISO-8859-1 as it's outdated, unless there is a *substantial* install base.  Ideally
you should only use UTF-8.  But if necessary, ISO-8859-15 is preferred above ISO-8859-1.

.. _../pages/guide/locales/glibc#checking:

Checking
========

For a quick check first install the locale as root run:

  install -r xx_XX

Then run checks, either

  definition xx_XX

Or

  definition -c LC_TIME xx_XX

And go through each one checking that the entries are correct

.. _../pages/guide/locales/glibc#defining_lc_time:

Defining LC_TIME
================

Use 'man date' to see what variables are valid in a locale file date and time formating.  
If you want to remove space padding then use minus in the variable eg: %-e will print the 
day of the week without a space padding before the number.  Eg '[space]1' becomes simply '1'

.. _../pages/guide/locales/glibc#gentoo_users:

Gentoo users
============

On gentoo you should NOT use the install script, but rather execute

  localedef -i <your_escaped_file> -f UTF-8 <your_locale>.UTF-8 -c -v

The install script uses locale-gen and can give you quite a lot of trouble with accented chars.

.. _../pages/guide/locales/glibc#resources:

Resources
=========

Website and such:

  * `glibc locales mailing list <http://sourceware.org/ml/libc-locales/>`_
  * `glibc website <http://sourceware.org/glibc/>`_
  * `glibc bugzilla <http://sources.redhat.com/bugzilla/>`_

Producing you locale file:

  * `A site dedicated to glibc locale files and their creation <http://lh.2xlibre.net/>`_
  * A `guide <http://www.kizito.uklinux.net/download/LocaleGuide.tar>`_ developed by the Lugandan locale creator
  * The latest `Afrikaans <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/localedata/af_ZA?view=markup>`_ and `Zulu <http://zaf.svn.sourceforge.net/viewvc/zaf/trunk/locale/localedata/zu_ZA?view=markup>`_ locales both heavily commented with references for certain locale data

Resource specific to the ISO standard for locales files:

  * The `ISO 14652 <http://anubis.dkuug.dk/jtc1/sc22/wg20/docs/n897-14652w25.pdf>`_ standard that defines locale or fdcc files (seems to be the latest version fo the standard)
  * `Comments from Ulrich Drepper <http://anubis.dkuug.dk/jtc1/sc22/wg20/docs/n922-linux-14652.txt>`_ the creator of locale implementation in glibc
  * `Keld Simonsen's comments on Drepper's mail <http://anubis.dkuug.dk/jtc1/sc22/wg20/docs/n925-14652-keld.txt>`_ (Simonsen manages the ISO 14652 standard)

.. _../pages/guide/locales/glibc#notes:

Notes
=====

All changes to glibc locales must also be reflected into the IBM ICU 
locales. So you need to post 'bug' reports against ICU and possibly 
against the OO locales as well.

.. _../pages/guide/locales/glibc#submitting_your_new/update_locale_to_glibc:

Submitting your new/update locale to glibc
==========================================

**Note:** double check everything before sending.  Its easy to overlook silly things
like comments that still apply to a previous language.  Check them all again.

Officially you should send your locale files to:

  * ` <http://www.gnu.org/software/libc/bugs.html>`_ or
  * :doc:`bug-glibc@gnu.org` or 
  * Use the glibcbug script which seems to email glibc-bug-reports-stable@gnu.org

I have in the past sent email to :doc:`Ulrich Drepper <drepper@redhat.com>`, the glibc maintainer.  This is not guarenteed to work but if all else fails try this route.

Attach the file and preferably a diff between your update and the one in glibc CVS

   diff -u xx_XX.glibc_version xx_XX.updated > xx_XX.diff

Make the subject very clear: "Update xx_XX glibc locale file".  Attach the files and send.

You also need to patch against `localedata/SUPPORTED <http://sources.redhat.com/cgi-bin/cvsweb.cgi/libc/localedata/SUPPORTED?content-type=text/x-cvsweb-markup&cvsroot=glibc>`_ so that you can define what charsets you can use with your locales.
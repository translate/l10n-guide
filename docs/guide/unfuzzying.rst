
.. _../pages/guide/unfuzzying#string_qa:

String QA
=========

The quality of translations is proportional to the quality of your original
strings. You can ensure higher accuracy of translations by adding `contextual
information
<http://www.gnu.org/software/gettext/manual/html_node/Contexts.html#Contexts>`_,
but the original string itself is the source of the translation. If you put the
same care into constructing your original strings as you do into your coding,
you will have effective and intuitive translated software.

.. _../pages/guide/unfuzzying#checking:

Checking
--------

Just as you always read over a line of code before running it, always read over
a string before using it. That single check will save you a lot of errors.
Spellchecking is also useful in catching typos. You can spellcheck PO files
using :ref:`pofilter <toolkit:pofilter>`.

.. _../pages/guide/unfuzzying#reports:

Reports
-------

You can also receive reports from translators who have spotted typo or other
errors in your original strings. Translators are a useful resource for this
kind of error.

.. _../pages/guide/unfuzzying#after_fixing:

After fixing
------------

Once you make typo or grammar fixes in your original strings, unless you have
actually changed the meaning of those strings, you want to **unfuzzy** them.
Strings are automatically marked fuzzy on update when the original text has
changed. This is useful when updating translations, but in the case of
typo/grammar fixes, it means that **every** translator for **every** language
will have to check **every** string you've fixed. This is a huge waste of
resources, and thus a very unpopular situation with translators. Imagine having
to check every line of code because someone had fixed the spelling in a
comment.

.. _../pages/guide/unfuzzying#howto_unfuzzy:

Howto Unfuzzy
-------------

So, good i18n practice is to **unfuzzy** strings after changes that don't alter
their meaning (e.g. typo/grammar fixes). How do we do that?

Oddly enough, since every project does this regularly, there doesn't seem to be
a quick and effective method. All we're really doing is diffing the changed
files with the previous files, then removing all fuzzy tags which have only
appeared in the changed files. So it could be done with :ref:`pogrep
<toolkit:pogrep>`: if you work it out, please add the command here.

Meanwhile, the Debian project has `its own method
<http://www.debian.org/doc/developers-reference/best-pkging-practices.html#bpp-i18n-debconf>`_,
and there are  a couple of useful items in the gettext manual (`Fuzzy Entries
<http://www.gnu.org/software/autoconf/manual/gettext/Fuzzy-Entries.html>`_ `PO
Mode Index
<http://www.gnu.org/software/autoconf/manual/gettext/PO-Mode-Index.html>`_).

.. _../pages/guide/unfuzzying#gettext_and_po4a:

Gettext and Po4a
----------------

*Nicolas François* adds:

In some specific cases, i.e. when all the PO files fully translated before the
typos are fixed, `msgattrib
<http://www.gnu.org/software/gettext/manual/html_node/msgattrib-Invocation.html#msgattrib-Invocation>`_
(gettext) is very fast and very safe.

The `po4a <http://po4a.org/>`_ package has a tool, msguntypot, which tries to
deal with the generic case, but the process to use it (8 steps) is quite
complicated and thus error-prone.  msguntypot is not yet well-tested either,
and all files should be backed-up before using it.

Unless you need to use msguntypot, I would recommend unfuzzying only complete
translations and using msgattrib.

.. _../pages/guide/unfuzzying#translate_toolkit:

Translate Toolkit
-----------------

*Friedel Wolff* adds:

If you want to unfuzzy all fuzzies in a single file, this should work:

::

    msgattrib --clear-fuzzy input.po -o output.po

If you want to work recursively on many files, or want to select the messages
on which to do the unfuzzying, using :ref:`pofilter
<toolkit:pofilter>`/:ref:`pogrep <toolkit:pogrep>` with :ref:`pomerge
<toolkit:pomerge>` (all Translate Toolkit programs) might be more powerful.


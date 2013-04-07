
.. _../pages/guide/tools/glossary#glossary_tools:

Glossary Tools
**************

For a quality translation it is important to develop a good glossary of terms.
In this section we list the various tools that can help you create and manage
such a glossary.

.. _../pages/guide/tools/glossary#glossary_management:

Glossary management
===================

To create a glossary of terms (words and phrases), you can either create it as
you go along during a pilot project, or you can extract terms from the source
text and compile them into a glossary.

The advantage of creating it during a pilot project is that the term list is
created in context, but the disadvantage is that it is a slower method and it
yields less terms (although most terms are useful).  The advantages of
automatic term extraction are that it is fast and yields potentially more
relevant terms.  The disadvantage is that terms are not viewed in context, and
you have to initially search through many unimportant or useless terms.

The disadvantages of either method can be overcome, though.

.. _../pages/guide/tools/glossary#bulk_term_extractors:

Bulk term extractors
--------------------

.. _../pages/guide/tools/glossary#bilingual_term_extractors:

Bilingual term extractors
^^^^^^^^^^^^^^^^^^^^^^^^^

Since some texts are available in bitext format (which can be a TM or a PO file
or similar), it would be possible through smart guessing to figure out which
source words fit which target words.  These tools are generally called "word
aligners" in the computational linguistics industry, and sadly most "free"
tools are free for academic purposes only.  Word aligners have great potential
because bitexts are usually translated by humans, and so the terms are likely
to be accurate.

You might also be able to do monolingual term extraction on a TM.

.. _../pages/guide/tools/glossary#poterminology:

Poterminology
"""""""""""""

The `Translate Toolkit <http://toolkit.translatehouse.org>`_ contains
:ref:`poterminology <toolkit:poterminology>` which can do bilingual term
extraction. It does frequency analysis on the input files, and uses stop words
to improve the results.  It has several parameters that allow you to change its
behaviour.  It does some alignment and fills in all translations for a term
that it found in the translation files.

.. _../pages/guide/tools/glossary#monolingual_term_extractors:

Monolingual term extractors
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Monolingual term extractors usually look for words or phrases that occur more
than X number of times in the text, or for words that occur in the text but do
not occur in a dictionary or established term list.  Such an extraction usually
contains a large percentage of useless terms unless steps are taken to remove
irrelevant repetitions from the result.

.. _../pages/guide/tools/glossary#poterminology_for_monolingual_extraction:

Poterminology for monolingual extraction
""""""""""""""""""""""""""""""""""""""""

:ref:`poterminology <toolkit:poterminology>` (see above) can also work on
untranslated files, in which case it would simply be doing monolingual term
extraction.

.. _../pages/guide/tools/glossary#extphr32_by_tim_craven:

ExtPhr32 by Tim Craven
""""""""""""""""""""""

Tim Craven's ExtPhr32 for MS Windows is not GPL but it is freeware for all
purposes.  It is very fast.  Unfortunately it converts all terms to uppercase.
You can also use a stoplist.  You can choose how many occurances of a term must
be the minimum, and you can choose the minimum number of words in a term.  The
output can be exported to two column plaintext (the second column contains a
count).

.. _../pages/guide/tools/glossary#plustools_from_wordfast:

PlusTools from Wordfast
"""""""""""""""""""""""

PlusTools is a macro that runs within MS Word on MS Windows.  It is not GPL but
it is freeware for all purposes.  It is slow but potentially useful for smaller
texts because it can exclude words that occur in MS Word's spellchecker and/or
thesaurus, or words that have less than X synonymns in the thesaurus.  You can
also exclude certain words (similar to a stoplist, but you can add any words to
it), words beginning with a certain set of characters, and words that are
smaller than X number of characters.

.. _../pages/guide/tools/glossary#other_tools:

Other tools
"""""""""""

* http://uplug.sourceforge.net/

GPL collection of corpus tools.

* SDL MultiTerm 7 Extract Freelance

Extracts terms from Trados compliant bitexts.  Pricetag: EUR 525.00 per single
user licence.

.. _../pages/guide/tools/glossary#concordancers:

Concordancers
-------------

A concordancer is a tool that displays a word in context.  An excellent, easy
to use concordancer, is Corpsis (previously Tenka Text).  Or, if you're willing
to pay some money, try Mike Scott's Wordsmith tools.  Corpsis can display
multiwords phrases using wildcards.

http://corpsis.sourceforge.net/

.. _../pages/guide/tools/glossary#glossary_editors:

Glossary editors
----------------

Whichever way you look at it, a glossary is a database, and most comprehensive
glossaries can be edited in a database editor tool.  For simple, three-column
glossaries, a spreadsheet program may be all that's necessary, though.

`Virtaal <http://virtaal.translatehouse.org>`_ can be used to edit many
formats, including many formats commonly used for storing terminology.

(todo)

.. _../pages/guide/tools/glossary#glossary_viewers:

Glossary viewers
----------------

There are quite a few glossary viewers, but they often require that you convert
your glossary to their weird format.  Examples are StarDict, Jalingo,
jDictionary and Pododict.  If you're willing to pay for a non-free product,
AnyLexic is an excellent glossary tool that supports simple formats too.

`Virtaal <http://virtaal.translatehouse.org>`_ can open many formats, including
many formats commonly used for storing terminology.

(todo)

.. _../pages/guide/tools/glossary#web_based_creation_and_management_tools:

Web based creation and management tools
=======================================

* `Pootle <http://pootle.translatehouse.org>`_ can do terminology extraction
  based on :ref:`poterminology <toolkit:poterminology>` since version 2.1.
  Term lists can be translated and downloaded for offline editing/use.
* `KiPot <http://www.it46.se/kipot/>`_ --- produced by `it46
  <http://www.it46.se/>`_ and used by the Kiswahili Localisation team
* `Gakartuleba.org <http://gakartuleba.sapikhvno.org/glossary_en.php>`_ ---
  custom tool used by the Georgian localisation team (requires free account)
* `Glossword <http://glossword.info>`_ --- helps to create your own dictionary or dictionaries


.. _../pages/guide/spell_checker_case_studies#a_spellchecker_for_your_language:

A spellchecker for your language
********************************

Does the current spellchecking software work well for your language? As software is translated into more and more languages, we are finding that writing aids software based on European-language structures is less and less effective.

So what can we do about it? It's time to review our current resources, and work together to create writing aids tools appropriate to a wider range of languages, or appropriate to specific languages. Some case-studies are discussed below.

This page will link to discussions on this subject in different mailing lists, to wiki pages detailing it for and in different languages, and to software being developed, or which can be used, to meet these needs.

Please add any information you think could be useful. :)

.. _../pages/guide/spell_checker_case_studies#case_studies:

Case Studies
============

.. _../pages/guide/spell_checker_case_studies#vietnamese:

Vietnamese
----------

.. _../pages/guide/spell_checker_case_studies#nguyễn_thái_ngọc_duy:

Nguyễn Thái Ngọc Duy
^^^^^^^^^^^^^^^^^^^^
I have been working on vspell, a Vietnamese spell checker, since 2003
 (there were huge gaps when I did not work on it at all, though). The
 source code can be found `here <http://repo.or.cz/w/vspell.git>`_ (click on the first "snapshot" link to get a tarball). The core idea is quite simple. It is
 trained with a word-segmented corpus. When a sentence is given
 (actually a phrase because it still does not understand "sentence"),
 it will generate similar sentences based on common spelling errors. It
 then uses statistics from the corpus to determine which sentence (the
 original one or one of the generated ones) is "better". If a generated
 one is better, then it assumes the original one is misspelled. That's
 all. The rest of work is matching the original one and the "right" one
 to see differences between them and tell users about that.

 The result as of three months ago was not very promising: precise rate
 was about 60%-70% (I expected at least 80% to be useful). I was
 investigating to see why the precise rate was low, and had some
 technical difficulties.

I've been working on a spellng checker for Vietnamese. The problems are:
  * It requires input as phrases, not words. As far as I can tell, hunspell and almost all spelling checkers take input as words.
  * It uses a lot of memory (≥ 256MB for itself)
  * It needs to be trained to be able to differentiate good phrases and bad phrases. There are some difficulties in my training method (I don't know, I may give up on my method, as it is becoming infeasible, something with number explosion).
  * It's not stable. I spent most of my time training it and testing it with a small sample. It liked to crash back then ;)

The first problem means we must interact with Openoffice without
Hunspell. That's not easy to do.

But the main problem is the third. My approach is statistics-based. It
requires lots of (correct) word-aligned sentences to be trained on.
That kind of corpus for Vietnamese does not exist (at least freely).
So my workaround is to take a raw corpus and train repeatedly to get
better result each iteration. The workaround has number explosion
problem. It breaks 32-bit integer limit easily and also "long double"
limit. In short, until I find a feasible training method, my spell
checker is no use.

.. _../pages/guide/spell_checker_case_studies#the_basic_problem_in_vietnamese:

The basic problem in Vietnamese
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Vietnamese "words" are often composed of more than one word. Words are usually monosyllabic, so we can think of them as syllables of these longer words. However, current spellchecking tools treat each Vietnamese "syllable" as a separate word. This means that when you make a mistake that is still a valid word, e.g. typing **màu hình** instead of **màn hình**, current spellchecking tools will still recognize « màu » and « hình » as valid separate words, and not detect the error.

.. _../pages/guide/spell_checker_case_studies#ivan_garcia:

Ivan Garcia
^^^^^^^^^^^
(Note: Ivan's current `Hunspell <http://code.google.com/p/hunspell-spellcheck-vi/>`_ spellchecking dictionary is being used in OpenOffice.org, and in Firefox and Thunderbird.)

.. _../pages/guide/spell_checker_case_studies#duy:

Duy
^^^

I know my statistical method isn't ideal. A rule-based approach would be more realistic. But the rule-based one requires human power to build the ruleset. A rule generation approach like `TBL <http://stp.ling.uu.se/~torbjorn/Mutbl/bibliography.html>`_ (Tranformation Based Learning) requires an annotated corpus, which I don't have.

Identifying composed words is also what I want my spellchecker to do.

I don't think a grammar-checker is viable, due to the complexity of Vietnamese grammar. My spellchecker is basically a spellchecker. Although it could also be able to detect some semantic/grammatic mistakes as well.

Even using current grammar-checking tools, you will have more troubles with Vietnamese ;) Before you discuss grammar, you must split a sentence into words (actually annotated words but that's not the point). It's already difficult to do that in Vietnamese. Now you are supposed to do that on a **misspelt** text.
Good luck :D

European languages don't have this problem, as distinct words can be easily
recognized. CJK languages do though, but I guess CJK spellchecker
status in OOo is just the same as it is for Vietnamese.

To have an idea how hard it is to split a sentence into words, let's
take a corner case: « **Ông già đi nhiều quá** ». You can understand this
sentence in a couple of ways:

  * An old man goes a long way (**Ông-già đi nhiều quá**, notice « **Ông già** » is a single word)
  * He gets very old (**Ông già đi nhiều quá**, notice « **Ông già** » is two separate words)

Now suppose « **già** » is mistakenly written as « **dà** », then pass the sentence
to a grammar checker ;)

.. _../pages/guide/spell_checker_case_studies#could_we_train_a_spellchecker:

Could we train a spellchecker?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Is it possible to train a spellchecker, as one trains a Bayesian spamfiltering program like `SpamSieve <http://c-command.com/spamsieve/>`_ on OSX? If we have a group of volunteers each building up a corpus, and training the spellchecker each time it makes a mistake, perhaps we could amass the data we need.

.. _../pages/guide/spell_checker_case_studies#this_discussion:

This discussion
^^^^^^^^^^^^^^^

You can follow this discussion on the specially-created `anoi-spell <http://lists.hanoilug.org/listinfo/spell>`_ mailing list, or on the :doc:`Translate Toolkit <https///lists.sourceforge.net/lists/listinfo/translate-devel>` mailing list.

.. _../pages/guide/spell_checker_case_studies#quechua:

Quechua
-------

.. _../pages/guide/spell_checker_case_studies#amos_batto:

Amos Batto
^^^^^^^^^^

It is interesting hearing about the difficulties of
spell checking in Vietnamese. I have also run into
problems using Hunspell to spellcheck Quechua (an
indigenous language of the Andes), but of a very
different nature.

Quechua is an agglutinative
language. Most words have 1 or 2 suffixes, but some
can have as many as 8 or 9 suffixes. Most suffixes
have to be added in a very specific order, but a few
can appear in almost any order. Needless to say, the
possible combinations of suffixes is almost infinite
and almost impossible to list in an affix file. When I
tried to write out all the possible combinations, I
got up to 500 pages of combinations and that was only
combining 1, 2, and 3 suffixes.

Hunspell is much
better than aspell and ispell because it allows an
infix and 2 levels of suffixes, but it is still
woefully inadequate for languages like Quechua.

Another problem of Hunspell is a lack of a "sounds
like" feature, as is found in  Aspell. In Quechua, K,
K', KH, Q, Q', QH are all easily confusable letters,
along with their Spanish equivalents: QU and C. In
order to properly spellcheck in Quechua a "sounds
like" function needs to be added to Hunspell. The code
for "sounds like" shouldn't be that difficult to
write, but the Hunspell code looks pretty complicated
and I haven't figured it out. 

//Note: Kevin Scannell, who was one of the developers of 
Aspell contacted me to say that he intended to add the 
Aspell "SoundsLike" function to Hunspell. I hope that he
finds the time to do this since it will help me greatly.
Kevin also noted that the metaphone function in Hunspell
could act like SoundsLike to some degree.//

If you have more interest in learning about the challenges 
of a Quechua spellchecker, see `this note <http://www.runasimipi.org/blanco-en.php?file=cartaHunspellPreguntas-en.txt>`_ I wrote to the
Hunspell developer explaining our difficulties.

.. _../pages/guide/spell_checker_case_studies#zulu:

Zulu
----

.. _../pages/guide/spell_checker_case_studies#friedel_wolff:

Friedel Wolff
^^^^^^^^^^^^^

The issue of agglutinative languages is quite interesting for me since
we are working on spellchecking in Zulu which is also of this nature.
We are starting to work now on a program to help people review word
lists and to identify word roots. This is all done under the assumption
that identifying roots is the most important part of the work in terms
of the words and word lists, and combined with proper affix rules
(developed separately), we can create a usable spell checker (for an
agglutinative language).

People interested can have a look `here <http://translate.sourceforge.net/specifications/Spelt/>`_ at our ideas for how this should
work. This is currently really meant to be a small project that can be
implemented quite quickly.

.. _../pages/guide/spell_checker_case_studies#statistical_support:

Statistical Support
-------------------

Kevin Scannell can generate word frequency lists and other useful statistics for many languages (more than 400 as of May 2008) using his web crawling software `An Crúbadán <http://borel.slu.edu/crubadan/>`_.   There's a good chance your language is already supported if it has a non-trivial presence on the web.
Contact him (kscanne at gmail dot com) if you are beginning development of a spell checker and plan on releasing it under and open source license. 

.. _../pages/guide/spell_checker_case_studies#your_language:

Your language
-------------
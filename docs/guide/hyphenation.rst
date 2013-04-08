
.. _../pages/guide/hyphenation#hyphenation:

Hyphenation
***********

.. _../pages/guide/hyphenation#resources:

Resources
=========

* A simple explanation of `TeX based hyphenation
  <http://www.tex.ac.uk/cgi-bin/texfaq2html?label=hyphen>`_ -- OpenOffice.org
  uses the same TeX files to hyphenate
* :man:`patgen` -- creates Hypenation pattern files from a set of good
  hyphenations
* Frank Liang, `Word hy-phen-a-tion by com-puter
  <http://www.tug.org/docs/liang/>`_, STAN-CS-83-977, Stanford University Ph.D.
  thesis, 1983. -- the creator of the Hyphenation system in TeX
* `OpenOffice.org hyphenation page
  <http://lingucomponent.openoffice.org/hyphenator.html>`_ -- OpenOffice.org
  use the ALTLinux hyphenator which is based on libhnj library by Raph Levien.
  It uses TeX hyphenation dictionaries with small corrections.
* `Current OpenOffice.org hyphenation dictionaries
  <http://lingucomponent.openoffice.org/hyph_dic.html>`_
* `ALTLinux standalone hyphenator
  <http://lingucomponent.openoffice.org/altlinux_Hyph.zip>`_
* Knuth's `The TeXbook
  <http://www.ctan.org/tex-archive/systems/knuth/tex/texbook.tex>`_ -- you
  can't generate this but you can read the TeX in appendix H
* This `patgen2 tutorial
  <ftp://tug.ctan.org/pub/tex-archive/info/patgen2.tutorial>`_ might be
  helpfull
* This is a well commented (in TeX) version of `patgen
  <http://www.tug.org/tex-archive/systems/knuth/unsupported/texware/patgen.web>`_
* `A very good explanation with clear examples
  <http://www.fi.muni.cz/%7Exantos/patlib/thesis/userguide-p.ps>`_ for OPatGen
  (a Unicode enabled patgen)
* `A very good set of tools <http://www.ntg.nl/spelling/hyphenation.html>`_
  written by the Dutch TeX team.  Also useful for manipulation of word lists.
* `Automatic non-standard hyphenation in OpenOffice.org
  <http://hunspell.sourceforge.net/tb87nemeth.pdf>`_ written by László Németh
  about the improved hyphenation technology in OpenOffice 2.0.2 and later.

.. _../pages/guide/hyphenation#creating_you_own_hyphenation_dictionary:

Creating you own hyphenation dictionary
=======================================

Two approaches are possible to construct your hyphenation dicionary. An
automated approach, and a manual approach. Which one is best for your needs,
will depend on the characteristics of your language, and the existing
information you have at your disposal. 

If you have a list of correctly hyphenated words that is representative of your
language, the automated approach might be best. If you don't have such a list,
or it is not high quality, or the rules of your language is very simple, the
manual approach might be best.

Take note of which programs and descriptions here refer to TeX format and
OpenOffice.org format.

.. _../pages/guide/hyphenation#patgen:

patgen
------

FIXME this is the process as I understand it now. It might be wrong!

You use patgen to create the initial hypenation file. ::

  patgen DICTIONARY PATTERNS OUTPUT TRANSLATE

Where:

* dictionary -- is the input hyphenation list
* patterns -- is the existing hyphenation pattern file
* output -- is the new hypenation pattern file
* translate -- is a configuration style file (it is explained in some places
  but not that well)

When you run the command you will be asked various questions, again not sure of
what these are about.

At the end you will have a pattern file that can be used in TeX.

.. _../pages/guide/hyphenation#by_hand:

By hand
-------
This section explains the format of the hyphanation file required by
OpenOffice.org. You might still be interested to understand how this works if
you need to fix mistakes caused by another approach. 

You need

* altlinuxHyph from http://lingucomponent.openoffice.org/hyphenator.html
* grep

Patterns are specified which describe patterns where hyphenation can occur and
where hyphenation cannot occur. The priorities of breaking or non-breaking
points are set by numbers (about 1-6). Odd numbers (1,3,5) indicate places
where hyphenation can occur. Even numbers (2,4,6) indicate places where
hyphenation are not allowed. All patterns that match a particular word are
applied to a word. Higher numbers overrule the lower numbers. The places with
odd numbers left indicate possible hyphenation points. A full stop can be used
to indicate a word boundary (either beginning or end).

Consider the word “example”. The word is prepared by putting a full stop in
front and at the back. Therefore we now have “.example.”. The hyphenation
software searches the file for patterns that match any part of the prepared
word. Lets say the following patterns match::

  x1a
  xam3
  4m1p
  1p2l2

This is how they are applied::

   . e x a m p l e .
       x1a
       x a m3
          4m1p
            1p2l2
   -----------------
   . e x1a4m3p2l2e .
        ^ - ^ - -

Now we can hyphenate at the points of the odd numbers. Note how the even
numbers overrule certain hyphenation points that otherwise might have caused
wrong hyphenation. Therefore, “ex-am-ple”. The software can now choose the
hyphenation point that results in the best layout. There will usually be
settings in the software that prohibits hyphenation in the very first and very
last characters of a word, in order to avoid having just one or two characters
left on the beginning or end of a line. (OpenOffice.org 2.0:
:menuselection:`Tools --> Options --> Language settings --> Language aids -->
Options`)

To encode exceptions, simply make sure that the pattern is surrounded by full
stops. It might be necessary to encode exceptions in cases where a word doesn’t
follow normal spelling rules, for example with brand names, person names, etc.
(.Kin1sa1s6ha.)

A confusing problem with the hyphenation patterns is the way they interact.
Consider the following hyphenation file::

  ISO8859-1
  n1t
  prin2t1able

Now consider the words “print”, “printable”, and “printer”. Run "example" from
altlinuxHyph as follows (each pair of lines contain both what was typed in, and
the output)::

  ./example printer.test /dev/stdin
  print
  print
  printable
  print-able
  printer
  printer

“Print” won’t be hyphenated, because the hyphenation point specified by the
first hyphenation pattern (“n1t”) occurs to close to the end of the word.
“printable” is hyphenated as we expect: “print-able”. If we now input
“printer”, we are surprised: it doesn’t hyphenate at all.  This happens because
the second pattern (“print2t1able”) is matched first (from the “p” up to the
“t”), but then discarded when the “e” in “printer” doesn’t match the pattern.
At that stage it doesn’t go back to consider all patterns from the second
character, but only continues from the last character that matched, “t”. To
solve this, edit the file as follows (add the last pattern)::

  ISO8859-1
  n1t
  prin2t1able
  prin1t

For the word “printer”, the second and third patterns will both match up to the
“t”, but the second pattern will not be considered. The first rule therefore
has to be “repeated” for the case where the second rule will mask it out. 

It is important to remember that the beginning of word marker (“.”) will be
handled like a normal character, and therefore the same masking problem can be
obtained.

.. _../pages/guide/hyphenation#altlinux:

ALTLinux
--------

ALTLinux make changes to the TeX hyphenation file that relate to optimisation
and performance. ::

  perl substrings.pl <tex hyphen file> <alt linux hyphen file>

Now add your languages encoding to the top of **alt linux hyphen file**.  Now
you are ready to include this in :doc:`OpenOffice.org <openoffice.org>`.

.. _../pages/guide/hyphenation#including_your_hyphenation_in_openoffice.org:

Including your hyphenation in OpenOffice.org
============================================

FIXME need to check this but this is just anecdotal based on my experience with
MySpell

Your hypenations dictionary need to be included in dictionarl.lst the format is
something like::

  HYPH xh ZA hyph_xh

Where:

* HYPH -- indicates its a hyphenation dictionary as apposed to a spelling DICTionary
* xh and ZA -- the language and country
* hyph_xh -- the name of the dictionary file without the .dic suffix

FIXME once again please check this :)


.. _../pages/guide/spell_quality.py#spell_quality.py:

spell_quality.py
****************

The spell_quality.py script can be used to calculate basic spellchecker quality metrics.

It doesn't have an installer, and depends on a working installation of Python and the `pyenchant library <http://pyenchant.sourceforge.net/>`_. Simply download `spell_quality.py <http://translate.svn.sourceforge.net/viewvc/translate/src/trunk/wordlist/spell_quality.py>`_ and run it with your python interpreter. It has only been tested with Python 2.5, but Python 2.6 should work fine. Please report on your success with Python 3.

usage:

::

    ./spell_quality.py --correct correctcorpus.txt \
       --incorrect incorrectcorpus.txt --language zu_ZA

The corpus files should include one single word per line and should be in the UTF-8 encoding. It can be prepared based on any given corpus with commands similar to

::

    tr -c 'A-Za-z' '\n' | sort  > corpus.txt

or if you only want to test unique words:

::

    tr -c 'A-Za-z' '\n' | sort | uniq > corpus.txt



.. _../pages/guide/evaluating_spellcheckers#evaluating_spell_checkers:

Evaluating spell checkers
*************************

.. _../pages/guide/evaluating_spellcheckers#metrics:

Metrics
=======

To get an idea of the quality of a spellchecker, we can use the information retrieval metrics of precision and recall.

**Precision**: is a measure of the exactness of the spellchecker's responses, it basically tells you how much you should trust the spellchecker when it tells you this word is correct.

**Recall**: is a measure of the completeness of the spellchecker, it tells you how much of the language the spellchecker covers, the lower the value the more likely it is that the spellchecker will complain about correct words.

It might also be useful to measure the same useful to measure the same metrics but for the case where the spellchecker identifies the word as incorrect instead of correct.

In that case recall is called specificity and it tells you how likely it is that the spellchecker will catch all incorrect words.

Generally speaking the spellchecker should have very high Precision and specificity to be useful.

We also calculate accuracy which is derived from both precision and recall and is a general measure of the quality of the spellchecker.

The :doc:`spell_quality.py` script in the wordlist directory of the toolkit can be used to measure precision, recall, accuracy and specificity.

.. _../pages/guide/evaluating_spellcheckers#actual_performance:

Actual performance
==================

Now these metrics can be a bit too generic, to judge whether a recall of 30% is good or bad you need to know which 30% of the language does the spellchecker cover. Or more importantly which correct words is it going to assume are incorrect.

It's ok if the spellchecker doesn't know about obscure, archaic, deeply technical or other rarely used words, but it is a very big problem if it can recognize millions of words but fails to recognize a few widely used ones.

We can manually evaluate coverage by generating :doc:`false negative frequency tables`.
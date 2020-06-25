
.. _../pages/guide/costing#budgetting_for_paid_translators:

Budgetting for Paid Translators
*******************************

Although we encourage the volunteer model there are projects that are funded
and there are projects that receive funds from time to time to do a specific
translation.  This gives a rough outline of how to cost such a translation.

.. _../pages/guide/costing#calculation:

Calculation
===========
::

  Words = untranslated msgid words + fuzzy msgid words
  Cost = Words to translate * Rate per word
  Days = Words to translate / Words per days

.. _../pages/guide/costing#rule_of_thumb:

Rule of thumb
-------------
::

  Weeks = Strings to translate / 2000
  Days = Strings to translate / 400 or 500
    ( Use 400 for large project 500 for a small project. This then evens out
    lost days or slow progress due to complicated section.)

  Strings = Words / 3.5
    (This varies but is helpful)

.. _../pages/guide/costing#calculating_costs:

Calculating Costs
=================

FIXME convert these numbers to dollars or other 'international' currency

Translators will quote based on the number of source words::

  R400 / 1000
  R40 / 100

  which calculates to R0.40 per words

Note: these are just for illustration purposes

Using :ref:`toolkit:pocount` determine the number of source words.  So this is the number of
words in untranslated strings plus the number of words in fuzzy strings. ::

  Words = untranslated + fuzzy
  Words = 40 000 + 5 000

Note: make sure you count the msgid or source words not the translations.

You final costing would then be::

  Cost = 45 000 * 0.4
       = R18 000

.. _../pages/guide/costing#calculating_time:

Calculating Time
================

Assuming that you need to translate 45 000 words do the following.  Either, 

* Find out how many words the translator can translate per day ::

    1300 words per day

    Days = 45 000 / 1300
         = 35 days
         = 7 weeks

* Convert to the rule of thumb guides above ::

    Strings = 45 000 / 3.5
            = 12 857 
           +- 13 000

    Days = 13 000 / 400
         = 33

    Weeks = 13 000 / 2000
          = 6.5 weeks

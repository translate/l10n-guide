
.. _../pages/guide/short_strings_first#one,_two,_short,_long:

One, two, short, long
*********************

How do you translate most quickly for the biggest impact?  If you look at a GUI
application you will notice that most strings are relatively short.  Menu items
are between one and three words long.  Error messages are more descriptive at
perhaps 5-10 words.  So in general the items that users see in normal operation
are relatively short.

Therefore, if you can initially focus your translation on the short strings
then you can make a quick visual impact.  Afterwards you can follow up with
longer and longer strings until the application is fully translated.

.. _../pages/guide/short_strings_first#shortcommings:

Shortcommings
=============

The problem with this method is that you lose context in that you are not sure
in what situation the single word string was used.  Did "Manual" mean
"configure manually" or the "operations manual".

.. _../pages/guide/short_strings_first#using_pogrep_to_select_messages:

Using pogrep to select messages
===============================

Use :ref:`toolkit:pogrep` to extract messages that are a certain number of
words long::

  pogrep --search=msgid -e '^\w+(\s+\w+){0,3}$' -i templates -o short-words

This will extract between 1 and 4 words from *templates* and place them in
*short-words*.  Once these strings have been translated you would use
:ref:`toolkit:pomerge` to combine them with the full PO file.

Use the following regex's to extract specific word counts:

=======  ====================================
 Words    Regex                                
=======  ====================================
 1        ``"^\w+$"``
 2        ``"^\w+\s+\w+$"``
 3        ``"^\w+(\s+\w+){2}$"``
 4        ``"^\w+(\s+\w+){4}$"``
 1-4      ``"^\w+(\s+\w+){0,4}$"``
=======  ====================================

Another way might be to look at all messages shorter than a certain number of
characters::

  pogrep --search=msgid -e '^.*{,30}$' -i complete -o short

This will extract messages that are up to 30 charactes long, but not longer
than that from *complete* and place them in *short*.  Once these strings have
been translated you would use :ref:`toolkit:pomerge` to combine them with the
complete PO file(s). This way it is sometimes possible to translate more than
60% of the messages by translating less than 40% of the words. Use
:ref:`toolkit:pocount` to see how much work has been isolated by pogrep - this
will help you to plan your time.

.. _../pages/guide/short_strings_first#example_of_the_potential_impact:

Example of the potential impact
===============================

As an example Mozilla 1.7.3 contains 32217 words for translation.  However,
breaking it down into the number of words in short strings you get the
following:

========  =============
 Words     Word Count    
========  =============
 1           1853        
 2           1774        
 3           1371        
 4            796        
========  =============

Or in total 5794 words, which is 17% of the original total.

False Nagtaive Frequency Tables
===============================

Frequency tables of words deemed incorrect by a spellchecker can be generated with a simple command line ::

    hunspell -d zu_ZA -l corpus.txt | sort | uniq -dc | sort -nr | head


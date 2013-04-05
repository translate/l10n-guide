Although PO files will show us which strings have changed, sometimes the string
can be very long and complex, such as a help screen. Also, HTML and text files
do not show changes in the organized, summary way gettext PO files do in our
translation editors.

.. _../pages/guide/comparingfiles#how_to_find_specific_changes:

How to find specific changes
============================

Text editors, and some translation editors, will run a "diff" routine which
compares two directories, and shows you which files have changes. That's
certainly a good start.

But how do we find specific changes? Ordinarily, we can run "diff", in the
terminal, or in our editor::

    diff -u old_file new_file

and the output will show in our terminal. To output the information to a file::

    diff -u old_file new_file >output_file.diff

But this will only show what the editor regards as line-by-line changes, which
in a PO file are often whole sections. 

You can hard-wrap the older file (but not the newer file) before running diff,
and that will actually give you a line-by-line comparison (you can remove the
line-breaks from the older file afterwards, if necessary). That's a definite
improvement.

But we can do even better.

If you run **wdiff** instead::

    wdiff -u old_file new_file >output_file.diff

you get output that looks like this::

    Test of a very long line where something [-has changed-] {+did change+} and
    you don't know what it {+really+} was, why?

In other words, you get a **word-by-word comparison**. 

You can clearly see what has changed: the {braces} show additions, and the
[brackets] show deletions. 

If you use the 'less' program in the terminal::

    wdiff -l  testA testB |less

you will also see bold text and underscored text highlighting the differences.

You can find `more information on wdiff
<http://wdiff.progiciels-bpi.ca/index.html>`_.

.. _../pages/guide/comparingfiles#gui_software:

GUI software
============

.. _../pages/guide/comparingfiles#winmerge_ms_windows:

Winmerge (MS Windows)
---------------------

http://winmerge.org/

To compare two files, drag and drop one of them onto the Winmerge icon, and
Winmerge will prompt you for the other file.

You can use Winmerge in combination with Tortoise SVN.  In the SVN tree,
right-click the folder with changes in it, and select Tortoise -> Check for
Modifications.  In the Modifications dialog, where modified files are
displayed, simply double-click a file to have it opened in Winmerge.

You can make changes to a file in Winmerge.

Winmerge requires a BOM to recognise a Unicode file, so if your Unicode files
don't have BOMs (which is the case with Toolkit produced files), you have to
tell Winmerge to "fall back" to Unicode when opening a "non-Unicode" file (no,
I'm not joking).  Go Edit -> Options -> Codepage -> Custom Codepage and type in
65001 (which is the codepage for UTF8).

Winmerge can also be used to compare trees and directories.


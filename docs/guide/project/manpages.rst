
.. _../pages/guide/project/manpages#translating_manpages:

Translating Manpages
********************

Manpages, or manual pages, displayed in your terminal by the **man** program,
are an important resource for computer users. They are distributed with the
system, and they contain a great deal of immediately-accessible and specific
information on how to use software.

``man man`` will tell you all about the **man** program, but briefly: you type
``man <command>`` (e.g. ``man find``) to view the manual page about that
command or program. Use the **spacebar** to page down, and type **q** to quit
(this clears the manpage completely and returns you to the point where you
called that page).

Manpages have been translated, and distributed separately by language groups,
or made available at certain sites. The aim of a small project liaising between
`GNU <http://gnu.org/>`_ and `The Translation Project
<http://translationproject.org/html/welcome.html>`_ is to integrate the
translation process with the central manpage distribution process. Manpages
will be translated, just like applications, then distributed with the original
package, just like applications.

The manpage format, **(g)roff** or similar, is not easy to translate. However,
the `po4a <http://po4a.alioth.debian.org/>`_ conversion filters remove this
problem completely, by giving us the capacity to convert manpages to our
familiar PO format. (See more information on conversion filters you can use in
:doc:`Non-PO formats </guide/nonpo>`.)

`Pootle <http://pootle.translatehouse.org>`_ has integrated po4a and the
Translate Toolkit filters, which enabled me recently to upload a trial manpage
to Pootle, have it automatically converted there to PO format, translate it
easily, then have it converted back to g(roff). This simplified the translation
process considerably.

:doc:`Debian </guide/debian>` has just made a package of manpages available in
PO format, again using po4a. This is a big step forward, and will result in
many more, and more current, manpage translations.

I found, once I'd translated my pilot manpage (find1), that I had to do some
configuration before my UTF-8 (Vietnamese) manpage would display correctly in
my terminal.  

XXX
===

.. _../pages/guide/project/manpages#manpage_process:

Manpage process
---------------

* Get translated manpage(s), place in MANPATH

  * If you're unsure what your MANPATH is, type ``echo $MANPATH`` — this shows
    all the places the **man** program will look for manpages.
  * Create a folder/directory named for your ISO language code (e.g. for
    Vietnamese, I create a folder called **vi** within my MANPATH : I placed it
    in ``</usr/share/man>``.
  * Create a sub-folder (``manX``) for each number shown after a manpage name.
    E.g. because I have the **find1** manpage, I need to create a **man1**
    sub-directory, which for me was ``</usr/share/man/vi/man1>``. Place each
    manpage in the appropriately-numbered sub-directory.

* Install the latest version of `groff
  <http://pdb.finkproject.org/pdb/package.php/groff>`_, if you don't have it.
  You can get it via **fink**, or your usual package manager. 
* Install `groff-utf8 <http://www.haible.de/bruno/packages-groff-utf8.html>`_.
  Bruno Haible is currently working on a full release of groff, which will
  support UTF-8; meanwhile, he has created this patch for us. Thanks, Bruno!
  :-)
* Set your **locale**, if it has not yet been set. 

  * Your locale tells your computer what language you prefer to use, plus some
    other useful information related to your language choice.   
  * You type your locale into your shell profile. (FIXME Does this differ from
    one shell to another?) 
  * For **bash**, find and edit your ``<~/.bash_profile>`` or ``<~/.profile>``
    file, where ~ is your username, your user directory. You can edit this type
    of file in your text editor. I used `BBEdit
    <http://www.barebones.com/index.html>`_ for Mac OSX.
  * Type ``export LC_ALL=ll_LL.UTF-8`` where ``ll_LL`` is your language code
    (and possibly country), e.g. for me it was ``export LC_ALL=vi_VI.UTF-8``.
  * Save the file, don't change the name or location.

* Find the file </etc/manpath.config> or <usr/share/misc/man.conf>. If you
  don't have either of these, it will be something similar. **man** has to get
  its config. info somewhere!
* Copy this file to <~/.man.conf>. (This leaves your original man config
  untouched, if you want to return to it later, or if the machine has multiple
  users.)
* In that file, find the **NROFF** line, something like this::

    ``NROFF		/usr/bin/groff -Wall -mtty-char -Tascii -mandoc -c``

  and edit it to::

    ``NROFF		/usr/bin/groff-utf8 -Tutf8 -mandoc -R``

  * Make sure you have a terminal (monospaced) font set which supports your
    language *and supports UTF-8*.
  * In your terminal, call your translated manpage!

    * All I had to do was type ``man find``. Because I had set my system to
      call documents and software in my language, and because this manpage was
      available, translated, in the directory for my language code, **man**
      automatically showed that page. It displayed beautifully (or as
      beautifully as my language can in a monospaced font ;-) ).

Please add any information specific to your system or language. This
information will help ensure an effective manpage translation and distribution
process. :-)

Clytie

<clytie@riverland.net.au>

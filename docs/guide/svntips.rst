
.. _../pages/guide/svntips#svn_tips_for_translators:

SVN Tips for Translators
************************

SVN is one of the most useful tools available for keeping up-to-date with your
PO files. It's not difficult to use, and once you get used to it, you'll wonder
how you ever got on without it. ;)

XXX
===

.. _../pages/guide/svntips#why_use_source_control:

Why use Source Control?
-----------------------

Most projects use some form of source control to manage their files. Source
control makes it possible for many people to work on the same file, without
confusion or lost data. Anyone who wants to change that file simply gets the
latest copy from the **repository** (location of the shared files), adds his or
her improvements, then **commits** (writes) the file back to the
**repository**. The source control software makes sure that each person's
additions are integrated in the main file. 

For example, if you add a section on Kumquats to the document on citrus fruits,
then commit it, your colleague will see it when she **checks out** (downloads
from the repository) the latest copy, to add her views on Grapefruit (good for
you but sour comfort in the mornings). Once her grapefruit information is
committed, another colleague may add forceful comments on the delightful taste
of grapefruit, and commit them. The original non-lover of grapefruit can
**check out** the latest file and add aspersions on her colleague's tastebuds,
which were shot off in the war. All nice, clean fun, while the SVN server
collects all the information and maintains the current file.

How does this affect us translators? **Source control means we have access to
the latest .po file at any time.**

**Note**: a GUI front-end for SVN like `svnX
<http://www.lachoseinteractive.net/en/community/subversion/svnx/features/>`_
makes using SVN even easier! Your `file-browser <http://www.cocoatech.com/>`_
might also have embedded SVN functions.//

.. _../pages/guide/svntips#how_do_i_get_the_files:

How do I get the files?
-----------------------

All you need to get your latest PO file, is the source control **address** of
its directory on the server. In the case of SVN, the address will either look
like svn://svn.servername.org/path/to/directory/po or
https://svn.servername.org/path/to/directory/po.

In other words, SVN files, just like webpages, have their own address. Like
many websites, they ask you to login. If you want to be able to **commit**
files (add them to the **repository**) you need permission (**write access**),
just as you would need permission to add or change files on a website. This
permission system protects our hard work from being altered or damaged by
unauthorized people.

For example, `Sourceforge <http://sourceforge.net>`_ uses the
https://svn.servername.org method, which requires you to input your Sourceforge
account username and password. You would also need permission from the
developers of your Sourceforge project, to **commit** files. Many
svn://svn.servername.org servers use `SSH
<http://www.csua.berkeley.edu/ssh-howto.html>`_ to identify you when you
connect. A server may be willing to let you **checkout** (download) files
anonymously, but it certainly doesn't want to accept files from a stranger.
Don't be a stranger: setup your SVN access. :)

To commit your files, if you don't have write access, you will be asked to
upload them using a tracker, or to email them to the developers, who will later
commit your files to the repository.

.. _../pages/guide/svntips#what_are_the_key_points:

What are the key points?
------------------------

- **Checkout** your **working copy** (your own local copy of the files on the
  server). This might be the whole **source tree**, containing all the files
  making up the project, or it might be part of that tree, only one **branch**,
  or only the ``/po`` directory containing your PO file. Checking out
  directories (you can't checkout single files) is as simple as **svn co
  svn_address**. You can use the whole word **checkout** or simply **co** for
  short. Type the command when you are in the directory where you want the
  server files to arrive.
- Notice an **.svn** directory that has also arrived from the server. This
  little folder is the key to source control. It keeps notes on where your
  files belong on the server, and what **revision** (version) of the files you
  have. Everytime you use SVN in that directory, that little **.svn** folder
  updates its information. It knows if your files come from a **branch**
  (separate version of the program), it knows exactly when you last updated or
  committed them. So anything you do outside your **working copy** doesn't
  count: you must use SVN within it.
- Always **update** your **working copy** before making any changes. Updating
  asks the server for the latest **revision** of the file. If you run **svn
  update** in your ``/po`` directory, the server will update every file in it
  to the latest **revision**. Your translation editor or text editor may also
  be able to update individual translation files via SVN. Either way, you must
  update your ``xx.po`` from inside its ``/po`` directory (or higher((Inside
  the **working copy**, SVN commands have a hierarchical effect: running **svn
  update** in any directory which contains ``/po`` will also update ``/po``,
  and any other contained directories. So, if ``/po`` is on the path
  ``/trunk/messages/po``, updating the ``messages`` directory will also update
  ``/po`` and any other directories it contains, and updating ``trunk`` will
  update the whole working copy.))). Even if you have downloaded a new copy of
  the file from the Web, or have been sent a new copy by email, you must update
  your working copy of ``xx.po`` before making any changes. Otherwise the
  server won't know that you have the latest file.

.. _../pages/guide/svntips#problem-solving:

Problem-solving
---------------

.. _../pages/guide/svntips#problem_1:

Problem 1
^^^^^^^^^

Minh receives the latest ``vi.po`` file for Program X by email, or downloads it
from the Web. He saves it to his ``/po`` directory. He updates his translation.
Then he tries to commit the updated PO file. The SVN server refuses it, says it
is out-of-date! Why? It's the latest file.

.. _../pages/guide/svntips#solution:

Solution
^^^^^^^^

The file may be the latest, but the SVN server doesn't know that. As far as it
knows, Minh last updated his ``vi.po`` file via SVN some time ago. He certainly
hasn't updated his ``/po`` directory from the server. So the server refuses any
files from what it sees as an old working copy. Imagine this conversation:

**vi.po:** Let me in!

**Program X svn server:** Who are you?

**vi.po:** I'm, um, vi.po.

**Program X svn server:** So you say. Are you the latest vi.po? I don't want
you overwriting a newer file. I have to check up on you. Wait over there, and
don't interrupt.

***Program X svn server** queries the .svn folder in the same directory with
vi.po*

**Program X svn server:** Do you know this vi.po?

**.svn folder:** There's a vi.po here with me.

**Program X svn server:** How recent is it?

**.svn folder:** This directory hasn't been updated from the server for a couple of days.

**Program X svn server:** Really? thanks.

***Program X svn server** now has the information it needs.*

**Program X svn server:** Hey, vi.po!

**vi.po:** Yes? Can I come in now?

**Program X svn server:** Get lost. You're an old version.

**vi.po:** But I'm not! I'm the latest version, all updated!

**Program X svn server:** Not according to your .svn directory. End of
conversation. Stop wasting my time.

.. _../pages/guide/svntips#doing_it_right:

Doing it right
^^^^^^^^^^^^^^

Minh receives an updated ``vi.po`` file via email, or downloads it from the
Web. He saves it somewhere else on his disk (*not* in his working copy ``/po``
directory), then updates his translation. When he's ready to commit the file,
he runs **svn update** in the ``/po`` directory where the old file is. *Then*,
if he is sure his edited file is the latest one, he saves it on top of the
updated one from the server. He runs **svn commit** inside the ``/po``
directory.

.. _../pages/guide/svntips#problem_2:

Problem 2
^^^^^^^^^

Sonja wants to know if her ``ro.po`` file for Program Y has been updated or
not. She looks at the ``ro.po`` file in her working copy ``/po`` directory. She
updated it yesterday, so it's pretty current, she thinks. It has some
untranslated and fuzzy strings, so she updates the translation, then commits
the file. The SVN server rejects the file, saying it is out-of-date. Why? She
updated it yesterday!

.. _../pages/guide/svntips#solution:

Solution
^^^^^^^^

Another member of Sonja's translation team has fixed some typos in the existing
translations. He committed his changes this morning. So yesterday's file is no
longer the current copy of the ``ro.po`` file.

.. _../pages/guide/svntips#doing_it_right:

Doing it right
^^^^^^^^^^^^^^

Sonja wants to know if her ``ro.po`` file for Program Y has been updated or
not. She updated it yesterday, but who knows what has happened on the server
since then? She runs **svn update** in her ``/po`` directory. She now has the
current copy of ``ro.po``, so she can update her translation, then commit it.

.. _../pages/guide/svntips#problem_3:

Problem 3
^^^^^^^^^

Jean-Christophe wants to know if his ``fr.po`` file for Program Z has been
updated or not. He updated it yesterday, and in our example, he is
unfortunately the only member of his translation team, so there aren't any
other translators! Nobody else would change the file. So he goes ahead and
updates the translation, then tries to commit the file. The SVN server rejects
the file, saying it is out-of-date. Why? No other translator can have changed
the file!

.. _../pages/guide/svntips#solution:

Solution
^^^^^^^^

The developer added a couple of new strings, and committed them this morning.
She then updated all the .po files. Jean-Christophe's version of the file is no
longer the latest one. The moral of this story being: you can never assume
you're the only person who would change a file, unless you're the only person
with write access, and even then, you might have setup some regular scripts
which update the files! So don't assume: **svn update**.

.. _../pages/guide/svntips#doing_it_right:

Doing it right
^^^^^^^^^^^^^^

Jean-Christophe wants to know if his ``fr.po`` file for Program Z has been
updated or not. He updated it yesterday, but anything could have happened since
then. He runs **svn update** in the ``/po`` directory. He now has the current
copy of ``fr.po``, so he can update his translation, then commit it.

.. _../pages/guide/svntips#conflicts:

Conflicts
^^^^^^^^^

There is still a small probability that someone else might change the file on
the server *while you're editing the file*. It's unusual, but it does happen,
either by coincidence, or in very busy projects/teams. If you've svn-updated
the file before working on the translation, and your commit is rejected as
being out-of-date, you can do one of two things.

.. _../pages/guide/svntips#solution:

Solution
^^^^^^^^

- Run **svn update** in the ``/po`` directory. This will create **conflicts**
  between the newer file on the server and your file. Extra files called
  ``xx.po``.mine and ``xx.po``.zzzz (where zzzz is the revision number of the
  current file on the server) and possible another dot file at the top, will be
  created in the ``/po`` directory. The **conflicts** will be shown between
  markers (>>>>> and <<<<<) in your ``xx.po`` file, with both copies of each
  changed line or string shown: marked **mine** and **zzzz**. You can choose
  which one to keep in each case. Make sure you have removed all signs of
  **conflict**, including the extra files, before trying to commit again. This
  is a messy process, and should be avoided if possible.
- If you have a backup copy of your completed translation (and you should
  *always* keep a backup copy of your work, asking your translation editor to
  create one automatically, or creating one in another directory before trying
  to commit), delete your ``xx.po`` file in your ``/po`` directory. Run **svn
  update** in the ``/po`` directory. The server will **update** the directory
  to the current revision by making sure you have *all* the latest files,
  including a brand-new, shiny copy of  ``xx.po``. (It will replace any missing
  files.) Now you can save your backup copy over the new ``xx.po``, or update
  your translation in that file, whichever works best for you at the time. Then
  commit! This method is much safer, since it avoids the messy **conflicts**.
  When you get into a mess with your working copy, you can always delete your
  own files and **update** them from the server. **svn update** will always
  **checkout** the current copy of that directory for you.

.. _../pages/guide/svntips#summary:

Summary
-------

So, basically you can **checkout** your **working copy** (at least the
directory containing your file), which gives you your ``xx.po`` file and the
.svn folder which keeps track of its status. Anytime you want to know if the
file has changed, run **svn update** in that directory. Then open ``xx.po`` in
your editor, add new translations or fix older ones, save it, and **commit**
it! Don't forget to edit the **ChangeLog** [#f1]_ if there is one.

.. rubric:: Footnote

.. [#f1] A text file, usually in the same directory, which contains entries of
   the format ``Date Filename What changed Name and Email address``.

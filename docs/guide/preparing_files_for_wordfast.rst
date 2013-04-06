

.. _../pages/guide/preparing_files_for_wordfast#preparing_files_for_wordfast:

Preparing files for Wordfast
****************************

It is possible to translate any plaintext l10n file in Wordfast (or Trados, if
you know what you're doing).  Here's how:

#. Open the file in MS Word, and save as DOC format
#. Prepare it
#. Translate it, check it, proofread it, review it, etc.
#. Clean it
#. Save it as a plaintext file again

If you're a Wordfast user, you will already know how to do steps 3 and 4.
Translating a l10n file in Wordfast is no different from translating any other
file, except that Wordfast will automatically prevent you from translating
certain stuff, and certain pieces of text have to inserted using Wordfast's
"placeable" feature (which is quite simple, actually, and is described in the
Wordfast user manual)

.. _../pages/guide/preparing_files_for_wordfast#how_to_open_a_l10n_file_in_ms_word:

How to open a l10n file in MS Word
==================================

When opening a text file in MS Word, MS Word will try to interpret the file.
This is not good, for our purposes -- we want MS Word to treat plain text as
plain text.  If you open an XLIFF file in MS Word, MS Word will recognise it as
an XML file, and will parse it as an XML file, rendering the file useful for a
passive user, but useless for a translator.

To prevent MS Word from parsing the file, do the following (MS Word 2000
instructions):

#. Open a blank document in MS Word
#. Go to Tools -> Options -> General
#. Select Confirm conversion at open
#. Click OK, etc
#. Close the blank document

MS Word doesn't seem to remember this setting, so you have to check that it is
enabled everytime you open a l10n file.

Normally there are many ways to open a document in MS Word, eg drag-and-drop,
Ctrl+O, File->Open, and double-clicking.  For MS Word to respect the setting
mentioned above, the l10n file has to be opend using the File -> Open method.

Usually, when opening a l10n file, MS Word will ask you to confirm the type of
file.  Do not choose "HTML", for example.  Choose "Encoded Text", and when
prompted for the encoding, select the encoding applicable to the file.  Do not
choose the option named "Unicode" -- be more specific than that.  If your file
is in UTF-8, choose UTF-8 as the file open type.

Once the file is open in MS Word, save it as a DOC file by pressing F12 and
selecting the DOC option.

At the end of the translation process, if you're certain that no hidden codes
are left in the file, you can save it as plain text again, by pressing F12 and
selecting "Encoded Text" as the file save type, and choosing the correct
encoding (again, do not choose simply "Unicode" but be more specific).  MS Word
might complain that you will loose formatting, but hey, that's exactly what you
want.

.. _../pages/guide/preparing_files_for_wordfast#how_wordfast_knows_which_text_is_which:

How Wordfast knows which text is which
======================================

To understand how Wordfast knows which text should be translated and which
shouldn't, one has to understand the concept of styles.

.. _../pages/guide/preparing_files_for_wordfast#styles_in_word_processing:

Styles in word processing
-------------------------

A word processor like MS Word (and OpenOffice.org) uses a concept called
"styles" to simplify document formatting, although very few people use it.  You
can apply a style to any piece of text, and that text will look and act
according to how the style defined.

You can create a style named "text123" and define it as "red, bold, Times New
Roman".  If you then select any text and choose the style "text123", the text
will become red, bold and Times New Roman.  In addition, the text will carry
the hidden label "text123".

Once text is marked with a certain style name, you can do all sorts of things
with it.  You can tell MS Word to delete all "text123" text, and it will delete
only the text marked in that style, even if there are other pieces of text that
look exactly the same (red, bold, Times New Roman).  You can also change the
style's definition to, say, "red, italics, Times New Roman", and all text
marked in the "text123" style will automatically become italic and non-bold.

For Wordfast, what a style looks like, is irrelevant, but the name of the style
is important.  Wordfast specifically looks for two styles, called
tw4winExternal and tw4winInternal.  The former is usually grey, the latter is
usually red.  

.. _../pages/guide/preparing_files_for_wordfast#how_to_create_wordfast_styles_the_easy_way:

How to create Wordfast styles (the easy way)
--------------------------------------------

The easiest way to create Wordfast styles, is to open a document that has
Wordfast styles in it, and then add those styles to your computer's normal.dot
generic template.  If you do this, your MS Word's Wordfast styles will look
like those of everyone else in the world (grey or red, hidden, Courier New,
etc).

Here's how:

#. Open the document that contains Wordfast styles
#. In MS Word, go Format -> Style, and click "Organizer"
#. In the organiser you'll see two documents open, namely the normal.dot and
   your current document.  Simply select the tw4win styles in the current
   document, and click "Copy" to copy them to the normal.dot.
#. Close both documents in the organiser, and click OK etc
#. Close MS Word, and start MS Word again.  See if the tw4win styles are now
   present in the styles dropdown list (usually upper left corner).

You can download such a document :doc:`here <guide:tw4winstyles.doc>`.

.. _../pages/guide/preparing_files_for_wordfast#how_to_create_wordfast_styles_easy_way,_not_ideal_though:

How to create Wordfast styles (easy way, not ideal though)
----------------------------------------------------------

You can create the requires styles in MS Word yourself, manually, but you may
find that the styles do not behave exactly the way that standard Wordfast
styles behave.  For example, if you forget to specify "No Proofing" as an
attribute, you may find that MS Word tries to spellcheck the raw l10n code.

To do this manually, you need to know what the exact style names are, because
really that's all Wordfast really cares about.  Here's how:

#. Open a blank document in MS Word, or open any other document in MS Word
#. In MS Word, go Format -> Style, and click "New"
#. Name the style tw4winExternal, and make it a "Character" style
#. Click the Format button, and select various pieces of formatting
#. Click OK, etc.

The style is now part of the current document.  To have the style available for
other documents, you should add it to the normal.dot template, described above
in "the easy way".  You may also create the style very time you open a new l10n
file, if you enjoy doing that.

We suggest the following formatting for the tw4win styles:

.. _../pages/guide/preparing_files_for_wordfast#tw4winexternal:

tw4winExternal
^^^^^^^^^^^^^^

* Font: Courier New, Regular, 12, Grey
* Language: No Proofing

.. _../pages/guide/preparing_files_for_wordfast#tw4wininternal:

tw4winInternal
^^^^^^^^^^^^^^

* Font: Courier New, Regular, 12, Red
* Language: No Proofing

.. _../pages/guide/preparing_files_for_wordfast#how_to_create_wordfast_styles_if_you_can_install_external_macros:

How to create Wordfast styles (if you can install external macros)
------------------------------------------------------------------

If you know how to install external macros (i.e. if you know where you should
copy a file in MS Windows' hidden folder structure), you can install AndoTools
(`here <http://atools.dotsrc.org/>`_) into MS Word, which has a function to
insert all tw4win styles into any document easily.  Once you've installed
AndoTools, in MS Word go Ando -> Documenet Operations -> Fonts and Language.
Click "Add tw4win styles" to add them to the current document.

.. _../pages/guide/preparing_files_for_wordfast#how_to_prepare_a_l10n_file_for_wordfast:

How to prepare a l10n file for Wordfast
=======================================

The concept of preparing a l10n file for Wordfast, is actually quite simple.
All you need to do, is to mark text that shouldn't be translated, as
tw4winExternal, and possibly any text that may be moved around, as
tw4winInternal.  What's more, the tw4winInternal is really only for advanced,
complex stuff like certain types of XML.  And even if a document can use
tw4winInternal, not having it will not make a difference as long as the
translator knows which pieces of text he should and shouldn't change.

For example, in the following line::

| The <bold>quick</bold> brown fox... |

the translator should know that <bold> and </bold> should not be translated,
but kept in "English".  These two pieces of text can be marked as
tw4winInternal, to help a translator copy them easier, but it isn't absolutely
necessary.

Marking tw4winInternal is a lot more work than marking tw4winExternal, so don't
bother, to begin with.

.. _../pages/guide/preparing_files_for_wordfast#preparing_a_file_manually_the_hard_way:

Preparing a file manually (the hard way)
----------------------------------------

I'm going to show how to prepare a file the hard way because it offers a useful
introduction to MS Word's advanced find/replace functions.  MS Word can do
limited regular expressions, with certain types of backreferences, which can be
quite useful.

What we're going to do, is to mark a document with tw4winExternal.  It is
assumed that either normal.dot or the document will itself have a style called
tw4winExternal already defined.  The easiest document to practice on, is a
Mozilla DTD file.  You can find it :doc:`here <guide:about.zip>` (zipped,
called about.dtd).  Open the file about.dtd in MS Word as describe above.  The
encoding is UTF-8.

The file looks like this:

.. code-block:: dtd

  <!ENTITY about "About">
  <!ENTITY version "Version:">
  <!ENTITY createdBy "Created By:">
  <!ENTITY homepage "Home Page:">

The stuff that needs translating, is between quotes.  The quotes themselves
should not be translated -- they do not form part of the "translatable" text.
Therefore, we must mark everything from ``<! ENTITY`` to ``"`` as
tw4winExternal, and everything that is ``">`` should also be marked as
tw4winExternal.

Here's how we do it:

- In MS Word, press Ctrl+H (the find/replace box).  Click "More" to open
  advanced features.
- Placing your cursor in the Find box, type ``(\<\!ENTITY)(*)(\")``.
- Place your cursor in the Replace box, and type ``\1\2\3``.
- Make sure your cursor is still in the Replace box, then click Format ->
  Styles, and select tw4winExternal from the list
- Select "Use Wildcards", and click "Replace all"
- Then, place your cursor in the Find box, and type ``">``.
- In the Replace box, remove everything (it must be empty).  Check that the
  style at the Replace box is tw4winExternal (if not, add it)
- Deselect "Use Wildcards", and click "Replace all"

The result should look like :doc:`this <guide:about.doc>` or like this:

.. image:: /_static/about_dtd_external.jpg

This DOC file can now be sent to a Wordfast user, who can translate it without
having to worry about which texts he should touch and which not, because
Wordfast will only prompt him to translate the black text.

.. _../pages/guide/preparing_files_for_wordfast#preparing_a_file_manually_the_easy_way:

Preparing a file manually (the easy way)
----------------------------------------

The DTD file above had a very simple structure, and it was simple to tag using
find/replace.  However, some formats are more complex, requiring many, many
steps of finding and replacing.  Luckily, MS Word allows us to record a number
of steps and save it as a macro.  The ideal would therefore be to create a
macro for each type of l10n file, and simply use the macro.

In MS Word, a macro can be embedded in a document so that it can be transported
and included into another document (or ideally in the project manager's
normal.dot template).

.. _../pages/guide/preparing_files_for_wordfast#adding_a_macro_by_pasting_it:

Adding a macro by pasting it
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Let's add the following macro to MS Word's normal.dot.

.. code-block:: vb.net

      Selection.HomeKey Unit:=wdStory
      Selection.Find.ClearFormatting
      Selection.Find.Replacement.ClearFormatting
      With Selection.Find
          .Text = ""
          .Replacement.Text = ""
          .Forward = True
          .Wrap = wdFindContinue
          .Format = False
          .MatchCase = False
          .MatchWholeWord = False
          .MatchWildcards = False
          .MatchSoundsLike = False
          .MatchAllWordForms = False
      End With
      Selection.Find.ClearFormatting
      Selection.Find.Replacement.ClearFormatting
      Selection.Find.Replacement.Style = ActiveDocument.Styles("tw4winExternal")
      With Selection.Find
          .Text = "(\<\!ENTITY)(*)(\"")"
          .Replacement.Text = "\1\2\3"
          .Forward = True
          .Wrap = wdFindContinue
          .Format = True
          .MatchCase = False
          .MatchWholeWord = False
          .MatchAllWordForms = False
          .MatchSoundsLike = False
          .MatchWildcards = True
      End With
      Selection.Find.Execute Replace:=wdReplaceAll
      Selection.Find.ClearFormatting
      Selection.Find.Replacement.ClearFormatting
      Selection.Find.Replacement.Style = ActiveDocument.Styles("tw4winExternal")
      With Selection.Find
          .Text = """>"
          .Replacement.Text = ""
          .Forward = True
          .Wrap = wdFindContinue
          .Format = True
          .MatchCase = False
          .MatchWholeWord = False
          .MatchWildcards = False
          .MatchSoundsLike = False
          .MatchAllWordForms = False
      End With
      Selection.Find.Execute Replace:=wdReplaceAll

This macro was recorded, and I'm sure any Visual Basic programmer could trim it
down to less lines.

To add the above macro, do the following:

- Select and copy the macro (copy to clipboard, Ctrl+C)
- Open a blank document in MS Word.
- In MS Word, go Tools -> Macro -> Macros.
- Type in the macro name, say, "apple" (use a name at the beginning of the
  alphabet, to find it easily).
- Click "Create".
- Place your cursor in the line above "EndSub" (by default your cursor will be
  there).
- Paste the above macro at that point.
- Press Ctrl+S to save, and exit the macro writer

The macro is now added to normal.dot, and can be used for any document that is
opened in MS Word.  Incidently, the above macro does exactly what we did in the
advanced find/replace operation above.

.. _../pages/guide/preparing_files_for_wordfast#adding_a_macro_from_an_existing_document:

Adding a macro from an existing document
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Adding a macro to normal.dot from an existing document is similar to what we
did in the "easy way" for adding styles.  I assume you have a document with a
macro embedded in it.  I've embedded the above macro for you, in a document
:doc:`here <guide:with_apple.doc>`.

To add the macro to normal.dot, here's how:

- Open a blank document in MS Word.
- In MS Word, go Tools -> Macro -> Macros.
- Click "Organizer".  It should show you the macros in with_apple.doc and
  normal.dot.
- Select "apple" and click Copy to copy to normal.dot.
- Close both files, and click OK etc.

And that's it.  Now a macro called apple.apple is part of normal.dot, and can
be used on any document you open in MS Word.

.. _../pages/guide/preparing_files_for_wordfast#how_to_execute_a_macro_on_a_document:

How to execute a macro on a document
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When running the macros described above, it is assumed that you have
tw4winExternal as a style in normal.dot, or in the document that you're about
to tag.  What we're going to do, is to run the macro apple or apple.apple,
which will perform the find/replace operation mentioned previously.  This will
mark the necessary text as "untranslatable", so that Wordfast will ignore it.

- Open the l10n file in MS Word (described above)
- In MS Word, go Tools -> Macro -> Macros.
- Select the macro apple or apple.apple in the list, and click "Run" (if you
  can't see the macro, it is either not in the normal.dot, or the normal.dot is
  not selected in the dropdown list).
- Click OK etc.

If everything went well, your document should now be tagged, as per the images
above.

(next write a short intro, plus upload a number of macros for XLIFF, TMX, PO,
etc.

.. _../pages/guide/preparing_files_for_wordfast#another_way...:

Another way...
--------------

Some of what is written here, is re-inventing the wheel.  The wheel we're
talking about, is Tortoise Tagger, `here
<http://www.accurussian.net/tagger.htm>`_.

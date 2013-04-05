
.. _../pages/guide/introduction_to_wordfast#introduction_to_wordfast:

Introduction to Wordfast
************************

This page is an overview of `Wordfast <http://www.wordfast.net/>`_, specifically with PO and l10n translation in mind.  For more comprehensive detail about Wordfast, read the user manual, downloadable from the Wordfast web site.

.. _../pages/guide/introduction_to_wordfast#the_way_wordfast_translates:

The way Wordfast translates
===========================

Since Wordfast is simply a Visual Basic macro that runs inside Microsoft Office, translators using Wordfast are in essense using Microsoft Office and all of its available featurs.  Wordfast can therefore be used to translate any document that can be opened in Excel (the spreadsheet) or Word (the word processor).  Wordfast can't translate binary files, but it can translate text files in various encodings.

Translators translating any plaintext file would do the following:

  1. Open the text file in Word, selecting the appropriate text encoding, eg UTF-8
  2. Save the file as an RTF or MS Word document
  3. Prepare the file for translation (optional)
  4. Translate the file, one sentence at a time
  5. Clean the file (explained below)
  6. Save the file as plain text, selecting the appropriate text encoding

.. _../pages/guide/introduction_to_wordfast#1._open_the_file_in_ms_word:

1. Open the file in MS Word
---------------------------

Microsoft Word attempts to guess the file type when opening, and if necessary parses it.  If MS Word believes that a file being opened is XML, it will parse it and won't display the tags.  When saving such a file, MS Word may recode the file according to its own idea of what XML should look like.  For this reason, XML files like XLIFF or TMX can't simply be opened in MS Word, because information will be lost when it is saved.

When a UTF-8 file (or any encoding other than ANSI or ASCII) is opened in MS Word (either by drag-and-drop or by using the File Open menu item), MS Word will guess the encoding and prompt the user to select it from a list.

The trick for our purposes is to force MS Word to prompt the user when opening an XML file.  To this, open a blank document in MS Word, then go Tools -> Options -> General -> Confirm conversion at open.  Then open the file by using the File -> Open menu item (not by drag-and-drop).  If all goes well, MS Word will ask what the file type is (answer "Encoded text") and what the encoding is (usually UTF-8).

MS Word has something called "Unicode" in addition to "UTF-8" -- this is a special Microsoft kind of Unicode that is not really compatible with UTF-8.

.. _../pages/guide/introduction_to_wordfast#2._save_the_file_as_rtf_or_ms_word:

2. Save the file as RTF or MS Word
----------------------------------

Wordfast adds invisible codes to the document while translating, and for this reason the file being translated must be saved as MS Word or RTF format while translating.  These codes are word processing codes and are not saved in the text file when an RTF file is resaved as text.  With MS Word, what you see is what you get (or rather, what you see is what gets saved, if you save as plaintext).

To save a file in MS Word, press F12, and type in the file name, and select the file type.  RTF is sufficient, but MS Word is usually used by Wordfast users.

.. _../pages/guide/introduction_to_wordfast#3._prepare_the_file_for_translation_optional:

3. Prepare the file for translation (optional)
----------------------------------------------

If the file to be translated is a plain text file, then no further preparation is necessary.  However, if the file is an XML file or contains sections that shouldn't be translated, it is necessary to prepare the file by marking the text in such a way that Wordfast will ignore text that shouldn't be translated.

In fact, if a Wordfast user who doesn't know how XML works, receives such a prepared file, he can translate it using Wordfast and deliver a perfectly valid XML file in the target language, because Wordfast will not prompt him to touch any text that shouldn't be touched during the translation process.

Preparing the file involves marking text as translatable and untranslatable, and marking the untranslatable text as either internal or external text.  To illustrate, take a look at this piece of HTML:

  <ul>
  <li><b>This is a <i>dog</i>.</b> That is a <a href="lion.html">cat</a>.</li>
  </ul>

In the above example, the text "This is a dog. That is a cat." should be translated.  The tags <ul> and <li> are not inline tags, and there is no reason why the user should have anything to do with them.  The tags <b> and <i> are inline formatting tags and the tag <a> is also an inline tag.  The translator should not change them, but he will likely have to move them around in the translation.

To prepare the above example text for translation in Wordfast, the tags <ul> and <li> should be marked as external untranslatables, and the tags <b>, <i> and <a> should be marked as internal untranslatables.

Wordfast has special routines for marking HTML, XML and a range of other common formats.  It doesn't have a routine for PO or XLIFF, or for Mozilla .properties and .DTD files, but a quick Find/Replace macro is all that is needed to accomplish that (a macro will be given on a different page).  A tool such as Tortoise Tagger can also be used.

Marking internal untranslatable text can speed up translation, but if a translator knows which texts not to change, it is not necessary for such text portions to be marked as internal.  Marking external text is more crucial.

Here's an example from a Mozilla DTD file:

  <!ENTITY about "About">

In the above example, the text "About" should be translated.  The text '<!ENTITY about "' and '">' should be marked as external untranslatable.

Here are two lines from a Mozilla .properties file:

  prefMessage=Int Pref Value: %d
  extensions.videodownloader.description=Download videos from Youtube

In both lines, the text before the equal sign (and including the equal sign) should be marked as external untranslatable.  The variable "%d" can optionally be marked as internal untranslatable, but that is really not essential.  If the above two lines are marked up as described, Wordfast will prompt the translator to translate "Int Pref Value: %d" and "Download videos from Youtube", and nothing else.

.. _../pages/guide/introduction_to_wordfast#4._translate_the_file,_one_sentence_at_a_time:

4. Translate the file, one sentence at a time
---------------------------------------------

When a translator uses Wordfast, Wordfast segments the text on-the-fly into sentences.  If Wordfast misguesses where a sentence begins or ends (eg if an unexpected abbreviation occurs in mid-sentence), the translator can easily fix the faulty segmentation there and then.

Basically, the translator presses Alt+down to move to the "next segment", then translates it, then presses Alt+down again, and so on.

When the translator presses Alt+down, the next segment is opened in a visual source text box, with an empty target text box below it.  The translator then types his translation in the target text box.  When the translator presses Alt+down again, the two boxes disappear but both the source and target text remain visible, with some special Wordfast codes between them.  These codes are actually hidden text (and the source text is too), so if you press Ctrl+comma, the hidden text is no longer displayed and you can see what the final text would look like.

Here are some screenshots of the above dog/cat example (external = grey, internal = red, translatable = black).

.. _../pages/guide/introduction_to_wordfast#4.1_raw_text,_marked_up_in_styles:

4.1 Raw text, marked up in styles
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The example below is a screenshot taken in MS Word.  As you can see (if you know any HTML), the grey text should not be touched by the translator, and the red text should not be changed, although it could be moved around, depending on the language.

| |image724|

.. |image724| image:: guide:wordfast1.jpg

 |

.. _../pages/guide/introduction_to_wordfast#4.2_alt+down_to_start_translating:

4.2 Alt+down to start translating
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the screenshot below, the translator had pressed Alt+down (i.e. "next segment") in Wordfast.  Wordfast moves the text to be translated to a new line, opens it in a box, and creates an empty box beneath it.  The translator will type his translation in the empty box.  The purple stuff are codes created by Wordfast to know where a segment begins and ends.

Interestingly, the purple text ``<}0{>`` is also an indication of whether a fuzzy match for this segment exists in the TM. In this case, there isn't, but if there had been a 77% match, the text would have read ``<}77{>``.

| |image776|

.. |image776| image:: guide:wordfast2.jpg

 |

.. _../pages/guide/introduction_to_wordfast#4.3_type_in_the_translation:

4.3 Type in the translation
^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the screenshot below, the translator had typed in a translation.  Strictly speaking, the translator could have typed the red text himself, but Wordfast has a method to grab each piece of internal text from the source box and copy it to the position of the cursor in the target box.

| |image744|

.. |image744| image:: guide:wordfast3.jpg

 |

.. _../pages/guide/introduction_to_wordfast#4.4_alt+down_to_go_to_next_segment:

4.4 Alt+down to go to next segment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the screenshot below, the translator had pressed Alt+down again, to go to the next segment.  The previous segment is no longer on its own line, but is inline with the text surrounding it.  The purple markers remain, to tell Wordfast where the segment begins and ends.

| |image32|

.. |image32| image:: guide:wordfast4.jpg

 |

.. _../pages/guide/introduction_to_wordfast#4.5_type_in_the_translation_again:

4.5 Type in the translation again
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the screenshot below, the translation has been typed in again.

| |image500|

.. |image500| image:: guide:wordfast5.jpg

 |

.. _../pages/guide/introduction_to_wordfast#4.6_end_the_translation_session:

4.6 End the translation session
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

At any time the translator can "end the session" by closing the current segment and not moving on to the next segment.  In the screenshot below, the session automatically ended because the last segment was reached.

| |image562|

.. |image562| image:: guide:wordfast6.jpg

 |

.. _../pages/guide/introduction_to_wordfast#4.7_hide_hidden_text:

4.7 Hide hidden text
^^^^^^^^^^^^^^^^^^^^

In the screenshot below, the translator had pressed Ctrl+comma (i.e. "toggle hidden text").  Only the text that doesn't have the "hidden" attribute is displayed.  This is also what the document would look like after clean-up.

| |image9|

.. |image9| image:: guide:wordfast7.jpg

 |

.. _../pages/guide/introduction_to_wordfast#5._clean_the_file:

5. Clean the file
-----------------

A file that has been translated with Wordfast contains both source text and target text, as well as other codes in purple.  It may also have text marked as internal or external untranslatable.  Even if the client is expecting an MS Word or RTF file back, it is obvious that the translator can't send it back in this form.  So the trick is to "clean" the file.  The function called "Clean" only removes the purple codes and the source text -- it does not remove untranslatable markings.

The screenshot at 4.7 above is what a cleaned file would look like.

The translator can reopen any segment by placing his cursor anywhere in the segment and pressing Alt+down (next segment).  He can then edit the translation, and close the segment again.  In sucn a case, the TM is updated automatically with the new translation.

The translator could send the "uncleaned" file to colleagues for proofreading.  Note that it is possible to edit the uncleaned file without using Wordfast, if care is taken not to overwrite the purple tags.  A proofreader can edit an uncleaned file using Track Changes, for example, and the translator or project manager can accept/reject such changes, without affecting the integrity of the uncleaned file.  One can also perform a spell-check on the unclean file, and let MS Word correct spelling errors in it.

Changes made to the translations by not opening and closing the segments with Wordfast, will not be reflected in the TM.  When a file is cleaned using Wordfast's "clean" function, Wordfast updates the TM by comparing the segments in the document with the segments in the TM. 

.. _../pages/guide/introduction_to_wordfast#6._save_the_file_as_plaintext:

6. Save the file as plaintext
-----------------------------

To use the translation in its l10n context, the file should be saved as plaintext.  The translator works on an MS Word document during the translation process, but after he had cleaned the document, he saves it as plaintext.  In MS Word, this is called "Encoded text" (the translator gets to choose which encoding).

MS Word will give text files the file extension "TXT".  If a different file extension is required, the files should be renamed in MS DOS or using some other renaming tool.

.. _../pages/guide/introduction_to_wordfast#marking_text_with_styles:

Marking text with styles
========================

Many Wordfast users have never worked with documents that have been marked with untranslatable text.  This shouldn't be a problem as long as they are told not to attempt to translate the grey text, and that they should use "Next Placeable", "Previous Placeable" and "Place Placeable" to copy the red text.

Placeables are pieces of text that Wordfast can grab in the source box and copy to the position of the cursor in the target box.  Placeables can be placed using icons on the Wordfast toolbar, or using keyboard shortcuts (see the Wordfast manual for a comprehensive list of shortcuts).

Even if a Wordfast user has worked with such marked documents before (they are referred to as tagged texts), he may not know how to mark such a document himself.  Ideally, therefore, the marking up of a document will be done by a project manager or senior translator.


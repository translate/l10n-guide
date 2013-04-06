
.. _../pages/guide/po_with_wordfast#translating_po_files_with_wordfast:

Translating PO files with WordFast
**********************************

| I'd like to make some notes that can be reused for someone using
| WordFast if they wanted to translate PO files.

Well, the important thing to remember is that Wordfast is not intelligent.  The
intelligence lies with the translator and/or the guy writing the tagger.
Thankfully PO is quite simple, and if the lines are not wrapped, a translator
can tag it almost manually.

What is tagging?

Well, in an MS Word document, you can apply a "style" to certain pieces of
text.  Default styles include Heading 1, Paragraph, etc.  You can also set the
behaviour of a style, so that all text with that style will look the same way.
For example, I could set "Heading 1" to be Arial font, size 12, red text on a
blue background, and all text with the style Heading 1 will look that way.
It's kinda like HTML.  You can also create your own "styles", and make them
look like any thing you want to.  The nice thing about styles is that you can
tell a macro or a Find/Replace operation to perform its actions only on certain
styles instead of the entire text.  Very few people who use MS Word are aware
of the great possibilities that exist thanks to "styles".

If I were to translate an HTML document in MS Word, I could do it as follows:
First copy the text (the HTML code) to an empty MS Word document.  Then create
a unique style with a unique name.  Then use Find/Replace to change the style
of all the non-translatable code to that unique style.  Then write a macro
which extracts the translatable text by ignoring everything which is in that
unique style.  Or, write a macro which hides all text which is in that unique
style (so that only the translatable text is visible).  Or, well, you can see
the possibilities here.

In Wordfast (and in Trados) there are two such unique styles, with which the
macros interact in a special way.  The one style is called tw4winExternal and
the other is called tw4winInternal.  In an HTML file (saved as an MS Word
document), the External style is applied to block-level code and the Internal
style is applied to line-level code.  The Wordfast macro ignores everything
which has the External style, and creates a temporary text box with each
sentence of translatable text in which the translator types the translation.
Text with the Internal style has a red colour, so that the translator can see
which pieces of line-level HTML he should watch out for.  In this way, the
translator doesn't need to know HTML and yet he can translate directly within
an HTML document (using MS Word) without any fear of "breaking" the code.

Marking the untranslatable code with External and Internal styles, is known as
"tagging".

So, a translator faced with a tagged PO file in MS Word will not necessarily
know how the PO format works.  He will be able to see everything in the PO
file, but he'll ignore it because Wordfast will automatically allow him access
only to the text to the translated.

And now for the complication...

In Wordfast, the source text is *overwritten* with the target text.  This means
that when the translator gets the file from the client, the file must already
be in such a way that the source text can be overwritten by the target text.
This is why I insist on a "duplicated" PO file (however, I can duplicate it in
MS Word too, so if the client is unable to provide a "duplicated" file, I can
do it myself anyway).

Now, if you think about it carefully, you'll see that a translator *cannot*
deal with PO fuzzys in Wordfast.  Not possible.

However, most of the time when fuzzys occur, it is because an existing string
(which had been translated before) has changed slightly, right?  So it follows
that the old string and its correct translation is still available somewhere.
If this old string and its translation isn't in the translation memory (TM)
already, it can easily be added to it, right?

Therefore, a simple workmethod is to delete all the proposed translations of
fuzzys and turn the fuzzys into untranslateds (and then "duplicate" them), and
translate them as usual.

Translating Opera

When I get PO files from my contact at Opera, the translated, fuzzy and
untranslated strings are in a single file.  First I used Gnu Gettext tools to
separate these into three files.  Then I turn the fuzzy strings into
untranslated strings.  Then I do the translation on the two "untranslated"
files, and then I merge them back into the original file (the translated
strings remain untouched by this process).

With Dwayne's PO files, I have to be more careful, and that is why I prefer
that he does the gymnastics (then if something goes wrong and it is a
conversion issue, then it's his fault).  The gymnastics I'm referring to here,
is separating the translated from the untranslated, and putting them into
separate files.  The "duplication" I can do flawlessless in MS Word (as long as
the lines are unwrapped).

What is duplication (just in case you don't know)?

Here is an unduplicated PO string:

.. code-block:: po

  # This is a comment.
  # This is another comment.
  msgstr "This is the source text."
  msgid ""

Here is a duplicated PO string:

.. code-block:: po

  # This is a comment.
  # This is another comment.
  msgstr "This is the source text."
  msgid "This is the source text."

Here is a translated PO string:

.. code-block:: po

  # This is a comment.
  # This is another comment.
  msgstr "This is the source text."
  msgid "Hierdie is die bronteks."

These examples are oversimplified, of course.

Any questions?

The reason why some of the first PO files I did for Dwayne, didn't quite work
out well, was because I didn't know how to do regex back then, so I didn't know
how to do tagging, so instead I did a roundtripping which turned out to be only
99% lossless.  Ouch (and again: sorry).

Samuel


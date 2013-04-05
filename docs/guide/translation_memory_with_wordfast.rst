
.. _../pages/guide/translation_memory_with_wordfast#creating_a_translation_memory_with_wordfast:

Creating a Translation Memory with WordFast
*******************************************

| Dwayne Bailey wrote on 24/01/2006 09:16 PM:
| 
| > On Tue, 2006-01-24 at 15:33 +0200, Samuel Murray wrote:
| 
| >> Here's what I would have done (if it were just me)...
| 
| > All this download, freeware, right click stuff makes me nervous :)
| 
| Hey... I thought Linux people thrived on modular approaches!
| 
| >> What I would have done, was to create a translation memory using the 
| >> translated strings of 1.0.5, ...
| 
| > You don't say how.
| 
| Okay, first step, try to think like a Windows user.  Then... well, 
| okay... just kidding, skip that step :-)
| 
| 1.  Download firefox-af-1.0.7.tar.gz and unzip it.
| 2.  Open all the PO files in MS Word (well, ten at a time is better), 
| and save them in MS Word or RTF format.  Tip: open the files by dragging 
| and dropping into an empty MS Word instance.
| 3.  Convert the PO files into memories (there are two ways of doing 
| this, Method A and Method B, each with pros and cons).
| 
| But first:  What is an uncleaned Trados file?
| 
| Right... how to explain this... erm... see, when you translate a file 
| using Wordfast (or Trados), the macros in Wordfast split the text into 
| segments, and the translator translates one segment at a time.  When the 
| translation is finished, the end-result is an MS Word or RTF file known 
| as an uncleaned document (or, an uncleaned Trados file).  The file looks 
| like this:
| 
| {0>This is a house.<}0{>Dit is 'n huis.<0} {0>This is another 
| house.<}77{>Dit is nog 'n huis.<0} {0>This is not a house.<}85{>Dit is 
| nie 'n huis nie.<0} {0>These are not houses.<}35{>Hierdie is nie huise 
| nie.<0}
| 
| The numbers indicate the fuzzy match percentage calculated during the 
| translation process.  Don't worry about the numbers... under different 
| circumstances they have different meanings, so forget about them for now.
| 
| The source text is usually marked as "hidden text" in MS Word, but this 
| is not required.  The tags {0>, <}[0-9][0-9]{> and <0} are in a unique 
| style known as tw4winMark (usually displayed as purple text).
| 
| The client might give this uncleaned file to a proofreader to check the 
| translation.  The proofreader might make several changes to the target 
| pieces of text.  When the client receives the proofread text back, he 
| would naturally want the changes to be updated in his translation 
| memory, right?  So he loads the proofread uncleaned document into 
| Wordfast, and he loads his original translation memory (which was 
| created when the document was originally translated) into Wordfast, and 
| he performs a "cleanup".  The cleanup removes the source text, it 
| removes the tags, and it checks every segment against the translation 
| memory, and updates the translation memory when it finds a changed segment.
| 
| And now for the nice one:  If during the cleanup, Wordfast finds a 
| segment in the uncleaned document which is not in the translation 
| memory, it adds that segment to the translation memory.  It follows, 
| therefore, that if you do a cleanup using an *empty* translation memory, 
| that all the segments will be added to the translation memory during 
| cleanup.  And this is the key to Method A mentioned above.
| 
| Method A
| 
| Convert this:
| 
| # This is a comment.
| # This is another comment.
| msgstr "I don't use Linux if I can help it."
| msgid "Ek gebruik nie Linux as ek dit kan verhelp nie."
| 
| into this:
| 
| {0>I don't use Linux if I can help it.<}0{>Ek gebruik nie Linux as ek 
| dit kan verhelp nie.<0}
| 
| and then do a cleanup on an empty translation memory.
| 
| Pros:  quick and easy
| Cons:  segmentation according to PO rules, not Wordfast rules
| 
| Let me explain the segmentation issue here.  According to this method, 
| this string:
| 
| # This is a comment.
| # This is another comment.
| msgstr "I'm a very happy Windows user.  I'm a very happy Windows user. 
| I'm a very happy... I'm a very happy... Oh, I'm a very happy Windows user."
| msgid "Ek's 'n baie bly Windows-gebruiker.  Ek's 'n baie bly 
| Windows-gebruiker.  Ek's 'n baie bly... Ek's 'n baie bly... O, ek's 'n 
| baie bly Windows-gebruiker."
| 
| will be turned into this:
| 
| {0>I'm a very happy Windows user.  I'm a very happy Windows user.  I'm a 
| very happy... I'm a very happy... Oh, I'm a very happy Windows 
| user.<}0{>Ek's 'n baie bly Windows-gebruiker.  Ek's 'n baie bly 
| Windows-gebruiker.  Ek's 'n baie bly... Ek's 'n baie bly... O, ek's 'n 
| baie bly Windows-gebruiker.<0}
| 
| which means that there will be one segment containing five sentences.
| 
| According to Wordfast segmentation rules, however, there should be at 
| least three segments:
| 
| {0>I'm a very happy Windows user.<}0{>Ek's 'n baie bly 
| Windows-gebruiker.<0} {0>I'm a very happy Windows user.<}100{>Ek's 'n 
| baie bly Windows-gebruiker.<0} {0>I'm a very happy...<}0{>Ek's 'n baie 
| bly...<0} {0>I'm a very happy...<}100{>Ek's 'n baie bly...<0} {0>Oh, I'm 
| a very happy Windows user.<}94{>O, ek's 'n baie bly Windows-gebruiker.<0}
| 
| This means that PO strings containing more than one Wordfast segment 
| will not get any matches (or will get less useful matches) from a 
| Wordfast translation memory.
| 
| Method B
| 
| Method B is to create two files -- one containing only the source text 
| and one containing only the target text -- and align them.  Method two 
| takes a bit longer, and involves manual labour, but it produces a 
| translation memory which is very, very useful because it uses exactly 
| the same segmentation rules as those which would be used during the 
| final translation.
| 
| Ideally, one would use both method A and B, and then combine the two 
| memories into a single super memory, which would yield more matches.
| 
| Since the Firefox old translation is not a single file but several 
| files, it would be easier to use Method B on the memory which was 
| created using Method A, than to attempt to extract the source and target 
| text from the 100 PO files and hope to maintain the sentences in an 
| alignable order.
| 
| Wordfast has an "extract" feature in which it segments the text of a 
| document into segments, each on its own line.  Hence, if you run an 
| extract on this paragraph:
| 
| This is a house.  This is another house.  This is not a house.  This is 
| the best house I have ever seen.  This is a house.  These are houses.
| 
| the end-result would be:
| 
| This is a house.
| This is another house.
| This is not a house.
| This is the best house I have ever seen.
| This is a house.
| These are houses.
| 
| and if you have a translation of this document, the translated strings 
| could also be extracted to something like:
| 
| Dit is 'n huis.
| Dit is nog 'n huis.
| Dit is nie 'n huis nie.
| Dit is die beste huis wat ek al gesien het.
| Dit is 'n huis.
| Hierdie is huise.
| 
| and then, because the source and target sentences in these two extracted 
| documents are mostly in the same order, you can align these two 
| documents in table form (or another form) and manually check to see if 
| each source segment fits the target segment that follows it.
| 
| Then correct the misalignments, press a button (Create TM), and let 
| Wordfast create a translation memory based on these segments.  Et voila.
| 
| Does this answer your question?  Any other questions?
| 
| Samuel

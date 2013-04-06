
.. _../pages/guide/pofilter_examples#common_translation_errors:

Common Translation Errors
*************************

The following are common errors detected by the :ref:`toolkit:pofilter` tool.
It is usefull to see these errors in order that you don't commit them yourself.
We have given examples of some false positives also.

.. _../pages/guide/pofilter_examples#double_spacing:

Double Spacing
==============

Notice the double space in "lefoko  la".

.. code-block:: po

    #: NoColorError
    #, fuzzy
    #_ doublespacing: checks for bad double-spaces by comparing to original
    msgid "Click on a color or enter a valid HTML color string"
    msgstr ""
    "tobetsa mmala kgotsa tsenya lefoko  la mmala la html le le letleletsweng"

The following is a false postive, notice that the double space ("account.
There") is in the msgid.

.. code-block:: po

    #: accountSettingsDesc.label
    #, fuzzy
    #_ doublespacing: checks for bad double-spaces by comparing to original
    msgid ""
    "The following is a special account.  There are no identities associated with "
    "it."
    msgstr ""
    "Se se latelang ke akhaoto e kgetegileng. Ga go kitsiso e kamano le yona."

.. _../pages/guide/pofilter_examples#end_punctuation:

End Punctuation
===============

The sentence is missing a fullstop.

.. code-block:: po

    #: MissingSiteNameError
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Please enter a name for this publishing site."
    msgstr "ka kopa tsenyetsa letlakala le la phatlalatso leina"

The sentence is missing and elipse (...)

.. code-block:: po

    #: AdvancedProperties
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Advanced Properties..."
    msgstr "ditiro tsa maemo a kwa godim"

Missing colon (:)

.. code-block:: po

    #: JobTitle.label
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Title:"
    msgstr "Setlha"

The end contains a space before the colon which shouldn't be there.

.. code-block:: po

    #: addressMessageTo.label
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Address message to:"
    msgstr "Attresetsa molaetsa go :"

Notice that the msgid is incorrect (it only has 2 dors) and the msgstr has been
corrected.  Leave this as it is as the msgstr is now correct.  Also report this
as an error against the application.

.. code-block:: po

    #: saveAll.label
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Save All.."
    msgstr "Boloka tsotlhe..."

There should be a space before "->"

.. code-block:: po

    #: fieldMapExport.add
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Add Field ->"
    msgstr "Atisa lebala->"

The msgstr should end in ? but it ends in .

.. code-block:: po

    #: PKCS12PasswordInvalid
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid ""
    "Could not decode PKCS #12 file.  Perhaps the password you entered was "
    "incorrect?"
    msgstr ""
    "Ga ya kgona go sirolola PKCS #12 file.  Gongwe lefoko-phetiso leo o le "
    "tsentseng le fosagetse."

The closing bracket should be a round bracket not a curly bracket.

.. code-block:: po

    #: UnknownCertIssuer
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "(Unknown Issuer)"
    msgstr "(Mofi ga e itsewe}"

.. _../pages/guide/pofilter_examples#end_whitespace:

End Whitespace
==============

Remove the extra whitespace at the end.

.. code-block:: po

    #: deleteCardCmd.label
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    #_ endwhitespace: checks whether whitespace at the end of the strings matches
    msgid "Delete Card"
    msgstr "Ntsha karata "

.. _../pages/guide/pofilter_examples#start_punctuation:

Start Punctuation
=================

False positive. The translation is correct, although you might want to define a
policy on how you handle this form of plural.

.. code-block:: po

    #: SuccessfulP12Backup
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    #_ startpunc: checks whether punctuation at the beginning of the strings match
    msgid "Successfully backed up your security certificate(s) and private key(s)."
    msgstr ""
    "(Di/Se)tifikeiti tsa gago tsa pabalelo le (di/se)lotlolo (t)sa bosephiri di/"
    "se bolokilwe thuso-morago ka tswelelopele."

.. _../pages/guide/pofilter_examples#start_whitespace:

Start Whitespace
================

The space at the beginning of the message should be deleted.

.. code-block:: po

    #: DisableDlgTitle
    #, fuzzy
    #_ startwhitespace: checks whether whitespace at the beginning of the strings matches
    #_ startpunc: checks whether punctuation at the beginning of the strings match
    msgid "%S Quick Launch"
    msgstr " %S Quick Launch"

The space at the beginning of the message should be deleted.

.. code-block:: po

    #: ko
    #, fuzzy
    #_ startwhitespace: checks whether whitespace at the beginning of the strings matches
    #_ startpunc: checks whether punctuation at the beginning of the strings match
    msgid "Korean"
    msgstr " SeKorea"

.. _../pages/guide/pofilter_examples#numbers:

Numbers
=======

The number 1252 does not appear in the translation.

.. code-block:: po

    #: windows-1252.title
    #, fuzzy
    #_ numbers: checks whether numbers of various forms are consistent between the two strings
    msgid "Western (Windows-1252)"
    msgstr "Turkish (Windows-1254)"

Might not be a problem if 2 has been written in full

.. code-block:: po

    #: SSL2Disabled
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    #_ numbers: checks whether numbers of various forms are consistent between the two strings
    msgid "You cannot connect to %S because SSL version 2 is disabled."
    msgstr "Ga o kgone go lomagana go %S ka gonne SSL e ntshitswe bokgoni.."

.. _../pages/guide/pofilter_examples#variables:

Variables
=========

&vendorShortName; should not have been translated.

.. code-block:: po

    #: throbber.tooltip
    msgid "Go to the &vendorShortName; home page"
    msgstr "E ya ko &vendorKortNaam; go letlakala la le gae"

&quot; should not have been translated

.. code-block:: po

    #: incomingServerNameDesc.label
    #, fuzzy
    #_ variables: checks whether variables of various forms are consistent between the two strings
    msgid "Enter the name of your incoming server (for example, &qout;mail.example.net&quot;)."
    msgstr "Tsenya leina la moridi~Zi wa gago yo a go romelago molaet~Za (ka mohlala, &tsopolo;poso.mohlala.net&tsopolo;)."

.. _../pages/guide/pofilter_examples#punctuation_spacing:

Punctuation Spacing
===================

There should be a space after , in "Ka sekai,netscape".  A single quote is also
missing.

.. code-block:: po

    #: abbreviateOn.label
    #, fuzzy
    #_ puncspacing: checks for bad spacing after punctuation
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Full names (For example, 'netscape.public.mozilla.mail-news')"
    msgstr "Maina ka botlalo (Ka sekai,netscape.public.mozilla.posol-dikgang')"

Space missing after colon.

.. code-block:: po

    #: unreadMsgStatus
    #, fuzzy
    #_ puncspacing: checks for bad spacing after punctuation
    msgid "Unread: %S"
    msgstr "Ga ja balwa:%S"

Space missing after comma "kenna,o sutlhe"

.. code-block:: po

    #: defaultcharactersetBidiCmd.label
    #, fuzzy
    #_ puncspacing: checks for bad spacing after punctuation
    msgid ""
    "Use my default character set, overriding the document-specified character set"
    msgstr ""
    "dirisa ditlhaka jaaka ditlhophilwe kenna,o sutlhe tse di tlhophetsweng "
    "tokomane e"

Space missing after semi-colon "da dk;faele".  Also note missing minus between
da and DK.

.. code-block:: po

    # LOCALIZATION NOTE GROUP : DO not localize the entities below; test case
    #: da-DK-file.label
    #, fuzzy
    #_ puncspacing: checks for bad spacing after punctuation
    msgid "Danish (da-DK; file)"
    msgstr "danish (da dk;faele)"

.. _../pages/guide/pofilter_examples#short:

Short
=====

There is a missing sentence

.. code-block:: po

    #: SIClueless
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    #_ endwhitespace: checks whether whitespace at the end of the strings matches
    msgid ""
    "There are unknown problems with this digital signature. You should not trust "
    "the validity of this message until you verify its contents with the sender."
    msgstr "Gona le mathata ao a sa itsiweng ka mosaeno o wa dinomoro. "

.. _../pages/guide/pofilter_examples#long:

Long
====

The translation looks too long, it might be right but it is unlikely.

.. code-block:: po

    #: directionBidiMenu.label
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Default Direction"
    msgstr ""
    "tshupetso e e diragadiwang fela fa ditshupetso tse dirulagantsweng go "
    "diragalapele sitwa godiragala."

.. code-block:: po

    #: mediaEncryption
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Encryption:"
    msgstr "fetolelo go mokwalo o o fitlhang tshedimosetso ka ga lefoko la tlwaelo"

.. _../pages/guide/pofilter_examples#unchanged:

Unchanged
=========

The english has not been translated.  The word plugin is translatable.  In fact
this example show two more errors, the start capital is missing and the colon
is also missing.  So this translators took an English string and replace it
with an untranslated and badly formated string.

.. code-block:: po

    #: mediaPlugin
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "Plugin:"
    msgstr "plugin"

.. _../pages/guide/pofilter_examples#urls_and_emails:

URLs and Emails
===============

This is a well translated email address in this case it was used as an example
so is translated

.. code-block:: po

    #: emailExample.label
    #, fuzzy
    #_ endpunc: checks whether punctuation at the end of the strings match
    msgid "(for example: user@example.net)."
    msgstr "(ka mohlala: modirisi@mohlala.net)"


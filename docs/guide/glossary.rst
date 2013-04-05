
.. _../pages/guide/glossary#glossary:

Glossary
********

Note: many of the terms use an abbreviation of the form x10y where 10 stands for the number of letters between the first letter x and the last letter y (e.g. l10n)

  * a12n --- see Africanisation
  * a11y --- see Accessibility
  * **Accessibility** --- This is the effort to make software device independent, for input, output, and "display".  this includes screen reading software, devices controlled by brain waves, and everything in between. This effort is mostly aimed at ensuring that computers and devices are usable by people with disabilities.
  * **Africanisation** --- Any activity that assists with the localisation and globalisation of software for the African continent.
  * **CAT** --- Computer Aided Translation.  Any one of a number of tools that assist translators during translation.
  * CLDR --- see Common Locale Data Repository
  * **Common Locale Data Repository** --- this is an effort to provide a unifies locale data repository, thus merging a number of seperate efforts.  They have also defined an XML standard for storing locale data seems to be much more flexible then current methods.
  * **fuzzy translation** --- This has two meanings: 1) In Gettext translation: any string that has been modified or guessed by the Gettext tools ie a piece of text that needs your review. 2) In the localisation industry: a fuzzy string is an attempt to match the untranslated string with information from a TM.  Usually this is expressed as a percentage eg 80% match.
  * g11n --- see Globalisation
  * **Gettext** --- A set of tools used primarily on Linux and Unix computers that makes a program translatable.  The toolset provides tools to extract messages from programs, to manipulate the translations, to compile the translations and to allow a program to appear translated when it is run.
  * **Globalisation** --- FIXME
  * i18n --- see Internationalisation
  * **Internationalisation** --- this is the process of making a program localisable.  This would cover work to allow for different fonts and charactersets to be displayed correctly.  To allow for scripts that run from right-to-left, etc.  This work is usually done once for a language, once the toolkits and programs support a language the internationalsiation work is usually complete.
  * l10n --- see Localisation
  * l12y --- see Localisability
  * l18n --- see either i18n or l10n.  This is a common mispelling of one of these words.
  * **Locale** --- this is a file that defines the locale data for your language and country.  A locale covers things such as: the names of months and days of the week, how to write dates in your language, how your write numebr and currency values, the sort order of your language and much else.  This data is essential for a computer to support your language.
  * **Localisation** --- This is the process of taking an existing program or operating system and making it work in your language.  This would include translating: interface and documentation, creating a locale file and the creation of fonts.  It would not include changing the widget set or program operation to cater for your language, that work would fall under internationalisation.
  * **Localisability** --- This is the degree to which a program can be localized - for example, fixed strings in a program that cannot be translated would be a localisability issue
  * m17n --- Multilingualization
  * **Machine Translation** --- when a machine translates from one language to another.  You might also hear of Machine Assisted Translation, this is where a machine does the initial translation usually drawing heavily on a Translation Memory and a human translator does the final approval and correction.
  * **MO** --- Machine Object file.  This is the result of compiling a PO file using Gettext's msgfmt command.  MO file are used because they are much quicker for a computer to read then PO files.
  * MT --- see Machine Translation
  * **Multilingualization** --- This has one several different usages:
    - The UI has a user selectable choice of languages.
    - The user can input data in a number of different languages.
    - The user can select the output in a number of different languages.
  * **PO** --- Portable Object file.  These are the files produced by xgettext (cf.) that a translator translates into their language.  These files are compiled using Gettext (cf.) tools into an MO file (cf.)
  * **PO Editor** --- Any one of a number of tools that can edit PO files.  PO files are plain text files and in most cases a PO editor will hide the complexity from the translator and provide extra features like translation memory, etc.
  * **TEnT** --- Translation Environment Tool.  A term suggested by some (Jost Zetzsche) as an alternative to CAT (cf.).
  * TM --- see Translation Memory
  * TMX --- see Translation Memory Exchange format
  * **Translation Memory Exchange format** --- TMX allows you to export, import and thus exchange translation memory data between various CAT tools.
  * **Translation Memory** --- to reuse existing translations you make use of a TM.  It makes translation faster but also ensures the translations remain consistent.
  * **Unicode** --- This is a standard that is able to represent all characters for all alphabets in one character set.  By doing this you are able to display any all and any character or language on one page.  Unicode only provides the encoding you would still need fonts to display the text.
  * UI --- User Interface
  * **UTF-8** --- A method of encoding Unicode using 8 bits.  Other methods include UTF-7, UTF-16 and UTF-32. UTF-8 is the most dominant method of encoding Unicode characers, but UTF-16 is becoming more common.
  * **XLIFF** --- A new file format for representing translation data.  It provides much more usefull features then any current format and you will see this become more widely adopted in future.
  * **xgettext** --- a program which is part of the Gettext (cf.) tools that extracts translatable content from programs and stores them in a PO (cf.) files that will be translated by a translator.


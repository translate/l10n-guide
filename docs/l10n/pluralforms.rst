.. _pluralforms:

Plural Forms
************

This is a list of the plural forms, as used by Gettext PO, that are appropriate
to each language.

If your language isn't represented -- please add it, or if the information is
inaccurate or inadequate in some way -- please edit it.  The Plural information
is usually very hard to find and also in many ways hard for a new localiser to
understand.  So please see this as a repository that can help localisers.
Understanding how the Gettext functions use plural forms will help you `design
a correct plural form
<http://www.gnu.org/software/gettext/manual/gettext.html#Plural-forms>`_.

.. note:: Launchpad also has `plural information
   <https://translations.launchpad.net/+languages>`_ for many languages, please
   add it here if your language is missing.

.. note:: Mozilla now also uses `plural forms
   <https://developer.mozilla.org/en/docs/Localization_and_Plurals>`_.  Although
   they follow a slightly different form, the `underlying equations
   <http://mxr.mozilla.org/mozilla/source/intl/locale/src/PluralForm.jsm#59>`_
   seem to be the same as those used by Gettext.

.. note:: Many of these rules have been generated with `cldr-to-gettext-plural-rules
   <https://github.com/mlocati/cldr-to-gettext-plural-rules>`_, a tool that generates
   the plural rules starting from the `Unicode CLDR data
   <http://cldr.unicode.org/>`_

.. _pluralforms#list:

.. We should build this automatically from the data that we have in the
   Translate Toolkit.

.. csv-table::
   :header-rows: 1
   :widths: 5 20 75

   ISO,     English name,            Plurals header in .po files
   **A**
   ach,     Acholi,                  nplurals=2; plural=(n > 1);
   af,      Afrikaans,               nplurals=2; plural=(n != 1);
   ak,      Akan,                    nplurals=2; plural=(n > 1);
   am,      Amharic,                 nplurals=2; plural=(n > 1);
   an,      Aragonese,               nplurals=2; plural=(n != 1);
   anp,     Angika,                  nplurals=2; plural=(n != 1);
   ar,      Arabic,                  nplurals=6; plural=((n == 0) ? 0 : ((n == 1) ? 1 : ((n == 2) ? 2 : ((n % 100 >= 3 && n % 100 <= 10) ? 3 : ((n % 100 >= 11 && n % 100 <= 99) ? 4 : 5)))));
   ar_001,  Modern Standard Arabic,  nplurals=6; plural=((n == 0) ? 0 : ((n == 1) ? 1 : ((n == 2) ? 2 : ((n % 100 >= 3 && n % 100 <= 10) ? 3 : ((n % 100 >= 11 && n % 100 <= 99) ? 4 : 5)))));
   arn,     Mapudungun,              nplurals=2; plural=(n > 1);
   as,      Assamese,                nplurals=2; plural=(n > 1);
   asa,     Asu,                     nplurals=2; plural=(n != 1);
   ast,     Asturian,                nplurals=2; plural=(n != 1);
   ay,      Aymará,                  nplurals=1; plural=0;
   az,      Azerbaijani,             nplurals=2; plural=(n != 1);
   **B**
   be,      Belarusian,              nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   bem,     Bemba,                   nplurals=2; plural=(n != 1);
   bez,     Bena,                    nplurals=2; plural=(n != 1);
   bg,      Bulgarian,               nplurals=2; plural=(n != 1);
   bh,      Bihari,                  nplurals=2; plural=(n > 1);
   bm,      Bambara,                 nplurals=1; plural=0;
   bn,      Bengali,                 nplurals=2; plural=(n > 1);
   bo,      Tibetan,                 nplurals=1; plural=0;
   br,      Breton,                  nplurals=5; plural=((n % 10 == 1 && n % 100 != 11 && n % 100 != 71 && n % 100 != 91) ? 0 : ((n % 10 == 2 && n % 100 != 12 && n % 100 != 72 && n % 100 != 92) ? 1 : ((((n % 10 == 3 || n % 10 == 4) || n % 10 == 9) && (n % 100 < 10 || n % 100 > 19) && (n % 100 < 70 || n % 100 > 79) && (n % 100 < 90 || n % 100 > 99)) ? 2 : ((n != 0 && n % 1000000 == 0) ? 3 : 4))));
   brx,     Bodo,                    nplurals=2; plural=(n != 1);
   bs,      Bosnian,                 nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   **C**
   ca,      Catalan,                 nplurals=2; plural=(n != 1);
   ce,      Chechen,                 nplurals=2; plural=(n != 1);
   cgg,     Chiga,                   nplurals=2; plural=(n != 1);
   chr,     Cherokee,                nplurals=2; plural=(n != 1);
   ckb,     Central Kurdish,         nplurals=2; plural=(n != 1);
   cs,      Czech,                   nplurals=3; plural=((n == 1) ? 0 : ((n >= 2 && n <= 4) ? 1 : 2));
   csb,     Kashubian,               nplurals=3; plural=(n==1) ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2;
   cy,      Welsh,                   nplurals=6; plural=((n == 0) ? 0 : ((n == 1) ? 1 : ((n == 2) ? 2 : ((n == 3) ? 3 : ((n == 6) ? 4 : 5)))));
   **D**
   da,      Danish,                  nplurals=2; plural=(n != 1);
   de,      German,                  nplurals=2; plural=(n != 1);
   de_AT,   Austrian German,         nplurals=2; plural=(n != 1);
   de_CH,   Swiss High German,       nplurals=2; plural=(n != 1);
   doi,     Dogri,                   nplurals=2; plural=(n != 1);
   dsb,     Lower Sorbian,           nplurals=4; plural=((n % 100 == 1) ? 0 : ((n % 100 == 2) ? 1 : ((n % 100 == 3 || n % 100 == 4) ? 2 : 3)));
   dv,      Divehi,                  nplurals=2; plural=(n != 1);
   dz,      Dzongkha,                nplurals=1; plural=0;
   **E**
   ee,      Ewe,                     nplurals=2; plural=(n != 1);
   el,      Greek,                   nplurals=2; plural=(n != 1);
   en,      English,                 nplurals=2; plural=(n != 1);
   en_AU,   Australian English,      nplurals=2; plural=(n != 1);
   en_CA,   Canadian English,        nplurals=2; plural=(n != 1);
   en_GB,   British English,         nplurals=2; plural=(n != 1);
   en_US,   American English,        nplurals=2; plural=(n != 1);
   eo,      Esperanto,               nplurals=2; plural=(n != 1);
   es,      Spanish,                 nplurals=2; plural=(n != 1);
   es_419,  Latin American Spanish,  nplurals=2; plural=(n != 1);
   es_AR,   Argentinean Spanish,     nplurals=2; plural=(n != 1);
   es_ES,   European Spanish,        nplurals=2; plural=(n != 1);
   es_MX,   Mexican Spanish,         nplurals=2; plural=(n != 1);
   et,      Estonian,                nplurals=2; plural=(n != 1);
   eu,      Basque,                  nplurals=2; plural=(n != 1);
   **F**
   fa,      Persian,                 nplurals=2; plural=(n > 1);
   ff,      Fulah,                   nplurals=2; plural=(n > 1);
   fi,      Finnish,                 nplurals=2; plural=(n != 1);
   fil,     Filipino,                nplurals=2; plural=(n != 1 && n != 2 && n != 3 && (n % 10 == 4 || n % 10 == 6 || n % 10 == 9));
   fo,      Faroese,                 nplurals=2; plural=(n != 1);
   fr,      French,                  nplurals=2; plural=(n > 1);
   fr_CA,   Canadian French,         nplurals=2; plural=(n > 1);
   fr_CH,   Swiss French,            nplurals=2; plural=(n > 1);
   fur,     Friulian,                nplurals=2; plural=(n != 1);
   fy,      Western Frisian,         nplurals=2; plural=(n != 1);
   **G**
   ga,      Irish,                   nplurals=5; plural=((n == 1) ? 0 : ((n == 2) ? 1 : ((n >= 3 && n <= 6) ? 2 : ((n >= 7 && n <= 10) ? 3 : 4))));
   gd,      Scottish Gaelic,         nplurals=4; plural=((n == 1 || n == 11) ? 0 : ((n == 2 || n == 12) ? 1 : ((n >= 3 && n <= 10 || n >= 13 && n <= 19) ? 2 : 3)));
   gl,      Galician,                nplurals=2; plural=(n != 1);
   gsw,     Swiss German,            nplurals=2; plural=(n != 1);
   gu,      Gujarati,                nplurals=2; plural=(n > 1);
   gun,     Gun,                     nplurals=2; plural=(n > 1);
   guw,     Gun,                     nplurals=2; plural=(n > 1);
   gv,      Manx,                    nplurals=4; plural=((n % 10 == 1) ? 0 : ((n % 10 == 2) ? 1 : ((n % 100 == 0 || n % 100 == 20 || n % 100 == 40 || n % 100 == 60 || n % 100 == 80) ? 2 : 3)));
   **H**
   ha,      Hausa,                   nplurals=2; plural=(n != 1);
   haw,     Hawaiian,                nplurals=2; plural=(n != 1);
   he,      Hebrew,                  nplurals=4; plural=((n == 1) ? 0 : ((n == 2) ? 1 : (((n < 0 || n > 10) && n % 10 == 0) ? 2 : 3)));
   hi,      Hindi,                   nplurals=2; plural=(n > 1);
   hne,     Chhattisgarhi,           nplurals=2; plural=(n != 1);
   hy,      Armenian,                nplurals=2; plural=(n != 1);
   hr,      Croatian,                nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   hsb,     Upper Sorbian,           nplurals=4; plural=((n % 100 == 1) ? 0 : ((n % 100 == 2) ? 1 : ((n % 100 == 3 || n % 100 == 4) ? 2 : 3)));
   hu,      Hungarian,               nplurals=2; plural=(n != 1);
   hy,      Armenian,                nplurals=2; plural=(n > 1);
   **I**
   ia,      Interlingua,             nplurals=2; plural=(n != 1);
   id,      Indonesian,              nplurals=1; plural=0;
   ig,      Igbo,                    nplurals=1; plural=0;
   ii,      Sichuan Yi,              nplurals=1; plural=0;
   in,      Indonesian,              nplurals=1; plural=0;
   is,      Icelandic,               nplurals=2; plural=(n % 10 != 1 || n % 100 == 11);
   it,      Italian,                 nplurals=2; plural=(n != 1);
   iu,      Inuktitut,               nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   iw,      Hebrew,                  nplurals=4; plural=((n == 1) ? 0 : ((n == 2) ? 1 : (((n < 0 || n > 10) && n % 10 == 0) ? 2 : 3)));
   **J**
   ja,      Japanese,                nplurals=1; plural=0;
   jbo,     Lojban,                  nplurals=1; plural=0;
   jgo,     Ngomba,                  nplurals=2; plural=(n != 1);
   ji,      Yiddish,                 nplurals=2; plural=(n != 1);
   jmc,     Machame,                 nplurals=2; plural=(n != 1);
   jv,      Javanese,                nplurals=1; plural=0;
   jw,      Javanese,                nplurals=1; plural=0;
   **K**
   ka,      Georgian,                nplurals=2; plural=(n != 1);
   kab,     Kabyle,                  nplurals=2; plural=(n > 1);
   kaj,     Jju,                     nplurals=2; plural=(n != 1);
   kcg,     Tyap,                    nplurals=2; plural=(n != 1);
   kde,     Makonde,                 nplurals=1; plural=0;
   kea,     Kabuverdianu,            nplurals=1; plural=0;
   kk,      Kazakh,                  nplurals=2; plural=(n != 1);
   kkj,     Kako,                    nplurals=2; plural=(n != 1);
   kl,      Kalaallisut,             nplurals=2; plural=(n != 1);
   km,      Khmer,                   nplurals=1; plural=0;
   kn,      Kannada,                 nplurals=2; plural=(n > 1);
   ko,      Korean,                  nplurals=1; plural=0;
   ks,      Kashmiri,                nplurals=2; plural=(n != 1);
   ksb,     Shambala,                nplurals=2; plural=(n != 1);
   ksh,     Colognian,               nplurals=3; plural=((n == 0) ? 0 : ((n == 1) ? 1 : 2));
   ku,      Kurdish,                 nplurals=2; plural=(n != 1);
   kw,      Cornish,                 nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   ky,      Kyrgyz,                  nplurals=2; plural=(n != 1);
   **L**
   lag,     Langi,                   nplurals=3; plural=((n == 0) ? 0 : ((n == 1) ? 1 : 2));
   lb,      Luxembourgish,           nplurals=2; plural=(n != 1);
   lg,      Ganda,                   nplurals=2; plural=(n != 1);
   lkt,     Lakota,                  nplurals=1; plural=0;
   ln,      Lingala,                 nplurals=2; plural=(n > 1);
   lo,      Lao,                     nplurals=1; plural=0;
   lt,      Lithuanian,              nplurals=3; plural=((n % 10 == 1 && (n % 100 < 11 || n % 100 > 19)) ? 0 : ((n % 10 >= 2 && n % 10 <= 9 && (n % 100 < 11 || n % 100 > 19)) ? 1 : 2));
   lv,      Latvian,                 nplurals=3; plural=((n % 10 == 0 || n % 100 >= 11 && n % 100 <= 19) ? 0 : ((n % 10 == 1 && n % 100 != 11) ? 1 : 2));
   **M**
   mai,     Maithili,                nplurals=2; plural=(n != 1);
   mas,     Masai,                   nplurals=2; plural=(n != 1);
   mfe,     Mauritian Creole,        nplurals=2; plural=(n > 1);
   mg,      Malagasy,                nplurals=2; plural=(n > 1);
   mgo,     Metaʼ,                   nplurals=2; plural=(n != 1);
   mi,      Maori,                   nplurals=2; plural=(n > 1);
   mk,      Macedonian,              nplurals=2; plural=(n % 10 != 1);
   ml,      Malayalam,               nplurals=2; plural=(n != 1);
   mn,      Mongolian,               nplurals=2; plural=(n != 1);
   mni,     Manipuri,                nplurals=2; plural=(n != 1);
   mnk,     Mandinka,                nplurals=3; plural=(n==0 ? 0 : n==1 ? 1 : 2);
   mo,      Moldavian,               nplurals=3; plural=((n == 1) ? 0 : ((n == 0 || n != 1 && n % 100 >= 1 && n % 100 <= 19) ? 1 : 2));
   mr,      Marathi,                 nplurals=2; plural=(n > 1);
   ms,      Malay,                   nplurals=1; plural=0;
   mt,      Maltese,                 nplurals=4; plural=((n == 1) ? 0 : ((n == 0 || n % 100 >= 2 && n % 100 <= 10) ? 1 : ((n % 100 >= 11 && n % 100 <= 19) ? 2 : 3)));
   my,      Burmese,                 nplurals=1; plural=0;
   **N**
   nah,     Nahuatl,                 nplurals=2; plural=(n != 1);
   nap,     Neapolitan,              nplurals=2; plural=(n != 1);
   naq,     Nama,                    nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   nb,      Norwegian Bokmål,        nplurals=2; plural=(n != 1);
   nd,      North Ndebele,           nplurals=2; plural=(n != 1);
   ne,      Nepali,                  nplurals=2; plural=(n != 1);
   nl,      Dutch,                   nplurals=2; plural=(n != 1);
   nl_BE,   Flemish,                 nplurals=2; plural=(n != 1);
   nn,      Norwegian Nynorsk,       nplurals=2; plural=(n != 1);
   nnh,     Ngiemboon,               nplurals=2; plural=(n != 1);
   no,      Norwegian (old code),    nplurals=2; plural=(n != 1);
   nqo,     NʼKo,                    nplurals=1; plural=0;
   nr,      South Ndebele,           nplurals=2; plural=(n != 1);
   nso,     Northern Sotho,          nplurals=2; plural=(n > 1);
   ny,      Nyanja,                  nplurals=2; plural=(n != 1);
   nyn,     Nyankole,                nplurals=2; plural=(n != 1);
   **O**
   oc,      Occitan,                 nplurals=2; plural=(n > 1);
   om,      Oromo,                   nplurals=2; plural=(n != 1);
   or,      Oriya,                   nplurals=2; plural=(n != 1);
   os,      Ossetic,                 nplurals=2; plural=(n != 1);
   **P**
   pa,      Punjabi,                 nplurals=2; plural=(n > 1);
   pap,     Papiamento,              nplurals=2; plural=(n != 1);
   pl,      Polish,                  nplurals=3; plural=((n == 1) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   pms,     Piemontese,              nplurals=2; plural=(n != 1);
   prg,     Prussian,                nplurals=3; plural=((n % 10 == 0 || n % 100 >= 11 && n % 100 <= 19) ? 0 : ((n % 10 == 1 && n % 100 != 11) ? 1 : 2));
   ps,      Pashto,                  nplurals=2; plural=(n != 1);
   pt,      Portuguese,              nplurals=2; plural=(n > 1);
   pt_BR,   Brazilian Portuguese,    nplurals=2; plural=(n > 1);
   pt_PT,   European Portuguese,     nplurals=2; plural=(n != 1);
   **R**
   rm,      Romansh,                 nplurals=2; plural=(n != 1);
   ro,      Romanian,                nplurals=3; plural=((n == 1) ? 0 : ((n == 0 || n != 1 && n % 100 >= 1 && n % 100 <= 19) ? 1 : 2));
   ro_MD,   Moldavian,               nplurals=3; plural=((n == 1) ? 0 : ((n == 0 || n != 1 && n % 100 >= 1 && n % 100 <= 19) ? 1 : 2));
   rof,     Rombo,                   nplurals=2; plural=(n != 1);
   ru,      Russian,                 nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   rw,      Kinyarwanda,             nplurals=2; plural=(n != 1);
   rwk,     Rwa,                     nplurals=2; plural=(n != 1);
   **S**
   sah,     Sakha,                   nplurals=1; plural=0;
   saq,     Samburu,                 nplurals=2; plural=(n != 1);
   sat,     Santali,                 nplurals=2; plural=(n != 1);
   sco,     Scots,                   nplurals=2; plural=(n != 1);
   sd,      Sindhi,                  nplurals=2; plural=(n != 1);
   se,      Northern Sami,           nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   seh,     Sena,                    nplurals=2; plural=(n != 1);
   ses,     Koyraboro Senni,         nplurals=1; plural=0;
   sg,      Sango,                   nplurals=1; plural=0;
   sh,      Serbo-Croatian,          nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   shi,     Tachelhit,               nplurals=3; plural=((n == 0 || n == 1) ? 0 : ((n >= 2 && n <= 10) ? 1 : 2));
   si,      Sinhala,                 nplurals=2; plural=(n > 1);
   sk,      Slovak,                  nplurals=3; plural=((n == 1) ? 0 : ((n >= 2 && n <= 4) ? 1 : 2));
   sl,      Slovenian,               nplurals=4; plural=((n % 100 == 1) ? 0 : ((n % 100 == 2) ? 1 : ((n % 100 == 3 || n % 100 == 4) ? 2 : 3)));
   sma,     Southern Sami,           nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   smi,     Sami,                    nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   smj,     Lule Sami,               nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   smn,     Inari Sami,              nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   sms,     Skolt Sami,              nplurals=3; plural=((n == 1) ? 0 : ((n == 2) ? 1 : 2));
   sn,      Shona,                   nplurals=2; plural=(n != 1);
   so,      Somali,                  nplurals=2; plural=(n != 1);
   son,     Songhay,                 nplurals=2; plural=(n != 1);
   sq,      Albanian,                nplurals=2; plural=(n != 1);
   sr,      Serbian,                 nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   ss,      Swati,                   nplurals=2; plural=(n != 1);
   ssy,     Saho,                    nplurals=2; plural=(n != 1);
   st,      Southern Sotho,          nplurals=2; plural=(n != 1);
   su,      Sundanese,               nplurals=1; plural=0;
   sv,      Swedish,                 nplurals=2; plural=(n != 1);
   sw,      Swahili,                 nplurals=2; plural=(n != 1);
   syr,     Syriac,                  nplurals=2; plural=(n != 1);
   **T**
   ta,      Tamil,                   nplurals=2; plural=(n != 1);
   te,      Telugu,                  nplurals=2; plural=(n != 1);
   teo,     Teso,                    nplurals=2; plural=(n != 1);
   tg,      Tajik,                   nplurals=2; plural=(n > 1);
   th,      Thai,                    nplurals=1; plural=0;
   ti,      Tigrinya,                nplurals=2; plural=(n > 1);
   tig,     Tigre,                   nplurals=2; plural=(n != 1);
   tk,      Turkmen,                 nplurals=2; plural=(n != 1);
   tl,      Tagalog,                 nplurals=2; plural=(n != 1 && n != 2 && n != 3 && (n % 10 == 4 || n % 10 == 6 || n % 10 == 9));
   tn,      Tswana,                  nplurals=2; plural=(n != 1);
   to,      Tongan,                  nplurals=1; plural=0;
   tr,      Turkish,                 nplurals=2; plural=(n != 1);
   ts,      Tsonga,                  nplurals=2; plural=(n != 1);
   tt,      Tatar,                   nplurals=1; plural=0;
   tzm,     Central Atlas Tamazight, nplurals=2; plural=(n >= 2 && (n < 11 || n > 99));
   **U**
   ug,      Uyghur,                  nplurals=2; plural=(n != 1);
   uk,      Ukrainian,               nplurals=3; plural=((n % 10 == 1 && n % 100 != 11) ? 0 : ((n % 10 >= 2 && n % 10 <= 4 && (n % 100 < 12 || n % 100 > 14)) ? 1 : 2));
   ur,      Urdu,                    nplurals=2; plural=(n != 1);
   uz,      Uzbek,                   nplurals=2; plural=(n != 1);
   **V**
   ve,      Venda,                   nplurals=2; plural=(n != 1);
   vi,      Vietnamese,              nplurals=1; plural=0;
   vo,      Volapük,                 nplurals=2; plural=(n != 1);
   vun,     Vunjo,                   nplurals=2; plural=(n != 1);
   **W**
   wa,      Walloon,                 nplurals=2; plural=(n > 1);
   wae,     Walser,                  nplurals=2; plural=(n != 1);
   wo,      Wolof,                   nplurals=1; plural=0;
   **X**
   xh,      Xhosa,                   nplurals=2; plural=(n != 1);
   xog,     Soga,                    nplurals=2; plural=(n != 1);
   **Y**
   yi,      Yiddish,                 nplurals=2; plural=(n != 1);
   yo,      Yoruba,                  nplurals=1; plural=0;
   **Z**
   zh,      Chinese [#f1]_,          nplurals=1; plural=0;
   zh,      Chinese [#f2]_,          nplurals=2; plural=(n > 1);
   zh_Hans, Simplified Chinese,      nplurals=1; plural=0;
   zh_Hant, Traditional Chinese,     nplurals=1; plural=0;
   zu,      Zulu,                    nplurals=2; plural=(n > 1);

.. rubric:: Footnotes

.. [#f1] zh means all districts and all variants of Chinese, such as zh_CN,
   zh_HK, zh_TW and so on.
.. [#f2] In rare cases where plural form introduces difference in personal
   pronoun (such as her vs. they, we vs. I), the plural form is different.

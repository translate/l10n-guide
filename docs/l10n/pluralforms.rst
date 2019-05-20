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

.. note:: `Unicode CLDR <http://cldr.unicode.org/>`_ also collects `plural
   information for many languages
   <http://www.unicode.org/cldr/data/charts/supplemental/language_plural_rules.html>`_
   (also in `XML form
   <http://unicode.org/cldr/trac/browser/trunk/common/supplemental/plurals.xml>`_).

.. _pluralforms#list:

.. We should build this automatically from the data that we have in the
   Translate Toolkit.

.. csv-table::
   :header-rows: 1
   :widths: 5 20 75

   ISO,   English name,          Plurals header in .po files
   **A**
   ach,   Acholi,                nplurals=2; plural=(n > 1);
   af,    Afrikaans,             nplurals=2; plural=(n != 1);
   ak,    Akan,                  nplurals=2; plural=(n > 1);
   am,    Amharic,               nplurals=2; plural=(n > 1);
   an,    Aragonese,             nplurals=2; plural=(n != 1);
   anp,   Angika,                nplurals=2; plural=(n != 1);
   ar,    Arabic [#f1]_,         nplurals=6; plural=(n==0 ? 0 : n==1 ? 1 : n==2 ? 2 : n%100>=3 && n%100<=10 ? 3 : n%100>=11 ? 4 : 5);
   arn,   Mapudungun,            nplurals=2; plural=(n > 1);
   as,    Assamese,              nplurals=2; plural=(n != 1);
   ast,   Asturian,              nplurals=2; plural=(n != 1);
   ay,    Aymará,                nplurals=1; plural=0;
   az,    Azerbaijani,           nplurals=2; plural=(n != 1);
   **B**
   be,    Belarusian,            nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   bg,    Bulgarian,             nplurals=2; plural=(n != 1);
   bn,    Bengali,               nplurals=2; plural=(n != 1);
   bo,    Tibetan,               nplurals=1; plural=0;
   br,    Breton,                nplurals=2; plural=(n > 1);
   brx,   Bodo,                  nplurals=2; plural=(n != 1);
   bs,    Bosnian,               nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   **C**
   ca,    Catalan,               nplurals=2; plural=(n != 1);
   cgg,   Chiga,                 nplurals=1; plural=0;
   cs,    Czech,                 nplurals=3; plural=(n==1) ? 0 : (n>=2 && n<=4) ? 1 : 2;
   csb,   Kashubian,             nplurals=3; plural=(n==1) ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2;
   cy,    Welsh,                 nplurals=4; plural=(n==1) ? 0 : (n==2) ? 1 : (n != 8 && n != 11) ? 2 : 3;
   **D**
   da,    Danish,                nplurals=2; plural=(n != 1);
   de,    German,                nplurals=2; plural=(n != 1);
   doi,   Dogri,                 nplurals=2; plural=(n != 1);
   dz,    Dzongkha,              nplurals=1; plural=0;
   **E**
   el,    Greek,                 nplurals=2; plural=(n != 1);
   en,    English,               nplurals=2; plural=(n != 1);
   eo,    Esperanto,             nplurals=2; plural=(n != 1);
   es,    Spanish,               nplurals=2; plural=(n != 1);
   es_AR, Argentinean Spanish,   nplurals=2; plural=(n != 1);
   et,    Estonian,              nplurals=2; plural=(n != 1);
   eu,    Basque,                nplurals=2; plural=(n != 1);
   **F**
   fa,    Persian,               nplurals=2; plural=(n > 1);
   ff,    Fulah,                 nplurals=2; plural=(n != 1);
   fi,    Finnish,               nplurals=2; plural=(n != 1);
   fil,   Filipino,              nplurals=2; plural=(n > 1);
   fo,    Faroese,               nplurals=2; plural=(n != 1);
   fr,    French,                nplurals=2; plural=(n > 1);
   fur,   Friulian,              nplurals=2; plural=(n != 1);
   fy,    Frisian,               nplurals=2; plural=(n != 1);
   **G**
   ga,    Irish,                 nplurals=5; plural=n==1 ? 0 : n==2 ? 1 : (n>2 && n<7) ? 2 :(n>6 && n<11) ? 3 : 4;
   gd,    Scottish Gaelic,       nplurals=4; plural=(n==1 || n==11) ? 0 : (n==2 || n==12) ? 1 : (n > 2 && n < 20) ? 2 : 3;
   gl,    Galician,              nplurals=2; plural=(n != 1);
   gu,    Gujarati,              nplurals=2; plural=(n != 1);
   gun,   Gun,                   nplurals=2; plural=(n > 1);
   **H**
   ha,    Hausa,                 nplurals=2; plural=(n != 1);
   he,    Hebrew,                nplurals=2; plural=(n != 1);
   hi,    Hindi,                 nplurals=2; plural=(n != 1);
   hne,   Chhattisgarhi,         nplurals=2; plural=(n != 1);
   hr,    Croatian,              nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   hu,    Hungarian,             nplurals=2; plural=(n != 1);
   hy,    Armenian,              nplurals=2; plural=(n != 1);
   **I**
   ia,    Interlingua,           nplurals=2; plural=(n != 1);
   id,    Indonesian,            nplurals=1; plural=0;
   is,    Icelandic,             nplurals=2; plural=(n%10!=1 || n%100==11);
   it,    Italian,               nplurals=2; plural=(n != 1);
   **J**
   ja,    Japanese,              nplurals=1; plural=0;
   jbo,   Lojban,                nplurals=1; plural=0;
   jv,    Javanese,              nplurals=2; plural=(n != 0);
   **K**
   ka,    Georgian,              nplurals=1; plural=0;
   kk,    Kazakh,                nplurals=2; plural=(n != 1);
   kl,    Greenlandic,           nplurals=2; plural=(n != 1);
   km,    Khmer,                 nplurals=1; plural=0;
   kn,    Kannada,               nplurals=2; plural=(n != 1);
   ko,    Korean,                nplurals=1; plural=0;
   ku,    Kurdish,               nplurals=2; plural=(n != 1);
   kw,    Cornish,               nplurals=4; plural=(n==1) ? 0 : (n==2) ? 1 : (n == 3) ? 2 : 3;
   ky,    Kyrgyz,                nplurals=2; plural=(n != 1);
   **L**
   lb,    Letzeburgesch,         nplurals=2; plural=(n != 1);
   ln,    Lingala,               nplurals=2; plural=(n > 1);
   lo,    Lao,                   nplurals=1; plural=0;
   lt,    Lithuanian,            nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && (n%100<10 || n%100>=20) ? 1 : 2);
   lv,    Latvian,               nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n != 0 ? 1 : 2);
   **M**
   mai,   Maithili,              nplurals=2; plural=(n != 1);
   me,    Montenegro,            nplurals=3; plural=n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2;
   mfe,   Mauritian Creole,      nplurals=2; plural=(n > 1);
   mg,    Malagasy,              nplurals=2; plural=(n > 1);
   mi,    Maori,                 nplurals=2; plural=(n > 1);
   mk,    Macedonian,            nplurals=2; plural= n==1 || n%10==1 ? 0 : 1; *Can't be correct needs a 2 somewhere*
   ml,    Malayalam,             nplurals=2; plural=(n != 1);
   mn,    Mongolian,             nplurals=2; plural=(n != 1);
   mni,   Manipuri,              nplurals=2; plural=(n != 1);
   mnk,   Mandinka,              nplurals=3; plural=(n==0 ? 0 : n==1 ? 1 : 2);
   mr,    Marathi,               nplurals=2; plural=(n != 1);
   ms,    Malay,                 nplurals=1; plural=0;
   mt,    Maltese,               nplurals=4; plural=(n==1 ? 0 : n==0 || ( n%100>1 && n%100<11) ? 1 : (n%100>10 && n%100<20 ) ? 2 : 3);
   my,    Burmese,               nplurals=1; plural=0;
   **N**
   nah,   Nahuatl,               nplurals=2; plural=(n != 1);
   nap,   Neapolitan,            nplurals=2; plural=(n != 1);
   nb,    Norwegian Bokmal,      nplurals=2; plural=(n != 1);
   ne,    Nepali,                nplurals=2; plural=(n != 1);
   nl,    Dutch,                 nplurals=2; plural=(n != 1);
   nn,    Norwegian Nynorsk,     nplurals=2; plural=(n != 1);
   no,    Norwegian (old code),  nplurals=2; plural=(n != 1);
   nso,   Northern Sotho,        nplurals=2; plural=(n != 1);
   **O**
   oc,    Occitan,               nplurals=2; plural=(n > 1);
   or,    Oriya,                 nplurals=2; plural=(n != 1);
   **P**
   pa,    Punjabi,               nplurals=2; plural=(n != 1);
   pap,   Papiamento,            nplurals=2; plural=(n != 1);
   pl,    Polish,                nplurals=3; plural=(n==1 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   pms,   Piemontese,            nplurals=2; plural=(n != 1);
   ps,    Pashto,                nplurals=2; plural=(n != 1);
   pt,    Portuguese,            nplurals=2; plural=(n != 1);
   pt_BR, Brazilian Portuguese,  nplurals=2; plural=(n > 1);
   **R**
   rm,    Romansh,               nplurals=2; plural=(n != 1);
   ro,    Romanian,              nplurals=3; plural=(n==1 ? 0 : (n==0 || (n%100 > 0 && n%100 < 20)) ? 1 : 2);
   ru,    Russian,               nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   rw,    Kinyarwanda,           nplurals=2; plural=(n != 1);
   **S**
   sah,   Yakut,                 nplurals=1; plural=0;
   sat,   Santali,               nplurals=2; plural=(n != 1);
   sco,   Scots,                 nplurals=2; plural=(n != 1);
   sd,    Sindhi,                nplurals=2; plural=(n != 1);
   se,    Northern Sami,         nplurals=2; plural=(n != 1);
   si,    Sinhala,               nplurals=2; plural=(n != 1);
   sk,    Slovak,                nplurals=3; plural=(n==1) ? 0 : (n>=2 && n<=4) ? 1 : 2;
   sl,    Slovenian,             nplurals=4; plural=(n%100==1 ? 0 : n%100==2 ? 1 : n%100==3 || n%100==4 ? 2 : 3);
   so,    Somali,                nplurals=2; plural=(n != 1);
   son,   Songhay,               nplurals=2; plural=(n != 1);
   sq,    Albanian,              nplurals=2; plural=(n != 1);
   sr,    Serbian,               nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   su,    Sundanese,             nplurals=1; plural=0;
   sv,    Swedish,               nplurals=2; plural=(n != 1);
   sw,    Swahili,               nplurals=2; plural=(n != 1);
   **T**
   ta,    Tamil,                 nplurals=2; plural=(n != 1);
   te,    Telugu,                nplurals=2; plural=(n != 1);
   tg,    Tajik,                 nplurals=2; plural=(n > 1);
   th,    Thai,                  nplurals=1; plural=0;
   ti,    Tigrinya,              nplurals=2; plural=(n > 1);
   tk,    Turkmen,               nplurals=2; plural=(n != 1);
   tr,    Turkish,               nplurals=2; plural=(n > 1);
   tt,    Tatar,                 nplurals=2; plural=(n > 1);
   **U**
   ug,    Uyghur,                nplurals=1; plural=0;
   uk,    Ukrainian,             nplurals=3; plural=(n%10==1 && n%100!=11 ? 0 : n%10>=2 && n%10<=4 && (n%100<10 || n%100>=20) ? 1 : 2);
   ur,    Urdu,                  nplurals=2; plural=(n != 1);
   uz,    Uzbek,                 nplurals=2; plural=(n > 1);
   **V**
   vi,    Vietnamese,            nplurals=1; plural=0;
   **W**
   wa,    Walloon,               nplurals=2; plural=(n > 1);
   wo,    Wolof,                 nplurals=1; plural=0;
   **Y**
   yo,    Yoruba,                nplurals=2; plural=(n != 1);
   **Z**
   zh,    Chinese [#f2]_,        nplurals=1; plural=0;
   zh,    Chinese [#f3]_,        nplurals=2; plural=(n > 1);

.. rubric:: Footnotes

.. [#f1]  http://wiki.arabeyes.org/Plural_Forms
.. [#f2] zh means all districts and all variants of Chinese, such as zh_CN,
   zh_HK, zh_TW and so on.
.. [#f3] In rare cases where plural form introduces difference in personal
   pronoun (such as her vs. they, we vs. I), the plural form is different.

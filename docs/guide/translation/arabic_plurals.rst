
.. note::

    This page is now dated. Please see `the page at Arabeyes <http://wiki.arabeyes.org/%D8%B5%D9%8A%D8%BA_%D8%A7%D9%84%D9%85%D8%B9%D8%AF%D9%88%D8%AF>`_ (`in English <http://wiki.arabeyes.org/Plural_Forms>`_).

xxx

.. _../pages/guide/translation/arabic_plurals#arabic_plurals_صيغ_الجمع_في_العربية:

Arabic Plurals (صيغ الجمع في العربية)
*************************************

Six plural forms are used:

  * Plural Form 0: (ويشمل الرقم 0)

0 books : لا كتاب

The translation may change depending on the context, therefore using لا is not an obligation.

  * Plural Form 1: (ويشمل الرقم 1)

1 book : كتاب واحد

  * Plural Form 2: (ويشمل الرقم اثنان)

2 books : كتابان

  * Plural Form 3: (ويشمل الأعداد من 3-10)

%d books: كتب %d

**Rule:**

 تمييز العدد من 3 إلى 10 يكون جمعا مجرورا . ويكون جمع قلة فيقال ثلاثة أشهر لا ثلاثة شهور

  * Plural Form 4: (ويشمل الأعداد من 11-99)

%d books : كتابا %d

**Rule:**

 تمييز العدد من 11 إلى 99 يكون مفردا منصوبا. ومثاله أحد عشر كوكبا، فانبجست منه اثنتا عشرة عينا

  * Plural Form 5: (ويشمل الأعداد من 100 فأكثر)

%d books : كتاب %d

**Rule:**

 تمييز المئة والألف ومضاعفاتها يكون مفردا مجرورا وإذا قرأ العدد من اليمين إلى اليسار يكون العدد منتهيا بمئة أو ألف أو ألف ألف، وبالتالي تبقى القاعدة صالحة لكل الأعداد الأكبر من 99 .

.. _../pages/guide/translation/arabic_plurals#formula_الصيغة:

Formula (الصيغة)
================

``nplurals=6; plural=n 
XXX
---

XXX
^^^

.. _../pages/guide/translation/arabic_plurals#0__0_:_n:

0 ? 0 : n
""""""""" 1 ? 1 : n == 2 ? 2 : n >= 3 && n <= 10 ? 3 : n >= 11 && n <= 99 ? 4 : 5;``

.. _../pages/guide/mozilla#mozilla_product_localisation:

Mozilla Product Localisation
****************************

`Mozilla <http://www.mozilla.org>`_ is the organisation credited with giving
the world the Firefox web browser, Thunderbird e-mail client and `many more
<http://www.mozilla.org/projects>`_. Most of the Mozilla products can be
localised and this page (and pages linked to) aims to be a comprehensive
resource of information about this process.

This page gives a broad overview of the localisation processes involved when
localising Mozilla products using PO files, the `Translate Toolkit
<http://toolkit.translatehouse.org>`_ and other PO based tool such as `Pootle
<http://pootle.translatehouse.org>`_ and `Virtaal
<http://virtaal.translatehouse.org>`_.

Product-specific information are on the projects' own pages:

* :doc:`firefox`
* :doc:`thunderbird`

.. _../pages/guide/mozilla#localising_mozilla_on_pootle:

Localising Mozilla on Pootle
============================

FIXME work in progress, we'll cleanup and retire the other information and the
Pootle way will be the only one that we talk about

So you want to translate Firefox into your language.  To start is simple, to
complete is a bit harder.

Before you begin lets be realistic about how much effort is required.  If you
can translate 1,500 words a day, like most professional translators, you can
expect to complete Firefox in 20 days if you work fulltime.  But you will still
need to review the translations and perform in product review.  So this is a
lot of work.

We're helping to reduce that effort.  While you translate we'll build the files
needed by Firefox for you as we do for our South African and African languages.
This takes a lot off your shoulders and you can happily begin translating
without any knowledge of what happens at Mozilla, the files formats, etc.

.. _../pages/guide/mozilla#what_do_i_need_to_do_to_get_started:

What do I need to do to get started
-----------------------------------

#. Check that nobody else is doing your language.  If they are, please join
   them.  If not we're happy to host your translations.
#. Create an account on Pootle.
#. Ask us to add your language.  We'll enable your language, give you rights to
   enable others and leave you to translate.
#. Begin translating the user1 component (the others look shorter and easier
   but please don't waste your time)

.. _../pages/guide/mozilla#what_should_i_translate_next:

What should I translate next?
-----------------------------

We have developed a number of modules that allow you to focus on the most
important strings first.

.. _../pages/guide/mozilla#how_do_i_get_my_translations_into_firefox:

How do I get my translations into Firefox
-----------------------------------------

#. First, complete the key translations needed for Firefox
#. Apply for your language to be included
#. You will need to respond to a number of bugs that need fiing for your
   language.  We can help you here, for most minority languages taking American
   English defaults is the correct approach.

.. _../pages/guide/mozilla#translation_file_formats_used_by_mozilla:

Translation file formats used by Mozilla
========================================
Mozilla products use monolingual translation formats and is further discussed
:doc:`here <monolingual>`.

.. _../pages/guide/mozilla#localisation_work-flow:

Localisation work-flow
======================
The `Mozilla L10n <https://wiki.mozilla.org/l10n/home_page>`_ project page
contains the rest of the information needed to start a new localisation or join
an existing localisation team.

- **Preparing translation files:** POT files for any string frozen version of
  Firefox or Thunderbird can be downloaded from the `Mozilla l10n server
  <http://l10n.mozilla.org/pootle/pot>`_ or you can :ref:`create it
  <toolkit:creating_mozilla_pot_files>` yourself. You can then create updated
  PO files with :ref:`pomigrate2 <toolkit:pomigrate2>`. :ref:`These scripts
  <toolkit:mozilla_l10n_scripts>` can help to keep a repository of Mozilla PO
  files up to date and ready for translation.
- **Translating the PO files:** The PO files can now be translated using your
  favourite CAT tool, like `Pootle <http://pootle.translatehouse.org>`_ for
  sharing the workload in a team or `Virtaal
  <http://virtaal.translatehouse.org>`_ to translate off-line.
- **Check for product specific issues:** The :doc:`firefox` and
  :doc:`thunderbird` pages describe some of these issues.
- **QA and bug checking:** You need to test your build.  Probably the best
  preventative step you can take it to run :ref:`pofilter
  <toolkit:using_pofilter>`'s *variable*, *accelerator* and *escapes* tests.
  Errors that these tests pick up are all capable of introducing potential
  breakage that is hard to trace.
- **Preparing translation files for uploading:** The PO files now need to be
  converted back to the original monolingual files before they can be committed
  to the Mozilla repositories. The :ref:`po2moz <toolkit:po2moz>` tool can be
  used to recreate the original file structure using the new translations.

.. _../pages/guide/mozilla#useful_odds_and_ends:

Useful odds and ends
====================

.. _../pages/guide/mozilla#dialogue_sizes:

Dialogue Sizes
--------------
Various dialogues are sized within the XUL work.  Often they have entries in
the DTD which allow you to change the size of the dialogue.  It is a very
time-consuming process, but hopefully the `bookmarklet and instructions
<http://www.axel-hecht.de/blog/archives/000233.html>`_ created by Axel Hecht
will help you quickly get the correct size to enter into your final files.

For reference:

* Put the following text into the location field of a new bookmark (therefore
  won't work with Thunderbird): (Make sure that you are not putting in smart
  (round) quotes produced by the wiki software)

  .. code-block:: javascript
  
      javascript:(function(){var p=2;var cs=window.getComputedStyle(document.documentElement,null);var fs=cs.getPropertyCSSValue('font-size').getFloatValue(5);var w=cs.getPropertyCSSValue('width').getFloatValue(5);var h=cs.getPropertyCSSValue('height').getFloatValue(5);prompt('Dialog size:', 'width: '+Math.ceil(w/fs*p)/p+'; height: '+Math.ceil(h/fs*p)/p+';');})();

* Browse to the correct XUL file with Firefox, for example
  ``chrome://browser/components/preferences/preferences.xul``.
* Choose your bookmark with the JavaScript and a message box displays the width
  and height.

.. _../pages/guide/mozilla#requirements_for_official_build:

Requirements for official build
-------------------------------

* See https://wiki.mozilla.org/L10n:Becoming_an_Official_Localization
* Translate the `start snippets <http://www.mozilla.org/start-snippets/>`_

.. _../pages/guide/mozilla#locale_switcher:

Locale Switcher
---------------
This `multi locale switcher
<http://www.saintpatrickdc.org/bsmedberg/locale-switcher/>`_ is best for use in
cases where you will have more than one language to install. Even with two it
is much cleaner then other locale switchers available.

.. _../pages/guide/mozilla#releasing:

Releasing
---------
There are some requirements which stem from the trademark policy. Mozilla
products can be released as either an official build or a community release.

.. _../pages/guide/mozilla#links:

Links
-----
* `Mozilla L10n Home <https://wiki.mozilla.org/l10n/home_page>`_
* `Localisation policy/trademarks, etc
  <http://www.mozilla.org/foundation/trademarks/l10n-policy.html>`_ (`2
  <http://www.mozilla.org/foundation/licensing.html>`_)
* :ref:`Scripts used by Translate.org.za <toolkit:mozilla_l10n_scripts>`

.. _../pages/guide/mozilla#deprecated_information:

Deprecated information
----------------------
.. toctree::
   :maxdepth: 1
   :hidden:

   mozillacvs

* :doc:`Mozilla CVS <mozillacvs>`: Information about localising older versions
  of Mozilla products that used CVS.
* :ref:`Migrating Mozilla translations to Firefox
  <toolkit:migrating_to_firefox>`: This quick-start shows you how to migrate
  your existing translations of the Mozilla suite to the Firefox web-browser.
  The same instructions can be used to migrate Thunderbird.


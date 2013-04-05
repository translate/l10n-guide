
.. _../pages/guide/foss_fonts#free_and_open_source_fonts:

Free and Open Source Fonts
**************************

If your language doesn't use traditional Latin characters then most likely you will need to look at fonts.
Here we try to list fonts that you can actually change to add your characters.

.. _../pages/guide/foss_fonts#resources:

Resources
=========

  * `Optimal Use of Fonts on Linux <http://avi.alkalay.net/linux/docs/font-howto/>`_
  * `Ed Trager's Unicode Font Guide For Free/Libre Open Source Operating Systems <http://eyegene.ophthy.med.umich.edu/unicode/fontguide/>`_
  * The `Wine <http://www.winehq.org>`_ projects `discussion on creating missing Windows fonts <http://wiki.winehq.org/CreateFonts>`_
  * `Scribus page on fonts <http://www.scribus.org.uk/modules.php?op=modload&name=Web_Links&file=index&req=viewlink&cid=3>`_
  * `FontForge <http://fontforge.sourceforge.net/>`_ --- Free font editing and creation tool  
  * Indrek Hein's `Letter Database <http://www.eki.ee/letter/>`_ --- what special characters are needed by your/a language, their Unicode codes, etc
  * Fontconfig `Orthographies <http://cgit.freedesktop.org/fontconfig/tree/fc-lang>`_ --- these fc-lang files contain the list of characters needed by various languages and are used to better guess which font to use to render a document.
  * ` <http://www.travelphrases.info/fonts.html>`_ --- want to see the scripts of various languages and their fonts, plus links to both free and proprietary fonts.
  * Troubleshooting
    * `Unix Fonts and AbiWord <http://www.abisource.com/help/en-US/problems/problemsfonts.html>`_
    * OpenOffice.org's `Font Trouble Shooting Guide <http://www.openoffice.org/FAQs/fontguide.html>`_
  * Freedesktop.org's list of:
    * `Open Source and other fonts <http://freedesktop.org/wiki/Software_2fFonts>`_
    * `BSD and GPLd <http://xorg.freedesktop.org/wiki/FreeFonts>`_ fonts --- this covers many non-Latin fonts
  * `A survey of free font licenses <http://trends.newsforge.com/article.pl?sid=06/02/22/1821200>`_ (NewsForge article)

.. _../pages/guide/foss_fonts#font_list:

Font List
=========

We probably need to start classifiying this list: decrotive, bitmap, etc.

  * `Bitsream Vera <http://www.gnome.org/fonts/>`_ (`2 <http://www.bitstream.com/font_rendering/products/dev_fonts/vera.html>`_) font -- you can't change this one see DejaVu if you want to add your langauges characters
  * `DejaVu <http://dejavu.sourceforge.net/wiki/index.php/Main_Page>`_ -- if you have to extend Bitstream Vera then do it in this font.
  * Greenville --- Tahoma replacement (`comparison <http://www.winehq.com/hypermail/wine-devel/2004/09/att-0601/01-Comparison_6_8_10_12_13.png>`_) --- seems to be vapourware
  * :doc:`URW <ftp///ftp.gnome.ru/fonts/urw/release/>` --- the 35 standard PostScript(TM) fonts, donated under the GPL by URW++ Design and Development GmbH.
  * `X.org's list of Open Source fonts <http://www.freedesktop.org/wiki/Software_2fFonts>`_
  * `Free UCS Outline Fonts <http://www.nongnu.org/freefont/>`_ --- This project aims to provide a set of free outline (PostScript Type0, TrueType, OpenType...) fonts covering the ISO 10646/Unicode UCS (Universal Character Set).
  * `Computer Modern Unicode Fonts <http://canopus.iacp.dvo.ru/~panov/cm-unicode/>`_
  * `UCS bitmap fonts <http://www.cl.cam.ac.uk/~mgk25/ucs-fonts.html>`_
  * `Wine Projects fonts <http://cvs.winehq.com/cvsweb/wine/fonts/>`_ replacements for Windows courier, marlett, sans serif and system
  * `MgOpen <http://www.ellak.gr/fonts/mgopen/>`_ fonts cover Greek but also Latin characters and are licensed in the same way as Bitstream Vera ie you can create derivatives if you use another name.  They also mention that you can try to get your glyphs accepted into the main font which seems like a good option, otherwise you would need to start an effort similar to DejaVu
  * `Matt Chisholm's <http://www.theory.org/~strthrwr/fonts/free/>`_ free decorative fonts (GPLd)
  * `Dark Garden <http://darkgarden.sourceforge.net/>`_ decorative font
  * `Artwiz <http://artwizaleczapka.sourceforge.net/>`_ bitmap fonts
  * `Libertine <http://linuxlibertine.sourceforge.net/>`_ fonts.  Regular, italic, bold and small caps.  Regular has very good latin coverage the others are still in progress.
  * `John Stracke's <http://www.thibault.org/fonts/>`_ decorative fonts
  * Some bitmap fonts on the `Yudit <http://www.yudit.org/download/fonts/bitmap/>`_ site.
  * `Junicode <http://www.engl.virginia.edu/OE/junicode/junicode.html>`_ a font for medievalists.  This has pretty good general latin coverage.

.. _../pages/guide/foss_fonts#determining_font_coverage:

Determining Font Coverage
=========================

What characters are included in a font?  This is often hard to work out and tedious if you have to type and check characters.  Its easier to let fontforge do the work for you.  Here are the steps to be followed:

  - Open the font file(s): TTF, etc using fontforge
  - Save as a fontforge .sfd file
  - Use status.pl from the DejaVu project to create a coverage file

This example creates a coverage file for Micrsoft's Arial Unicode font:

::

    $ fontforge ARIALUNI.TTF # File Save As... and make sure you save an SFD file
    $ touch ArialUnicodeMS.status.txt
    $ ./status.pl original ArialUnicodeMS.status.txt ArialUnicodeMS.sfd  >> ArialUnicodeMS.status.txt.new
    $ vim ArialUnicodeMS.status.txt.new # to view the coverage

.. _../pages/guide/foss_fonts#coverage_--_a_future_hack:

Coverage -- a future hack
-------------------------

Ideally you need a small app that can output coverage or more ideally if fed a font or font directory plus a list of required code points it will return a list of fonts that can satisfy the requirements.  It should run on either Windows or Linux, be able to find the system font directory by default or be supplied with a directory or font file.  It must be able to output all code points covered or return a coverage percentage if a list of required code points is supplied.

The following links could prove usefull in building such an app:

  * MSDN `GetFontUnicodeRanges <http://msdn.microsoft.com/library/default.asp?url=/library/en-us/gdi/fontext_2alv.asp>`_, `GLYPHSET <http://msdn.microsoft.com/library/default.asp?url=/library/en-us/gdi/fontext_43ua.asp>`_ and `WCRANGE <http://msdn.microsoft.com/library/default.asp?url=/library/en-us/gdi/fontext_6cmq.asp>`_
  * A FreeType test that seems to test coverage: http://www.scipy.org/mailinglists/mailman?fn=scipy-cvs/2003-November/002280.html
  * `FontTools <http://fonttools.cvs.sourceforge.net/fonttools/fonttools/>`_
  * `TTFQuery <http://ttfquery.cvs.sourceforge.net/ttfquery/ttfquery/>`_
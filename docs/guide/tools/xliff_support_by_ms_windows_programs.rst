

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#xliff_report_--_1_october_2007:

XLIFF report -- 1 October 2007
==============================

(investigation by Samuel Murray)

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#general_overview:

General overview
----------------

I've investigated some of the programs currently capable of exporting/importing and translating XLIFF files, and here are my findings.

  * Some localisation programs like Sisulizer, Catalyst and appTranslator can export to XLIFF, and import it again, but I get the impression that these are vendor-specific dialects of XLIFF which would be dangerous to roundtrip via the Translate-toolkit.  For example, roundtripping an appTranslator XLIFF file loses a lot of information.

  * Some CMSes claim to export/import their content in XLIFF.  Drupal is one, but I haven't been able to get my hands on exported XLIFF from it.

  * Some CAT (machine aided human translation) tools use XLIFF as their internal format.  Examples are a concept version of OmegaT called OmegaT2, Cafetran and Transolution.  I haven't been able to these programs working to see what their XLIFF formats look like.

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#sdl_trados_2007:

SDL Trados 2007
---------------

  * You can use Trados to translate Translate-toolkit's XLIFF files
  * Trados doesn't have a real XLIFF filter; it treats XLIFF as XML, but it is smart enough to protect the source text
  * The file must be sourcecopied (you can do that using msgen)
  * To translate, simply open the XLIFF file in TagEditor.

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#omegat_2.1.1:

OmegaT 2.1.1
------------

  * OmegaT doesn't have a real XLIFF filter; it simply treats XLIFF as XML
  * You can probably use OmegaT to translate Translate-toolkit's XLIFF files
  * The file must be sourcecopied (you can do that using msgen)
  * The file extension must be XLF
  * Previously, OmegaT saved XML files with LF even if the source file is CRLF (not sure if it still does that).

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#sdlx_build_7014:

SDLX (build 7014)
-----------------

  * SDLX doesn't seem to have a real XLIFF filter; it converts XLIFF to its own ITD format
  * You can use SDLX to translate Translate-toolkit's XLIFF files (but see warning)
  * The file extension must be XLF

**Warning:** Empty target tags in SDLX will be displayed as <0/>, and these must be deleted before saving as XLIFF again, otherwise they are included in the XLIFF file.  For this reason I'm not sure how SDLX will handle more complex XLIFF files.  Also note that SDLX overwrites the original XLIFF file without asking.

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#dvx_dejavu_version_4_aka_version_x:

DVX (DejaVu version 4 aka version 'X')
--------------------------------------

  * DVX doesn't have a real XLIFF filter; it treats XLIFF as XML, but you need to create the filter yourself using the particular XLIFF DTD and a filter creation utility inside DVX.
  * I think you can use DVX to translate Translate-toolkit's XLIFF files (untested)
  * The file must be sourcecopied (you can do that using msgen)

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#heartsome_xliff_editor_6.2-10_build_7d7-3-1b:

Heartsome XLIFF Editor 6.2-10 Build 7D7-3-1B
--------------------------------------------

  * You can use Heartsome XLIFF Editor to translate Translate-toolkit's XLIFF files
  * It saves the file with LF line endings, even if the original file had CRLF line endings.
  * It adds deprecated prop-group tags, but those don't affect the Translate-toolkit

.. _../pages/guide/tools/xliff_support_by_ms_windows_programs#open_language_tools_1.2.7:

Open Language Tools 1.2.7
-------------------------

  * OLT doesn't recognise XLIFF files by Translate-toolkit
  * It only supports XLIFF 1.0, and reports XLIFF 1.1 and 1.2 as invalid.


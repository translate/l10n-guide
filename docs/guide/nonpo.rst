
.. _../pages/guide/nonpo#translating_non-po_files_using_pootle:

Translating non-PO files using Pootle
-------------------------------------

We all have our favourite format, and you can certainly translate it on Pootle! Pootle is your own personal translation environment: we want you to be able to set it up to suit your own workflow and needs. 

We also want to simplify the file-format issue for you. Whether you're translating application files, documentation, manpages or working with glossaries and translation memory, you can convert the file to your favourite format.

This will be a feature of the Pootle interface: simply choose your format and convert the file! The file converters are those in the `Translate Toolkit <http://sourceforge.net/project/showfiles.php?group_id=91920&package_id=97082>`_, plus those in the `po4a <http://po4a.alioth.debian.org/>`_ package, and any others our users find useful.

So, until you can use the Pootle interface to convert your files, simply email :doc:`the Pootle mailing list <translate-pootle@lists.sourceforge.net>`, attach your file and ask for it to be converted to the chosen format and loaded onto Pootle! Then you translate it, and request conversion back to the original format.

I tested this out with my first manpage translation, where the Pootle admins converted my (n)roff file to PO format, I translated it on Pootle, then they converted it back to (n)roff, and the process worked very well. It was quick and accurate. There were no conversion problems or artefacts, and the resulting file works well.

So, what formats can we handle? Below is our list, but note that not all formats can be converted in both directions yet. If you want to add other formats to it, please edit this page or write to our mailing list. If you know of another filter which would be useful, please tell us. 

After all, Pootle is what we make of it.  :)

|  **File format**  |  **filetype**  |  **Translate Toolkit**  |  **po4a**  |
|  Comma-separated values  |  :doc:`csv <toolkit/csv>`  |  √  |  |
|  Dia diagrams (uncompressed)  |  |  |  √  |
|  Docbook  |  xml  |   |  √  |
|  Document Type Definition  |  dtd  |  √  |  |
|  Guide  |  xml  |  |  √  |
|  Hypertext Markup Language  |  html  |  √  |  |
|  Kernel configuration help files  |  |  |  √  |
|  LaTeX files  |  |  |  √  |
|  Manpages  |  |  |  √  |
|  Mozilla translation project  |  |  √  |    |
|  Nannoblogger files  |  nb  |  √  |    |
|  Open Office translation project  |  |  √  |    |
|  POD data  |  pod  |  |  √  |
|  Portable Object Template  |  pot  |  √  |    |
|  Standard Generalized Markup Language  |  sgml  |   |  √  |
|  TeX documents and derivates  |  |  |  √  |
|  Translation Memory eXchange  |  :doc:`tmx <toolkit/tmx>`  |  √  |    |
|  Qt Linguist  |  ts  |  √  |    |
|  OpenOffice.org Writer  |  sxw  |  √  |    |
|  Text file  |  txt  |  √  |  √  |
|  XML Localization Interchange File Format  |  .xliff   |  √  |    |
|  eXtensible Markup Language  |  .xml  |  |  √  |

Information on how to handle specific non-po files can be entered below.

.. _../pages/guide/nonpo#openoffice.org:

OpenOffice.org
^^^^^^^^^^^^^^

If you're starting a translation of OpenOffice in your language, you can take the .po files from ` <http://sourceforge.net/projects/translate>`_. If you have already started translation of OpenOffice with strings extracted from the source, you have to do the following:

- convert the OO format to PO format (see above)
... more to come

(see :doc:`toolkit/oo2po` if you want to convert them using the translate toolkit)

.. _../pages/guide/nonpo#firefox:

FireFox
^^^^^^^=
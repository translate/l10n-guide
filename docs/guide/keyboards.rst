
.. _../pages/guide/keyboards#keyboards:

Keyboards
*********

For some languages you will need to create a keyboard.  For many Latin languages this is not that difficult
for others it can get quite elaborate and time consuming.  Its easy if you are simply capturing the 
keyboard operation from an existing platform eg migrating a Microsoft based keyboard to Linux.  However,
if you are creating a whole new keyboard then you have a number of issues such as acceptance of the keyboard
and standardisation processes.

.. _../pages/guide/keyboards#resources:

Resources
=========

  * SIL documents on keyboards and input methods
    * `Guidelines for Writing System Support: Technical Details: Data Entry and Editing <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=WSI_Guidelines_Sec_7>`_
    * `An introduction to keyboard design theory: What goes where? <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=KeybrdDesign>`_
    * `SIL Keyboarding Chart for Africa <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=AfricanKeyboard1>`_
    * `Resources for Writing Systems Implementation using Copyleft and FLOSS (Free/Libre and Open Source Software) <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=FLOSS>`_
    * `Some tools and resources for character input <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=inputtoollinks>`_
  * A list of `Alternate Input Methods <http://www.datacal.com/alternative-language-support.htm>`_ for Windows

.. _../pages/guide/keyboards#creating_keyboards_on_microsoft:

Creating keyboards on Microsoft
===============================

.. _../pages/guide/keyboards#microsoft_keyboard_layout_creator_msklc:

Microsoft Keyboard Layout Creator (MSKLC)
-----------------------------------------

  * `MSKLC <http://www.microsoft.com/globaldev/tools/msklc.mspx>`_ --- Microsoft Keyboard Layout Creator

This will only work on Windows 2000 and XP.  It WILL NOT work on Windows 95, 98, ME or NT 4

.. _../pages/guide/keyboards#using_msklc:

Using MSKLC
^^^^^^^^^^^

Firstly load an existing keyboard layout if you simply want to extend and existing layout.

You will notice that you can define keys for for each of the shift states and for the other modified state (usualy AltGr).  For dead keys you must define one of the states as being a dead key and then define each of the combinations.  Quite easy but tedious.

Once you are happy with your keyboard then select 'Project - Test Keyboard Layout...' you will see a text entry field and can type and test the keyboard.  If all works well then select 'Project - Validate Layout', this will give you a report about any problems that were detected in your keyboard.  

Want a picture of your new keyboard? 'File - Save As Image' - they're ugly but they get the message across.

The last step is to build your keyboard for that select 'Project - Build DLL and Setup Package'.  This will create and MSI installer and a keyboard DLL, see the section below for steps on how to actually make the installer work.

.. _../pages/guide/keyboards#repackaging_installers_with_wix:

Repackaging Installers with WiX
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The MSKLC creates .msi files that don't contain the dll (they put it in a separate file).

In the keyboards/za module in CVS there is an example of how to rebuild these files correctly (for the South African keyboards). You need to run Make xx-xx.msi (and have the WiX binaries installed, see below) to rebuild the msi file for a language. You will probably need cygwin to run Make (it requires sed as well).

Manual way to fix this:
  - download WiX binaries from http://sourceforge.net/projects/wix/ and unpack them somewhere.
  - Disassemble the .msi file: ``/path/to/wix/dark.exe -x . path/to/us-za.msi us-za.wxs``
  - Make the changes to the .wxs file listed below
  - Make the wix object file: ``/path/to/wix/candle.exe us-za.wxs``
  - Build the new installer: ``/path/to/wix/light.exe us-za.wixobj``

You should see that the built installer has increased in size.

.. _../pages/guide/keyboards#changes_need_to_the_msklc_to_get_it_to_make_a_standalone_installer:

Changes need to the MSKLC to get it to make a standalone installer
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

Edit the .wxs file before the candle and light commands:
  - Add **Compressed="yes"** as an attribute to the Package element at the start
  - Add **EmbedCab="yes" Cabinet="Keyboard.cab"** to the Media element a bit further down
  - Move the Media entry to between the **Package** and **Property** sections.

.. _../pages/guide/keyboards#using_msklc_automatically:

Using MSKLC automatically
^^^^^^^^^^^^^^^^^^^^^^^^^

It's nasty using a GUI tool :-)

http://lists.sharif.edu/pipermail/persiancomputing/2004-June/001425.html seems to be an approach to making it command-line...

.. _../pages/guide/keyboards#jankos_keyboard_generator:

Janko's Keyboard Generator
--------------------------

  * `Janko's Home Page <http://solair.eunet.yu/~janko/engdload.htm>`_

This will only work for Windows 95, 98 and ME.

Please note that if your languages characters are not in any Microsoft codepages then you will not be able to
create a keyboard with those characters.  Michael Kaplan (the Microsoft localisation guru) explains why not in this 
`blog entry (look at the second one) <http://blogs.msdn.com/michkap/archive/2005/04/28/412977.aspx>`_.  Essentially Windows
95 is an old product which MS has stopped supporting and they'd rather you move to something new, they're both
technical and marketing considerations.

.. _../pages/guide/keyboards#creating_keyboard_layouts_for_linux:

Creating keyboard layouts for Linux
===================================

.. _../pages/guide/keyboards#x.org_and_xfree86:

X.org and XFree86
-----------------

FIXME various pointers

.. _../pages/guide/keyboards#getting_a_nice_picture_of_your_layout:

Getting a nice picture of your layout
-------------------------------------

This prooves rather harder than expected.  These pages will give you some pointers that are hopefully helpfull.

  * `Ogonkify patch for processing xkbprint output <http://www.meduna.org/sw_a2ps_en.html>`_
  * Look at `xkbprint <http://www.xfree86.org/current/xkbprint.1.html>`_ man page

.. _../pages/guide/keyboards#keyboard_mapping_for_linux_kmfl:

Keyboard Mapping for Linux (KMFL)
---------------------------------

  * `Sourceforge project page <http://sourceforge.net/projects/kmfl>`_

This project is trying to bring the kyman keyboard mapings to Linux it is/will be GPL'd

.. _../pages/guide/keyboards#changes_needed_to_your_linux_distribution:

Changes needed to your Linux distribution
-----------------------------------------

The various Linux distros have different configuration applications for setting things like keyboard.  These few notes give a quick guide as to what files you need to change and where you need to look.

.. _../pages/guide/keyboards#fedora/red_hat:

Fedora/Red Hat
^^^^^^^^^^^^^^

The application ``system-config-keyboard`` sets the keyboard for your setup.  It is simply a configuration tool for the normal X keyboard mappings.  The file **``keyboard_models.py``** which is part of **rhpl** needs to be edited to add your keyboard.

.. _../pages/guide/keyboards#creating_keyboard_layouts_for_mac:

Creating keyboard layouts for Mac
=================================

SIL has created a nice tools called `Ukelele <http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&item_id=ukelele>`_ designed to create the XML files needed by the Macs keyboard system.
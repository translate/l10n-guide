
.. _../pages/guide/message_marking#profiling_through_message_marking:

Profiling through message marking
*********************************

If you can quickly determine where a string in the user interface originates
from then you can determine what strings and packages are more important to
translate.

To achieve this you need to be able to visually identify the strings origin.
This is achieved by using :ref:`toolkit:podebug` from the `Translate Toolkit
<http://toolkit.translatehouse.org>`_.

.. _../pages/guide/message_marking#advantages:

Advantages
==========

It is simple to use and can also be used for correcting errors in the
translations.  By simply running an application or computer environment in the
same way as your target audience you can quickly determine what parts of the
system are being called and therefore what aspects you will want to translate.

.. _../pages/guide/message_marking#using_the_podebug_method:

Using the podebug method
========================

:ref:`toolkit:podebug` is simple to use and will take a directory of translated
PO files and create a directory of tagged PO files::

  podebug -f "[%cb] " -i af -o af-debug

Once the debug PO files are created then the normal build process is followed
for that project.

.. _../pages/guide/message_marking#existing_profiling_builds:

Existing profiling builds
=========================

The following are builds that have already been profiled.  Simply download,
install and run the program as normal, making notes of the source files
identified in the various screens.

* `OpenOffice.org
  <http://www.kilinux.org/kiblog/downloads/OOo_1.1.3_LinuxIntel_install_src_debug.tar.gz>`_


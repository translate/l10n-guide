
.. _../pages/guide/translation/variables#variables:

Variables
*********

Variables are placeholders that will be substituted with values when the
translated application is run.

When you are translating and see a messages that looks like this::

  Error: file %s causes error %s

You need to know that both of the %s will be replaced during execution to
produce an error message such as this::

  Error: file /home/bob/todo caused error segmentation fault

.. _../pages/guide/translation/variables#variables_styles:

Variables styles
================

There are many different types of variables the most common are the `printf
<http://man.splitbrain.org/index.php/man/printf(3)>`_ style which include the
following::

  %s %d etc.

However, **Python named variables** are becoming more common::

  %(name)s  %(filename)s  %(message)s  etc.

Do **not** translate the word(s) inside these named variables: these are
literal expressions, not translatable terms.

Over and above these you will see various styles depending on the application
that you are translating.  Here are the styles present in the major
applications:

.. _../pages/guide/translation/variables#openoffice.org:

OpenOffice.org
--------------
::

  &file;
  %PROGRAMNAME 
  %PROGRAMNAME%
  $(file)
  $file$
  ${file}
  #file#
  ($file)
  $[file]
  [file]
  $file

.. _../pages/guide/translation/variables#mozilla:

Mozilla
-------
::

  &name;
  %name%
  %s
  $name
  #1

.. _../pages/guide/translation/variables#gnome,_the_translation_project_and_others:

GNOME, The Translation Project and others
-----------------------------------------
::

  %s
  $(name)
  %(name)s  [Python named variables]

.. _../pages/guide/translation/variables#what_values_will_a_variable_contain:

What values will a variable contain?
====================================

Knowing that the %s will contain values will help you decide how to structure
the sentence.  In many variable styles the programmer will name the variable:
file, name, dir.  From this you can know what content to expect.  With the case
of printf style variables (those that start with % and have one letter) you can
use the printf manpages to determine the type of variables but generally:

========  ===========
 letter    content     
========  ===========
  s         string     
  d         decimal    
========  ===========

Use this information to restructure your sentences.

.. _../pages/guide/translation/variables#changing_the_order_of_variables:

Changing the order of variables
===============================

Your language might be one that has a different sentence structure or order to
that of English.  In this case feel free to change the order of the variables.
However in your translation you will need to tell the computer what new order
you have used.  You can do that by numbering the variables::

  Xxxxx %2$s xxx xxxx %1$s

This will reorder the variables placing the second %s before the first.

Please note that not all translated applications will support this feature.
Almost all GNU Gettext based programs will allow you to do this.  Others may
not, so please check.

.. _../pages/guide/translation/variables#leaving_out_a_variable:

Leaving out a variable
======================
It might be possible with some applications to leave out a variable entirely.
Applications that use named variables might work. For glib based applications
(applications using GNOME or GTK) you might be able to do the following (can
somebody confirm?)::

  xxxxxxxxxxxx %0$s

This way gettext will still accept your translation as valid (it contains  all
the parameters) but the variable will not appear.

.. _../pages/guide/translation/variables#languages_that_need_to_prefix_variables:

Languages that need to prefix variables
=======================================

If your language adds prefixes to words depending on how they relate to other
parts of the sentence then you need to choose how to add you prefix wisely.
This should probably become a standard for your language.  Here are some
examples that give you an idea of how your translation would appear, the
language is (almost) fictitious.

============  ================  ========================  ===============================================================================
  Language      Translation       When running              Comment                                                                        
============  ================  ========================  ===============================================================================
  Default      Loading %s        Loading google.com        This is without any translation                                                 
  1            Layisha %s        Layisha google.com        This works but is not what the language speaker expects                         
  2            Layisha i%s       Layisha igoogle.com       This is correct according to the language but produces an unreadable result     
  3            Layisha i-%s      Layisha i-google.com      This balances what the language user expects while making it readable           
  4            Layisha i- %s     Layisha i- google.com     This might look a bit odd to the user but would also work                       
============  ================  ========================  ===============================================================================

The main issue that you must consider is that you are often not aware of what
content the variable might contain.

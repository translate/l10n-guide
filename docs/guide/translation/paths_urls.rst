
.. _../pages/guide/translation/paths_urls#translating_example_paths_and_urls:

Translating Example Paths and URLs
**********************************

A path shows you where a file is located on your computer

  /home/dwayne/somefile.doc
  c:\Windows\Desktop\somefile.doc
  \\Server\share\somefile.doc

A URL is similar but relates to files located on the Internet

  http://www.google.com
  ftp://someserver.com/file/to/download.zip

In translatable messages you will find real paths and URLs but you will
also find instances where the author is giving the user an example. 

.. _../pages/guide/translation/paths_urls#simple_policy:

Simple Policy
=============

Want a simple policy on what to do with URLs (example or real)?

**Do not translate ANY paths, URLs or URIs**

.. _../pages/guide/translation/paths_urls#system_directories:

System directories
==================

Many operating systems contain system directories, these are directories used
by the operating system itself.  System direcotories will not change even when 
your langauge changes.  The following are system directories on Linux and should 
not be translated:

  /home
  /mnt
  /usr
  /etc
  /bin
  /sbin

The following are system directories on Windows and should also not be translated:

  C:\Windows
  C:\Windows\System

.. _../pages/guide/translation/paths_urls#home_directories:

Home directories
================

On Linux systems each user has a home directory which corresponds to their 
username and is usually located under /home eg. /home/fred.
The word **home** should not be translated because it is a sytem directory.
But the username should be translated.  You should probably keep the username
to ASCII characters (some operating systems cannot use Unicode in filename) 
and thus romanise the name if you needed.

.. _../pages/guide/translation/paths_urls#extensions:

Extensions
==========

A file is made up of the:

| path  |  **/the/path/to/**file.doc  |
| filename  | /the/path/to/**file.doc**  |
| basename  | /the/path/to/**file**.doc  |
| extension  | /the/path/to/file.**doc**  |

The file extension is thus the characters that appear after the last fullstop in a filename.
You do not translate the file extension but you do translate the basename.  
Eg. budget.doc - Translate budget but do not translate .doc.

.. _../pages/guide/translation/paths_urls#examples:

Examples
========

Often examples can be identified because they involve saving a file from within 
an application. Eg,  "Save the picture to /home/dwayne/picture/snapshot.png"
You will want to translate dwayne, picture and snapshot.  You would not translate home
because that is a system directory nor png because it is an extension.

.. _../pages/guide/translation/paths_urls#urls:

URLs
====

A URL is made up of these components

  protocal :// server : port / directorie(s) / filename . extension

Here is a real URL

  http://www.translate.org.za/downloads/openoffice.org-afrikaans.tar.gz

you should not translate it unless you needed to point to 
a version of the URL that is in your language.

This is an example URL

  http://example.com/directory/filename.html

you would translate: example, directory and filename.

You would not translate:

| http  | the protocols are not translatable  |
| .com  | top level doamns are also not translatable  |
| .html  | is a file extension and therefore not translated  |

.. _../pages/guide/translation/html#translating_html:

Translating HTML
****************

HTML is used to design web pages, but it often occurs in GUI translations.  You will also see XML - which looks very much like HTML.  They are both examples of markup languages used to specify some information about text.  This guide explains which parts of HTML you can safely translate and which you should leave unchanged.

HTML is recognised by tags between angle brackets: <tag>

A tag can also contain extra information: <img src="picture.jpg" />  Here the img (image) tag contains an extra attribute to specify the file name of the picture to show in the image tag.

Tags often occur in pairs: <p> </p> - note the difference between the opening and closing tag.

.. _../pages/guide/translation/html#what_not_to_translate:

What not to translate
=====================

Do not translate the actual markers.  HTML consists of tags which indicate the start and end of a section of text.  This text could be a heading, a paragraph, a hyperlink or just a piece of text to display in bold:

  * <h1>A heading</h1>
  * <p>A paragraph</p>
  * <a href=bob.html>A hyperlink</a>
  * This is normal and <b>this is bold</b>

Some markers just beg to be translated, such as these:
<title>, <center>, <body>
Do not be tempted - these need to remain in English.

.. _../pages/guide/translation/html#reordering_or_changing_tags:

Reordering or changing tags
===========================
In some cases, it might be necessary to reorder the tags.  If tags surround some text, it means that the translation representing the text inside the tags should probably also be surrounded with the same tags.

Some inline tags can represent something that should be positioned in the translation, such as an image or a footnote.  Take care where you put this in the translation to have the same effect as the original text.

Whenever you work with tags, always ensure that opening and closing tags go together in pairs, and that the closing tags always follow the opening tags.

.. _../pages/guide/translation/html#attributes_-_which_to_translate:

Attributes - which to translate
===============================

An attribute is a variable associated with a tag.  E.g.  <body bgcolor=blue>, here "bgcolor" is an attribute and "blue" is its value.  Attributes, like tags, are never translated.  However some values can be translated.  In the example above the value "blue" should not be translated.

There are only a few values that can be translated:

| alt  | found in the img (image) tag and used to give a textual description of the picture that will be loaded. This is essential for people with disabilities |
| title  | a text title that pops up when you hover something, exactly like a tooltip |

In some cases you might also need to change the "lang" or "dir" attributes. This is best left to people with good knowledge of HTML.

.. _../pages/guide/translation/html#tags_that_should_be_translated:

Tags that should be translated
==============================

Some things that looks like tags are not really tags and should be translated. These would include the following:
<Error>, <File not found>, etc.

How to identify them?  If you are an experienced HTML editor you will immediately know which are real tags.  If you are not, then use this rule:  If its all in lowercase or uppercase then it very likely a tag.  If it combines case most likely it is not.  If it contains any attribute such as <font color=blue> it is definitely a tag.  And lastly if it's the only text in the message e.g. "<None>" then it is most probably not a tag.

.. _../pages/guide/translation/html#should_i_change_hyperlinks_and_images:

Should I change hyperlinks and images?
======================================

Although as a translator you should only change the text of the program, you do have complete control over the HTML.  This can be used to your advantage if needed. If for example you were translating a manual that referred to an image of the application then you would most likely want to have an image in the users language, rather then explaining to them in their language using an English picture.

Because of the work involved, the translation teams will often not change images until much later in their efforts.

To change the image first you will need to create an image.  You can use ksnapshot or gnome-screenshot or Gimp to create screenshots.  Remember to keep the look consistent, i.e. try to use the same theme across all images.  Ideally your picture should be the same size as the one it is replacing.

Lastly depending on the application you will need to place the file in the correct place so that it will be shown with your translations.  What usually happens is that images are first sought in the language specific directory and if they are not found then they use the English version.


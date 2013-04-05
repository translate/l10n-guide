
.. _../pages/guide/translation_guidelines_german#german_translation_guidelines:

German Translation Guidelines
*****************************
**(Richtlinien für die Deutsche Übersetzung)**

Dieses Dokument enthält die Richtlinien die speziell bei deutschen Übersetzungen zu beachten sind. Bitte lesen Sie auch die :doc:`allgemeine Einführung <guide/start>`, da hier nur auf Besonderheiten der deutschen Sprache eingegangen wird.

Empfehlenswert ist auch das `Handbuch für Übersetzer <http://oss.erdfunkstelle.de/kde-i18n/tiki-index.php?page=handbuchUebersetzungKDE4>`_ des deutschen KDE-Übersetzungsteams (speziell das Kapitel „Inaltliches“ und die nachfolgenden Kapitel, aber auch etwas technischer Hintergrund (speziell Gettext und PO-Dateien) kann nicht Schaden).

.. _../pages/guide/translation_guidelines_german#groß-/klein-schreibung:

Groß-/Klein-Schreibung
======================
Im Gegensatz zum Englischen werden im Deutschen nicht nur Wörter am Satzanfang, Eigen- und Ländernamen sondern außerdem auch alle Substantive (Hauptwörter) groß geschrieben.

.. _../pages/guide/translation_guidelines_german#titel:

Titel
-----
Handelt es sich um einen Titel (Buch, Film, usw.) werden im Englischen fast alle Wörter groß geschrieben, dies ist im Deutschen nicht so, hier wird normale Groß-/Kleinschreibung verwendet.

> Dances With Wolves -> Der mit dem Wolf tanzt

.. _../pages/guide/translation_guidelines_german#getrennt-schreibung:

Getrennt-Schreibung
===================
Im Englischen werden viele zusammengesetzte Hauptwörter dadurch gebildet, dass man die Wörter einzeln hintereinander schreibt. Im Deutschen hingegen wird entweder ein Bindestrich verwendet oder das Wort zusammengeschrieben:

> localisation guide -> Übersetzungsleitfaden oder Übersetzer-Leitfaden

.. _../pages/guide/translation_guidelines_german#ss_und_ß:

SS und ß
========
Entgegen manchen Gerüchten gibt es auch nach der Rechtschreibreform noch das ß. Es kommt dann zum Einsatz wenn ein scharfes S auf einen langen Vokal oder mehrere Vokale folgt:

> <del>Strasse</del> Straße; <del>Massband</del> Maßband aber Knetmasse
> <del>Weiss</del> Weiß; <del>aussen</del> außen

.. _../pages/guide/translation_guidelines_german#apostrophe:

Apostrophe
==========
Im Deutschen wird das Genitiv-s nicht mit einem Apostroph vom zugehörigen Wort getrennt wie das im Englischen der Fall ist. Weder im Deutschen noch im Englischen wird das Plural-s mit einem Apostroph abgetrennt. Generell sollte man den Apostroph nur sparsam verwenden.

> David's car -> Davids Auto
> <del>Apple's</del> Apples are red

.. _../pages/guide/translation_guidelines_german#plural_mehrzahl:

Plural (Mehrzahl)
=================

.. _../pages/guide/translation_guidelines_german#gettext_plural_header:

Gettext Plural Header
---------------------
<file>Plural-Forms: nplurals=2; plural=n != 1;</file>

.. _../pages/guide/translation_guidelines_german#hartcodierter_plural:

Hartcodierter Plural
--------------------
Manchmal wurde der Plural in Klammern in den Text eingefügt anstatt zwei Texte zu verwenden wie `Gettext <http://de.wikipedia.org/wiki/Gettext>`_ es eigentlich vorsieht. Da ein Plural im Deutschen eine ganze Reihe weiterer Änderungen im Satz nach sich ziehen kann und auch in der Regel nicht so leicht wie im Englischen mit einem angehängten s gebildet wird sollte man wenn der Aufwand (und Platzverbrauch) zu groß wird die Mehrzahl verwenden.

> Please enter the author(s) name. -> <del>Bitte geben Sie den/die Namen des/der Autors/Autoren ein.</del> Bitte geben Sie die Namen der Autoren ein.
> Document(s) -> Dokument(e)

.. _../pages/guide/translation_guidelines_german#höflichkeit:

Höflichkeit
===========
Es sollte grundsätzlich die formale Anrede (Sie) benutzt werden, dabei ist darauf zu achten, dass Sie, Ihr, Ihnen usw. wenn es sich um eine Höflichkeitsform handelt groß zu schreiben ist, wenn es sich jedoch um etwas anderes handelt (zum Beispiel Bezug zu anderen Personen als dem angesprochenen Benutzer) klein.\\
Die informelle Anrede (Du) sollte nur in sehr seltenen Fällen (z.B. Computerspiele die ausschließlich auf ein jugendliches Publikum ausgerichtet sind) benutzt werden, da sie leicht sehr künstlich (auf jung getrimmt) wirkt.

> Translate this programme into your language -> Übersetzen Sie dieses Programm in Ihre Sprache

.. _../pages/guide/translation_guidelines_german#weibliche_formen:

Weibliche Formen
----------------
Wo immer möglich sollte man versuchen geschlechtsneutrale Bezeichnungen zu verwenden. Ist dies nicht möglich so empfehle ich den generischen Maskulin, da man sonst Gefahr läuft dass die Texte zu lang und schwer lesbar werden.
> students -> Studierende (statt Studenten und Studentinnen)
> the user -> der Benutzer (statt der/die Benutzer/-in)

.. _../pages/guide/translation_guidelines_german#zeichensetzung:

Zeichensetzung
==============
Die deutsche Zeichensetzung unterscheidet sich (bis auf die Kommasetzung) nicht wesentlich vom Englischen. Insbesondere bei Sonderzeichen (alles außer Punkt und Komma) sollte peinlichst darauf geachtet werden, dass die Zeichensetzung bestehen bleibt. Kommas werden im Deutschen allerdings wesentlich häufiger verwendet als im Englischen, wo sie eigentlich nur dazu dienen in Situationen die sonst mehrdeutig wären Klarheit zu schaffen. Auch sollte man bei Sätzen die durch die Übersetzung zu lang werden nicht davor zurückschrecken sie in zwei separate Sätze aufzutrennen.

.. _../pages/guide/translation_guidelines_german#vorsicht_bei_auf_den_ersten_blick_unsinnigen_zeichenfolgen:

Vorsicht bei auf den ersten Blick unsinnigen Zeichenfolgen!
-----------------------------------------------------------
Oftmals handelt es sich dabei um spezielle Markierungen zur Formatierung des Textes. So werden z.B. in vielen Programmiersprachen Zeilenumbrüche, Tabulatoren und mehrere aufeinander folgende Leerzeichen (diese Zeichengruppe wird als „Whitespaces“ bezeichnet) so behandelt als stünde an ihrer Stelle ein einziges Leerzeichen. Will man also eines dieser Zeichen im ausgegebenen Text erzeugen muss man sogenannte Escape-Sequenzen benutzen (z.B. ``\n`` für einen Zeilenumbruch, ``\t`` für einen Tabulator, ``\\`` für einen Backslash (in C-verwandten Sprachen, HTML hat wiederum andere Escape-Sequenzen)). Auch Links werden oft speziell (z.B. durch eine zweifache eckige Klammer) gekennzeichnet um sie im Programm anklickbar zu machen. An dieser Stelle sei nochmals auf die :doc:`allgemeine Einführung <guide/start>` verwiesen.

Es ist also überaus ratsam Zeichensetzungen exakt aus dem Original zu übernehmen, Pootle bietet hierfür die Schaltfläche „Kopieren“ die den Originaltext in das Textfeld kopiert, in welchem dann nur noch der pure Text übersetzt werden muss, so ist garantiert, dass die Zeichensetzung erhalten bleibt.

> Recent news:\n
> Our project has been <nowiki>`slashdotted <http://slashdot.org>`_</nowiki>.

> Neuigkeiten:\n
> Unser Projekt wurde auf <nowiki>`slashdot.org <http://slashdot.org>`_</nowiki> erwähnt.

.. _../pages/guide/translation_guidelines_german#anführungszeichen:

Anführungszeichen
-----------------
Die korrekten deutschen Anführungszeichen sind folgende: „ “ bzw. ‚ ‘ (Regel 9966) und auch Französische sind zugelassen » « bzw. › ‹

Leider lassen sich diese Zeichen nicht so einfach mit der Tastatur erzeugen **(bitte benutzen Sie keine Kommas, größer als, kleiner als oder andere ähnlich aussehende Zeichen, da sie nur zu Verwirrung führen** (z.B. für Blinde die den Text durch ein Programm vorgelesen bekommen oder Leute die andere Schriftarten verwenden als Sie)). Theoretisch kann man die Zeichen einfach per Kopieren & Einfügen aus der Zeichentabelle oder dem obigen Text verwenden oder den Unicode per Tastenkombination eingeben (Windows: Alt-Taste gedrückt halten und Code auf dem Ziffernblock eingeben, Gnome: STRG+Shift+U drücken und dann den Code in hexadezimaler Schreibweise eingeben) dies ist jedoch unpraktikabel.

Linux-Benutzer können stattdessen die :doc:`Compose-Taste <https///help.ubuntu.com/community/composekey>` benutzen oder sich mit ``xmodmap`` die Tastaturbelegung entsprechend anpassen (ich verwende Caps-Lock als Compose-Taste, da sie sonst sowieso keinen Zweck erfüllt). Wem das immernoch zu umständlich ist, der kann auch die „ganz normalen“ Anführungszeichen " und ' (Shift+2, Shift+#) benutzen.

**Achtung:** „normale Anführungszeichen“ (") müssen in PO-Dateien mit der Escape-Sequenz <file>\"</file> codiert werden, sonst meldet Gettext einen Syntax-Fehler. Pootle und die meisten anderen PO-Editoren machen das zwar automatisch aber man sollte lieber vorher nochmal im Handbuch nachschauen bevor man alles von Hand korrigieren muss.

.. _../pages/guide/translation_guidelines_german#die_französische_art:

Die Französische Art
--------------------
In Frankreich ist es üblich Leerzeichen vor die Satzzeichen zu setzen. Dies ist im Deutschen falsch (und äußerst unschön) und wird als *Plenken* bezeichnet. Auch das Gegenstück, das verzichten auf Leerzeichen um die Satzzeichen ist falsch (soweit ich weiß in allen Sprachen) und wird *Klempen* genannt.

Richtig: kein Leerzeichen vor den Satzzeichen und ein Leerzeichen dahinter (Ausnahmen: öffnende Klammern und Gedankenstriche).

> Plenken , also das Einfügen eines Leerzeichens zwischen Wort und nachfolgendem Satzzeichen , ist uncool !
> Klempen,der beinahe völlige Verzicht auf Leerzeichen,aber auch!Auch wenn man dadurch Platz spart.

.. _../pages/guide/translation_guidelines_german#markennamen:

Markennamen
===========
Werden üblicherweise nicht übersetzt. Ausnahmen sollten nur dann gemacht werden wenn die Marke auch im allgemeinen Sprachgebrauch in der übersetzten Form benutzt wird (mir fällt gerade keine solche ein)

.. _../pages/guide/translation_guidelines_german#fehler_im_original:

Fehler im Original
==================
Sollten nicht einfach in der Übersetzung behoben werden. Man sollte vorerst den Text so übersetzen wie er da steht, die Übersetzung als fraglich markieren und den vermeintlichen Fehler in der Anmerkung darlegen. Dann sollte man die Entwickler kontaktieren und sie auf den augenscheinlichen Fehler aufmerksam machen (die Kontaktaufnahme kann in der Regel am schnellsten über das IRC-Netzwerk erfolgen). Diese Vorgehensweise hat die Vorteile, dass erstens alle Sprachen von der Fehlerkorrektur profitieren, zweitens der eigentliche Fehler behoben wird und nicht nur seine Auswirkungen minimiert und drittens dass für den Fall dass es gar kein Fehler war die Übersetzung korrekt bleibt.

.. _../pages/guide/translation_guidelines_german#fragliche_wörter_&_anmerkungen:

Fragliche Wörter & Anmerkungen
==============================
Wenn man sich bei einer Übersetzung nicht 100% sicher ist sollte man nicht zögern diese als fraglich zu markieren und evtl. eine Bemerkung dazu zu schreiben warum man sich nicht sicher ist. Es ist wesentlich besser einige korrekte Übersetzungen als fraglich zu markieren als eine falsche Übersetzung unmarkiert zu lassen. Der Grund ist einfach: während fragliche Übersetzungen häufig nochmals von anderen Übersetzern geprüft werden, kann es sein dass die unmarkierten von keinem mehr überprüft werden.

Auch an anderen Stellen sollte nicht mit Anmerkungen gespart werden, gerade an solchen Stellen an denen auch andere Übersetzungen potenziell in Frage kommen oder wenn man andere Übersetzer korrigiert sollte man kurz begründen warum man diese Form wählt und nicht die andere, auch um zu verhindern, dass beide Übersetzer die Übersetzungen immer wieder gegenseitig korrigieren was schnell zu Streitigkeiten führen kann.

.. _../pages/guide/translation_guidelines_german#glossare:

Glossare
========
Kann ich keine empfehlen (da ich keine benutze). Im Zweifelsfall einfach mal bei einer anderen Anwendung nachgucken. Auch Wikipedia hilft oftmals bei der Suche nach dem passenden Begriff weiter.

Pootle listet bei der Übersetzung möglicherweise relevante Wörter mit ihren Übersetzungen aus dem Terminologie-Projekt rechts auf. Oftmals wurden dort alternative Übersetzungen als Anmerkung hinterlegt welche als Tooltip verfügbar sind (den Mauszeiger für eine kurze Zeit über dem Wort positionieren).

.. _../pages/guide/translation_guidelines_german#wörterbücher:

Wörterbücher
============
Wer ein Online-Wörterbuch sucht ist bei `leo.org <http://www.leo.org/>`_ ganz gut aufgehoben (Vorsicht bei Google-Sprachtools & Co., da sie oftmals nur eine Übersetzung für das Wort auflisten und nicht wie leo.org auch alternative Bedeutungen)

„Analoge“ Wörterbücher sind für die Übersetzung von Anwendungen meist eher weniger geeignet, da Online-Wörterbücher oftmals einen größeren Wortschatz in Richtung EDV aufweisen. Auch hier sollte man auf einen ausreichend großen Wortschatz achten und auch alternative Bedeutungen eines Wortes durchlesen.
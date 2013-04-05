
.. _../pages/l10n/displaysettings#display_settings:

Display settings
****************
On this page, we're putting together a list of display settings that are needed or preferred for each language. If your language isn't represented, or if the information is incomplete in some way, please edit it or add to it. Some tips for developers are available at the :doc:`developers/styling` guidelines.

For many languages written in Latin scripts without diacritics, the default settings are probably OK. 

List the fonts in order of preference, even if they are not widely available. Browsers will take the first font in the list that is available. If a certain glyph (character) is not available, it will continue in the list trying to find a font to display the glyph. Please specify your choice of Serif or Sans with the font name where relevant.

If a font-size adjustment is necessary to display your language readably, input it as a percentage relative to 100% (e.g. 130% for a size of 30% larger than the default). Input a percentage which should create a font size equally readable with the ordinary Latin script at the default size. Remember to take your resolution, browser settings, etc. into account. Your browser's setting for the minimum font size should override a smaller font size, so please make sure your browser preferences don't overrule what you specify here.

Underlining hyperlinks is a common practice, but a nuisance for some languages, especially those which have a diacritic or mark of some kind underneath the character. Indicate the ideal link-decoration for your language. If underlines don't work, perhaps overlines do, or links becoming bold when the mouse hovers over them. Colour-specific decoration is probably not ideal here. In any case, the mouse in your browser will usually change to a hand when it passes over a link, so links don't **have** to be marked otherwise.

If your language uses a different number system (such as many languages from the middle and far east), you can indicate it. Please indicate if not all readers of the language prefer the number system (like for Arabic).

If you need to specify another setting, add a column to this table and input the information. To specify the special characters for your language that Pootle should provide during editing, see :doc:`pootle/characters`.

=====  =================  =========================================================================  ===========================  ======================  ===================================================  =====================================
 ISO    English name       Fonts in order of preference                                               Font size adjustment         Hyperlink decoration    RTL                                                  Number system                         
=====  =================  =========================================================================  ===========================  ======================  ===================================================  =====================================
 ar     Arabic             Tahoma, Nazli, DejaVu Sans                                                                                                      Yes                                                  Some prefer Arabic-Indic digits       
 bn     Bengali            FreeSans, Muktinarrow, Vrinda                                              110%, line-heigt:120%        ?                       No                                                   ...                                   
 fa     Persian            Terafik, Traffic, Roya, Nazli, Nazanin, sans                               120%                                                 Yes                                                  Eastern-Indic digits                  
 el     Greek              Dejavu                                                                                                                         No                                                                                          
 he     Hebrew                                                                                                                                             Yes                                                                                        
 ks     Kashmir                                                                                                                                            Yes                                                                                        
 ps     Pashtu                                                                                                                                             Yes                                                                                        
 ru     Russian            DejaVu Sans, Liberation Sans, FreeSans, Sans                                                                                    No                                                   support dashes and hyphens properly   
 ug     Uyghur             UKIJ Tuz Tom, Alkatip, Uyghur Ekran, Tahoma, Segoe UI, Microsoft Uighur                                                         Yes                                                                                        
 ur     Urdu               Nafees Nastalique, Nafees Web Naskh                                                                                             Yes                                                                                        
 vi     Vietnamese         Lucida Grande, Vu Phu Tho, [[http://freshmeat.net/projects/urwvn/         URWVN fonts]], DejaVu Sans    None                    No underline, no overline, change colour on hover    No                                    
 yi     Yiddish                                                                                                                                            Yes                                                                                        
 zh     Chinese                                                                                       120%                         underline               No                                                                                         
 fr     French             Arial                                                                                                                           yes                                                                                        
=====  =================  =========================================================================  ===========================  ======================  ===================================================  =====================================

.. _../pages/l10n/displaysettings#external_links:

External links
==============
  * http://wiki.freedesktop.org/wiki/Software_2fFonts
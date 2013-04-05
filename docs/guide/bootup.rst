
.. _../pages/guide/bootup#direction_setting_based_on_the_installation_and_bootup_process:

Direction setting based on the installation and bootup process
**************************************************************

This document looks at the whole Linux installation and bootup process with these main sections:

  - Installation
  - Booting
  - Init 5 (GUI)
  - Init 3 (Text)

The bootup and installation process are very visual and give a user the first impression of 
the level of localisation in their software. If we can give them a good impression with less
work then it becomes easier to create a fully translated Linux distribution.

The idea is to layout the dependencies and try place translatable components in
some relative order in the process.  This is done so that we for instance can place 
the language locale file at the correct point in the bootup process. And thus at the 
correct point at which it becomes important to a localisation project.

FIXME This document is based on Fedora but probably applies to any Linux distribution.

.. _../pages/guide/bootup#installation:

Installation
============

=======================  ===========  =================================================================================================================================================
 Stage                    Messages     Description                                                                                                                                       
=======================  ===========  =================================================================================================================================================
 CD boot messages          (unkown)                                                                                                                                                      
 rhpl                      134         lists mice keyboards and exceptions might be needed in bootup as it mentions failed mouse detection and not being able to do graphical install    
 Comps                     158         package groups and some descriptions used by anaconda I presume                                                                                   
 Anaconda installer        1473                                                                                                                                                          
 Anaconda online help      263                                                                                                                                                           
 Firstboot                 73                                                                                                                                                            
=======================  ===========  =================================================================================================================================================

.. _../pages/guide/bootup#booting:

Booting
=======

===============  ==========  ==========================================================================================
 Stage            Messages    Description                                                                                
===============  ==========  ==========================================================================================
 Grub             -           not sure how to localise (localisation not implemented only scheduled post 1.0 release)    
 kernel                       The Linux kernel messages are localisable                                                  
 Locale files     -           needed by some initscripts to display date                                                 
 Initscripts       29         only 'sysinit' and some 'init.d/funtions'                                                  
 rhgb              29                                                                                                    
 Kudzu             70                                                                                                    
===============  ==========  ==========================================================================================

**END OF BOOT PROCESS** the next stage depends on the run level, most end-users will never see run level 3

.. _../pages/guide/bootup#init_3:

Init 3
------

=============  ==========  =======================================================================
 Stage          Messages    Description                                                             
=============  ==========  =======================================================================
 /bin/login                 found in util-linux - should try and extract only /bin/login strings    
=============  ==========  =======================================================================

.. _../pages/guide/bootup#init_5:

Init 5
------

============  ==========  ===========================================
 Stage         Messages    Description                                 
============  ==========  ===========================================
 GDM            695        lots of bumf but hard to seperate it out    
 Wallpaper                                                             
 Fedora         5          artwork                                     
============  ==========  ===========================================

.. _../pages/guide/bootup#post_booting:

Post Booting
============

The booting process will take a computer to the place where the user is required to login.  This section looks at what items
are seen just after the user logs in.

.. _../pages/guide/bootup#init_5:

Init 5
------

  * Wallpaper (if different from login wallpaper)
  * Fedora - menu's
  * GNOME / KDE
    * Kicker
    * K Menu bar general
    * Clock
    * Desktop

.. _../pages/guide/bootup#init_3:

Init 3
------

  * /etc/issue not really possible to change easily

.. _../pages/guide/bootup#config_tools:

Config Tools
============

Once logged in a user will interact with the standard Free and Open Source applications that are usually localised
outside of the distribution community.  However each distribution has its own set of configuration tools that
need localisation.

FIXME Create some category of which configuration tools are more important to localise then others.

On Fedora all the user centric and hardware related system-config tools constiture 7691 words of translation.


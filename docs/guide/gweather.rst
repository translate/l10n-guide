
.. _../pages/guide/gweather#localising_gweather:

Localising GWeather
*******************

This email explains what needs to be done to localise gweather so that it has
the right names for locations in your locale.  ::

    From: Davyd Madeley 
    To: gnome-love@gnome.org, gnome-i18n@gnome.org
    Date: Tue, 30 Nov 2004 03:10:04 +0800
    Subject: GNOME Lovers Needed: l10n work for locations database

    gweather ships a very comprehensive locations database. GNOME-Applets
    2.9.2 has some 3000+ more locations to this database[1] from syncing
    with the latest METAR list, but now we need your help.

    The database now has support for  tags (as well as ,
     and ). While region, country, and state are all easy to
    work out, city tags are hard, it's easy to figure out what locations are
    in a city (sometimes) but not what their local names are. As a result,
    many names are things like "Location 1" or "My Location (alternate)".

    This is where you come in, spread around the world, and having a good
    knowledge of local, state and maybe even national geography, you will be
    able to clean up the locations file for your area.

    How do you do this?
     1) Check out the latest version of Locations.xml.in [2]
     2) Fix up your area, the format for the XML file should be fairly
    evident, or you can consult the DTD [3].
     3) Use xmllint and the DTD to check that the file structure is still
    sane.
     4) File a bug in bugzilla under the gweather component of
    gnome-applets. Give it the subject, "Locations Love - $my_area". Attach
    a context diff of the Locations.xml.in file.

    If you're a new contributor to GNOME, this is a really good way to get
    yourself in the Changelog and NEWS file. This type of bread and butter
    work is really easy, and you don't even have to build any software to do
    it ;)

    Remember that all strings in the Locations.xml.in file should be in the
    C locale (US english). This means that locations should use their
    American names or anglicized names. Otherwise use the local name. If you
    use an anglicized name, add a comment to the XML so that translators
    know about the local name.

    I would really like this done as soon as possible so that translators
    can get to work on getting the translations for the database up to
    scratch. I want to have a really rocking locations database ready for
    GNOME 2.10 (and eventually weather.gnome.org).

    Also, maintaining the locations database has been proving to be an
    increasingly time consuming task for me. If you feel you might be up to
    scratch at maintaining this database, drop me a line, I could do with
    some help.

    Happy Hacking,
    --davyd

    [1] a log showing new locations/changed locations and removals is here:
    http://oracle.bridgewayconsulting.com.au/~davyd/misc/locations_changes.log
    [2] http://cvs.gnome.org/viewcvs/*checkout*/gnome-applets/gweather/Location=
    s.xml.in
    [3] http://cvs.gnome.org/viewcvs/*checkout*/gnome-applets/gweather/location=
    s.dtd

    -- 
    Davyd Madeley              http://www.davyd.id.au/


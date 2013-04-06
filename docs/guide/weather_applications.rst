
.. _../pages/guide/weather_applications#localising_weather_applications:

Localising Weather Applications
*******************************

There are a number of weather related applictions for the Linux desktop.  Most
of these lookup up weather data from airport meteorological stations.  These
stations are identified by an international 4 character abbreviation.  These
applcications use this to lookup the corect watehr information.

.. _../pages/guide/weather_applications#applications:

Applications
============
.. toctree::
   :maxdepth: 1
   :hidden:

   gweather
   evolution

* :doc:`gweather`
* :doc:`evolution`

.. _../pages/guide/weather_applications#problems:

Problems
========

FIXME this data may be out of date please check and update it.

In Evolution there is a problem in that location names are not localisable.
Bug `#89746 <http://bugzilla.gnome.org/show_bug.cgi?id=89746>`_ refers to this
problem.

.. _../pages/guide/weather_applications#where_do_you_get_the_data:

Where do you get the data
=========================

More pressing then the localisability is the fact that many localitions are
missing for countries.  The data is easily retreived. Use the following URLs to
identify weather stations in yor country and locations.

You may have to correct a few where names have changed eg airport names or to
reflect to a normal user not an aeroplane pilot where this site is located.

* https://www.notams.jcs.mil/common/icao/index.html -- This is a good listing
  of sites sorted by country
* http://www.nws.noaa.gov/oso/site.shtml -- Contains downloadable ASCII version
  and instructions on obtaining hardcopy versions - downloadable version seems
  to be missing
* http://www.wapf.com/world/FALA.html -- Produces nice maps and proximity to
  other stations to help you identify the location.
* http://www.partow.net/miscellaneous/airportdatabase/ -- A database
  representation of the ICAO codes.
* http://weather.noaa.gov/weather/metar.shtml -- You can retreive data from
  multiple stations.  Usefull to check whether the ICAO code is valid for
  weather data.
* http://weather.noaa.gov/cgi-bin/mgetmetar.pl?cccc=FAJS -- The actual URL used
  by :doc:`gweather` to retreive weather data.

Please also check the data of the weather, it might be so out of date that it
is not valid.


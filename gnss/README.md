# GNSS

* [An Introduction to GNSS](https://www.novatel.com/an-introduction-to-gnss)
* [Navipedia](https://gssc.esa.int/navipedia/index.php/Main_Page)

GNSS Systems:

* GPS (United States)
* GLONASS (Russia)
* BeiDou (China)
* Galileo GNSS system (European Union)
* IRNSS regional navigation satellite system (India)
* QZSS regional navigation satellite system (Japan)

-----

# RTK

DGPS stands for Differential GPS. It is the GPS signal corrected by ground reference stations (which can estimate the ionosphere error on the GPS signal). Traditionally, DGPS accuracy can go down to sub-meter level. RTK technique allows DGPS accuracy to be at centimeter-level.

RTK stands for Real Time Kinematic. RTK algorithms make use of the carrier phase measurement to estimate accurately the distance from the receiver to the satellites. It allows an accuracy of 1-2 cm on position.

# Software

* [GeographicLib](https://geographiclib.sourceforge.io/) is a small set of C++ classes for performing conversions between geographic, UTM, UPS, MGRS, geocentric, and local cartesian coordinates, for gravity (e.g., EGM2008), geoid height, and geomagnetic field (e.g., WMM2010) calculations, and for solving geodesic problems.

* [RTKLIB](http://www.rtklib.com/): An Open Source Program Package for GNSS Positioning

* [GPSoftNav](https://gpsoftnav.com/)

* [gpsd](https://gpsd.gitlab.io/gpsd/) is a service daemon that monitors one or more GPSes or AIS receivers attached to a host computer through serial or USB ports, making all data on the location/course/velocity of the sensors available to be queried on TCP port 2947 of the host computer.

# Introduction #

The current implementation displays a GPS marker
![http://gmapcatcher.googlecode.com/svn/trunk/images/marker_gps.png](http://gmapcatcher.googlecode.com/svn/trunk/images/marker_gps.png)
and can auto center the map to the GPS location.

The GPS functionality is supported using the gps daemon: http://gpsd.berlios.de .

If a GPS unit is properly installed and the gps daemon is running the GPS menu will show up in the main menu when gmapcatcher is started.

![http://gmapcatcher.googlecode.com/svn/wiki/GPSv0.4.png](http://gmapcatcher.googlecode.com/svn/wiki/GPSv0.4.png)

## Compatible Devices ##
A List of compatible and tested devices is here:
http://gpsd.berlios.de/hardware.html

# Starting gmapcatcher with GPS #
  * Start GPS daemon (bluetooth GPS): _sudo gpsd -D 5 -nN /dev/rfcomm0_
  * Start gmapcatcher

# Installation of the GPS daemon #
  * Ubuntu: _sudo apt-get install python-gps_
  * Windows: Download and install [GPSd for Windows](http://code.google.com/p/gpsd-4-win/)

# Installation of bluetooth GPS #
  * Run _hcitool scan_ to find the GPS id on the form xx:xx:xx:xx:xx:xx.
  * Edit _/etc/bluetooth/rfcomm.conf_ and add the following:
```
rfcomm0 {
  bind yes; 
  device _xx:xx:xx:xx:xx:xx_; 
  channel 1; 
  comment "BT GPS"; 
}
```
  * Restart bluetooth: _sudo /etc/init.d/bluetooth restart_
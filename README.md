sweb
====

sweb (Simple WEb Browser) is a fullscreen web browser with no controls, it's designed to be used as an embedded device frontend or for signage or kiosk applications.

This project uses QT/Webkit and is based on one of the QT example projects (fancybrowser). The reason this project was created was that in the case where we have been wanting to just display a single web page, other web browsers running in fullscreen or kiosk mode were too demanding of system resources and we did not need many (if any) of the features offered by those browsers. So we trialed creating a simple fullscreen webkit based browser (sweb). It's worked great for us so far taking up far less system resources, although we're still testing it. When I mentioned this project to others they were very interested in using it, so here it is...

Building and running
====================

This has been tested with libqt4 and libqt4.8, I'd recommend 4.8 several people have shown interest in running this on the Raspberry Pi, as the current distro of choice for the Pi is raspbian which is based on Debian Wheezy and comes with libqt4.8 it should be as simple as the following to get it to run:

'''
  sudo apt-get install libqt4-webkit
  git clone https://github.com/csldevices/sweb.git
  cd sweb
  qmake
  make
  ./sweb
'''

I haven't tested the above on a raspberry pi specfically but it should work fine, for none debian based systems ignore the first step and instead install qt4 and libqt-webkit using your distributions favourite pacakge manager. I guess this should work on other platforms than Linux, ie. any platfrom the Qt toolkit runs on but again, not been tested.

By default sweb tries to load whatever is running on port 80 of the local machine, but if you pass a url on the command line it will go to that instead, so:

  ./sweb http://www.google.com

There is no built in method to exit sweb so you'll need to kill it from a command line.

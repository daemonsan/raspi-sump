Raspi-sump is a sump pit water level monitoring system using a Raspberry Pi and an 
Ultrasonic Sensor (HC-SR04)


![alt tag](http://www.linuxnorth.org/raspi-sump/images/raspi-chart.png)


Currently the system monitors the water level in your pit at defined intervals. It sends
email sms alerts if the water reaches a critical level, indicating a possible sump pump failure.

New Version 1.0.0 Python3 compatible 
=====================================


See the [changelog](https://github.com/alaudet/raspi-sump/blob/master/changelog) 
for changes to all versions.



QUICK INSTALL 
=============

Python 3 Recommended for Raspbian Jessie
=====================================
Install the pip package manager (if not present on your pi).

    sudo apt-get install python3-pip


Install Raspi-Sump.

    sudo pip3 install raspisump

Upgrading an existing version


    sudo pip3 install -U raspisump

This will also install the [HCSR04sensor](https://github.com/alaudet/hcsr04sensor) and  RPi.GPIO modules if not present on your Pi.

If you want to use charts install maplotlib.

    sudo apt-get install python3-matplotlib


Matplotlib should install Numpy.  If you need to install Numpy seperately;

    sudo apt-get install python3-numpy

Read the configuration docs copied during setup on your pi at the following location;

    /home/pi/raspi-sump/docs

They are also available on github https://github.com/alaudet/raspi-sump/blob/master/docs/install.md


Upgrading from Python2 to Python3 (Raspbian Jessie)
=================================

    sudo pip uninstall raspisump
    sudo pip3 install raspisump


Your configuration file will be preserved in /home/pi/raspi-sump/


Python2 install
===============

Recommended for Raspbian Wheezy
===============================

Raspi-sump was originally written in Python 2 and is still compatible with the
older version.

On Raspbian Wheezy it may be better to just stick with Python 2 as there are no
packaged versions of python3-matplotlib.  You will have to install it manually
with pip3.2.

Matplotlib can be a little tricky when installing with pip.  It depends on many
packages and requires some fiddling to get to work.  It's just easier to use
apt-get.  However it will work fine with Python3 if you manage to install
matplotlib.  There is no extra functionality in the Python3 version of
Raspi-Sump, it's just a compatibility upgrade.  If Python2 version is working
fine for you right now you could just stick with it as it will continue to be
identical.

To run in python 2 install with pip instead of pip3

    sudo pip install raspisump

All apt-get installs should be done with;

    sudo apt-get install python-<package name>

More Info
=========
Further details provided at http://www.linuxnorth.org/raspi-sump/

An example hourly updating graph is available for view.
http://www.linuxnorth.org/raspi-sump/raspi-sump-today.html

Disclaimer
==========
You are welcome to use Raspi-Sump but there is no guarantee it will work. Your house may still flood if your sump pump fails. This software comes with no warranty. See License details.

This is not a replacement for remaining vigilant in maintaining your water pumping system. It is one tool you can use to give yourself extra piece-of-mind.

Best practices should also include:

* A backup pump that triggers at a slightly higher water level than your main pump.
* The secondary pump should be connected to a seperate dedicated electrical breaker. 
* You should also have a generator that can provide power should you have an extended outage during the spring or other unseasonally wet time of year.
* if you are building a new home, pay attention to the grade of your property, as you may even be able to let gravity empty your pit for you.  That would be the best approach with a backup pump just in case. 

Once you have done all of these things, then consider using a monitoring system like Raspi-Sump.

License
=======
MIT License.  I want you to do whatever you want with Raspi-Sump.  If you
improve it please let me know.

Contributing
============
If you add a useful feature please consider forking Raspi-Sump and contributing
back by issuing a Pull Request.   Use the devel branch for adding new features
and if it works I will merge them into Master.

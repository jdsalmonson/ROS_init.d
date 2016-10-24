#ROS_init.d

These init files are for starting roscore and a real time
clock on Ubuntu for raspberry pi.

Edit the rtchwclock file to set your i2c device and address in the
DEVTYPE and DEVADDR variables. These are currently set for a ds3231
at the address 0x68.

Edit the shutdown_pi.py to set the GPIO pin for polling the shutdown signal.
Info of this file can be found at:
https://www.element14.com/community/docs/DOC-78055/l/adding-a-shutdown-button-to-the-raspberry-pi-b

Copy these files to /etc/init.d:

cd ROS_init.d

sudo cp * /etc/init.d

sudo chmod ugo+rx /etc/init.d/roscore 

sudo chmod ugo+rx /etc/init.d/rtchwclock 

Add the scripts to the init system:

sudo update-rc.d rtchwclock defaults 15

sudo update-rc.d roscore defaults

sudo update-rc.d pishutdown defaults

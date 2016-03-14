#ROS_init.d

These init files are for starting roscore and a real time
clock on Ubunutu for raspberry pi.

Edit the rtchwclock file to set your i2c device and address in the
DEVTYPE and DEVADDR variables. These are currently set for a ds3231
at the address 0x69.

Copy these files to /etc/init.d:

cd ROS_init.d
sudo cp * /etc/init.d
sudo chmod ugo+rx /etc/*

Add the scripts to the init system:
sudo update-rc.d rtchwclock defaults 15
sudo update-rc.d roscore defaults

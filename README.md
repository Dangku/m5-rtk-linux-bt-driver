# rtk-linux-driver

----------
**Prepare**

Realtek Blutooth UART and USB driver in Linux system, supported kernel version is 2.6.32 - 5.7.1

Please Install the following packages for Ubuntu Server or Debian before build

    $ sudo apt update
    $ sudo apt install -y make gcc git bluez bluez-tools bluetooth rfkill

Correctly setup the uart pins for uart device. 

**Build**

Build/Install uart or usb bluetooth driver, install firmware files and  hciuart systemd service 

    $ sudo make install INTERFACE=usb         //for usb
    $ sudo make install INTERFACE=uart        //for uart
  
 After build successfully, usb driver will be loaded automatically when device plugin. For uart device,  the hciuart service must be started before use.

    $ sudo systemctl start rtk-hciuart.service
    $ sudo systemctl enable rtk-hciuart.service

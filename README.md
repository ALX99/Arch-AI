# Arch-AI

Quick and easy Arch Linux installation script aimed towards setting up the most useful and crucial things you will need on your system.  
It should *probably* work right now if you want to use it but I'm continuously improving it when I have time.

**Pull requests are welcome**

## Features

* Drive formatting
* User account  & hostname & sudo setup
* WM/DE installation
* Option to install additional common packages
* Locale configuration and generation
* Error log

### Things that are done without input

* Obtains fastest mirror before install
* GPU driver detection + installation
* Timezone + clock setup
* GRUB installation
* Xorg setup (No DM used)

## TODO

* root password is currently none I believe
* Partition size selection
* LUKS encryption
* Better dialog experience
* Option to change DNS server?

## Not working

* i3 doesn't work since there is some package missing...

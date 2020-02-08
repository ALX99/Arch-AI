# Arch-AI

Quick and easy Arch Linux installation script aimed towards setting up the most useful and crucial things you will need on your system.  
It should _probably_ work right now if you want to use it but I'm continuously improving it when I have time.

**Pull requests are welcome**

## Why

I do realize there several other popular automatic Arch Linux install scripts out there but most of them seem unnecessarily complex and annoying to use.  
This automatic installation script focuses primarily on user-friendliness. It will set up and install sensible without asking you such as Network Manager, separating the / and /home in different partitions, configuring the timezone and downloading the appropriate GPU drivers for your GPU without you having to specify it.

It'll only primarily focus on core OS features many people use, things such as manually specifying different partitions _might_ never be supported.

Furthermore, all the user interaction is done at the beginning, so after answering those questions you could go get a coffee and come back to a fully set up Arch Linux system ready to use.

## Features

- Automatic drive formatting
- User account & hostname & sudo setup
- WM/DE installation
- Option to install additional common packages
- Locale configuration and generation
- Error log

### Things that are done without user input

- Obtains fastest mirror before install
- GPU driver detection + installation
- Timezone + clock setup
- GRUB installation
- yay installation

#### List of packages that are always installed without asking

- linux
- linux-firmware
- base
- base-devel
- xorg-server
- xorg-xinit
- xorg-xrandr
- grub
- networkmanager
- git

## TODO

- ~~root password is currently none I believe~~
- ~~Partition size selection~~
- Partition naming
- Sudo configuration settings
- Option to install a DM
- ~~Install [yay](https://github.com/Jguer/yay) in setup~~
- LUKS encryption
- Better dialog experience
- Option to change DNS server?

## Not working

- i3 doesn't work since there are some package missing...

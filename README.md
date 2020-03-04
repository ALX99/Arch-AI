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
- GPU detection + installation
- CPU detection + microcode installation
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
- go (dependency of yay)

## TODO

- ~~root password is currently none I believe~~
- ~~Partition size selection~~
- ~~Partition naming~~
- Option to install a DM
- ~~Install [yay](https://github.com/Jguer/yay) in setup~~
- Better dialog experience
- Option to change DNS server
- [NVIDIA DRM kernel modesetting](https://wiki.archlinux.org/index.php/NVIDIA#DRM_kernel_mode_setting)

### Might do

- LUKS encryption

### Scratched

- Sudo configuration settings  
  - Your user will be added to the wheels group which will have sudo access, which is enough for most people

## Not working

- i3 doesn't work since there are some package(s) missing...

### Problems

The `out` function is the same in both `install` and `setup`, but can't be placed in `sharedfuncs` since it uses variables set by the script. These variables can't be exported in the first script since we'll chroot to a different environment.

# Arch-AI

Quick and easy Arch Linux installation script aimed towards setting up the most useful and crucial things you will need on your system.  
The script is continuously being developed in the `develop` branch whenever I have motivation and time. I aim to keep the master branch as bug-free as possible, but no promises.

## Preview

[![asciicast](https://asciinema.org/a/307557.svg)](https://asciinema.org/a/307557)  
Finally ready to install Arch Linux?

```shell
wget -O- cutt.ly/Arch | bash; ./install
```

## Why

I do realize there exists several other popular automatic Arch Linux install scripts out there but most of them appear unnecessarily complex and seem annoying to use to me.  
This automatic installation script focuses primarily on user-friendliness. It will set up and install sensible packages without asking you such as Network Manager, sudo and git.  
It'll also separate the / and /home directories in different partitions, configure the timezone automatically and download the drivers for your GPU.

The script will primarily focus on core OS features many people use, things such as manually specifying different partitions _might_ never be supported.

Furthermore, all the user interaction is done at the beginning, so after answering the questions you could go get a coffee and come back to a fully set up Arch Linux system ready to use.

## Features

- Automatic drive formatting
- User account & hostname & sudo setup
- Timezone + clock setup
- CPU detection + microcode installation
- GPU detection + installation
- GRUB installation
- yay installation
- Option to install additional common packages
- Option to auto-trim mounted SSDs once a week
- Option to configure parallel and optimized compilation&compression for makepkg
- Locale configuration and generation
- Obtains fastest mirror before install
- Error log

### List of packages that are always installed without asking

- linux
- linux-firmware
- base
- base-devel
- xorg-server
- xorg-xinit
- xorg-xrandr
- grub
- networkmanager
- git (required to install yay)
- go (required to yay)

## TODO

- ~~root password is currently none I believe~~
- ~~Partition size selection~~
- ~~Partition naming~~
- ~~Install [yay](https://github.com/Jguer/yay) in setup~~
- ~~Better dialog experience~~
- ~~Option to change DNS server~~
  - The user will set this through Network if he so chooses
- Hibernation

### Might do

- LUKS encryption
- [NVIDIA DRM kernel modesetting](https://wiki.archlinux.org/index.php/NVIDIA#DRM_kernel_mode_setting)
- AMDGPU SI & CIK detection & module paramaters & kernel paramaters
- HP computer detection on UEFI boot & prompt user that they need to change the "customized boot" option the UEFI

### Scratched

- Sudo configuration settings
  - Your user will be added to the wheels group which will have sudo access, which is enough for most people

### Problems

The `out` function is the same in both `install` and `setup`, but can't be placed in `sharedfuncs` since it uses variables set by the script. These variables can't be exported in the first script since we'll chroot to a different environment.

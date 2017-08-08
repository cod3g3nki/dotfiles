# dotfiles
## Development environmet config files

A collection of config files used to setup and maintain a uniform development environment accross different machines.

## Contents
- bashrc script
- Conky config
- i3 tiling WM config

## Requirements & Dependencies
1. ### bashrc
   copy bashrc script file to your home directory and add a source line in
.bshrc file:
   ```bash
   source .bashrc.cpwd.sh
   ```
   For changes to take effect either run ```source ~/.bashrc``` from terminal or logout and login.

   #### Screenshot

   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/shell-shot.png "Bash prompt")

2. ### conky 1.10+
   Depends on *conky*, *curl*, *jq*, *vnstat*  
   To setup *vnstat* on Debian/Ubuntu, install from default repo:
   ```bash
   sudo apt-get install vnstat
   ```
   *vnstat* initializes a db, for each network interface, in
   ```/var/lib/vnstat```. To monitor an interface (say eth0), create a new db for it as:
   ```bash
   vnstat --create -i eth0
   ```
   To avoid *Permission denied* errors while querying vnstat data, change
ownership of db files to *vnstat* user:group pair.  
   ```bash
   sudo chown vnstat:vnstat /var/lib/vnstat/*
   ```
   After setting up dependencies, move .conky directory to your home. Add
   ```.conky/conky-startup.sh``` as a autostart application from system settings.

   #### Screenshots
   **minimal# Hydrogen**
   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_minH_shot.png ".conkyrc_minH")

   **minimal# Helium**
   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_minHe_shot.png ".conkyrc_minHe")


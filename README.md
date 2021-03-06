# dotfiles
## Development environment config files

A collection of config files used to setup and maintain a uniform development environment across different machines.

## Contents
- bashrc script
- Conky config
- i3 tiling WM config

## Requirements & Dependencies
### 1. bashrc
   copy either of the two `bashrc` script files to your home directory and add a source line in `~/.bashrc` file:
   ```bash
source .bashrc.env.sh
   ```
   For changes to take effect either run ```source ~/.bashrc``` from terminal or logout and login.

​	Both files, in addition to custom aliases and functions, print a custom prompt and are differentiated as follows:


- `.bashrc.cpwd.sh` prints a shell script based simple prompt

![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/shell-shot.png "Bash prompt")

- `.bashrc.env.sh` prints a `powerline-shell` based prompt that can be installed via terminal by the command:

    ```bash
    pip install powerline-shell
    ```

![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/powershell-shot.png "Bash prompt")

### 2. Conky Config

#### minimal# X, mixCxx

   Depends on: *conky* (>= 1.10), *curl*, *jq*, *vnstat*

#### SpaceX

   Depends on: *conky* (>= 1.10), *Python 3* (for optional `apt` script)

#### StarWarp

   Depends on: *conky* (>= 1.10), *curl*, *jq*, *vnstat*, *Python 3* (for optional `apt` script)

##### Setup dependencies
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
   For weather updates and forcasts get an API key from [OpenWeatherMap](https://openweathermap.org "OpenWeatherMap's Homepage")
   and find [city id](http://openweathermap.org/help/city_list.txt "City ID List")  for city of your choice. Substitute these values against
   *template1* and *template2* variables in conkyrc file.

##### Autostart conky on startup

After setting up dependencies, move conky configuration directory (e.g. spacex) to `~/.conky`. Edit `.conky/conky-startup.sh` file and substitute name of the script that launches configuration file of your choice. Add ```.conky/conky-startup.sh``` as a autostart application from system settings.

   ##### Screenshot Gallery
   ###### minimal# Hydrogen

   ###### ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_minH_shot.png "conkyrc_minH")

   ###### minimal# Helium

   ###### ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_minHe_shot.png "conkyrc_minHe")

   ###### minimal# Hydrogen Icon Mix

   ###### ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_minH_mix_shot.png "conkyrc_minH_mix")

   ###### minimal# Carbon
   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_mixC12_shot.png "conkyrc_mixC12")

   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_mixC13_shot.png "conkyrc_mixC13")

   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/conkyrc_mixC14_shot.png "conkyrc_mixC14")

   ###### SpaceX

   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/spacex_sys.png "spacex_sys")

   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/spacex_os.png "spacex_os")

   ##### StarWarp
   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/starwarp-loaded00.png "starwarp desktop")
   ![alt text](https://github.com/cod3g3nki/dotfiles/raw/master/starwarp-loaded02.png "starwarp desktop")


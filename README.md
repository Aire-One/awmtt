# awmtt
awmtt (AwesomeWM Testing Tool) is a bash script that helps you test your Awesome configuration files.  
It requires Xephyr, an Xorg-Application which can spawn a nested instance of xorg-server, allowing you to open multiple instances of Desktop Environments or Window Mangers like AwesomeWM.  

### Installation
ArchLinux users can find awmtt in the [AUR](https://aur.archlinux.org/packages/awmtt/).

Example Debian/Ubuntu manual installation:
``` bash
sudo apt-get install xserver-xephyr
sudo wget -O /usr/bin/awmtt https://raw.githubusercontent.com/mikar/awmtt/master/awmtt.sh
sudo chmod a+x /usr/bin/awmtt
```

### Screenshot
Here's an example of what it looks like:  
![ScreenShot](https://github.com/mikar/awmtt/blob/master/example.jpg)

### Usage
```
awmtt (start | stop [all] | restart) [-B <path>] [-C <path>] [-D <int>] [-S <size>] [-e <cmd>] [-o <opt>]
awmtt theme (get | set <theme> | list | random)

Arguments:
  start           Spawn nested Awesome via Xephyr
  stop            Stops the last Xephyr process
    all           Stop all instances of Xephyr 
  restart         Restart all instances of Xephyr
  theme           Some basic theming control via:
    get           Get current theme name
    set <theme>   Set theme to <theme>
    list          List available themes
    random        Set a random theme
    
Options:
  -B|--binary <path>  Specify path to awesome binary (for testing custom awesome builds)
  -C|--config <path>  Specify configuration file
  -D|--display <int>  Specify the display to use (e.g. 1)
  -S|--size <size>    Specify the window size
  -N|--notest         Don't use a testfile but your actual rc.lua (i.e. $HOME/.config/awesome/rc.lua)
  -e|--execute <cmd>  Execute command in nested Awesome
  -o|--options <opt>  Pass options to awesome binary (e.g. --no-argb or --check)
  -h|--help           Show this help text
  
Examples:
  awmtt start (uses defaults: -D 1 -C $HOME/.config/awesome/rc.lua.test -S 1024x640)
  awmtt start -D 3 -C /etc/xdg/awesome/rc.lua -S 1280x800
  awmtt theme set zenburn
```

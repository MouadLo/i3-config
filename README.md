# setupi3

This is an experimental project to setup up a nice i3 desktop environment running on Ubuntu .


## Usage:


### Install i3
```
sudo apt-get update
sudo apt-get install i3 i3-wm i3blocks i3lock i3status 
```

### Configure

The configure file for i3 is located (by default) at:
```
~/.config/i3/config
```



### Enable multimedia keys

1. Install *pactl*, *xbacklight*: 
```
sudo apt-get install  xbacklight
```

2. Install *playerctl*:

Download the package from:
https://github.com/acrisci/playerctl/releases

Then `sudo dpkg -i the_package.deb`



### [Optional] Set custom wallpaper

The line for setting custom wallpaper has been added (but commented)
out in the config file.

Before activating that line, need to install *feh*:
```
sudo apt-get install feh
```


### Bound an app to a workspace

A certain app will be launched only in a specified workspace.
Take the *firefox* for example.

1. Launch firefox, and an empty terminal.
2. In the terminal, run `xprop`, then click the firefox window to
   show the app info. Look for the line "WM_CLASS(STRING)", and
   take a note of the 2nd field, for firefox it's "Firefox".
3. In the config file, add
```
assign [class="Firefox"] $workspace1
```


### Install *Font Awesome*

This is to enable icons in workspace names, as defined in
the i3 config file.

1. Go to `https://github.com/FortAwesome/Font-Awesome/releases`
and download the font file zip.

2. copy the .ttf font files from fonts/ folder to `/usr/local/share/fonts`.



### Apply the system font to GTK applications.

1. Install lxappearance
```
sudo apt-get install lxappearance
```
2. Launch lxappearance, and set **Default font** to **SFNS Display**.



### Install *Arch GTK* theme

```
sudo apt-get install arc-theme
```


### Install *Rofi*, as a replacement of *dmenu*

1. Install `sudo apt-get install rofi`
2. Replace `dmenu_run` command with a rofi command in the i3 config file.


### Install *compton*, to enable transparency effect of *rofi*

1. Install `sudo apt-get install compton`
2. Add `exec_always compton -f` in the i3 config file


### Customize bar using i3blocks instead of i3status

The default status bar is updated using *i3status*. Change this to *i3blocks* which is easier to control.

1. Copy the default *i3blocks* config file:
```
cp i3blocks.conf ~/.config/i3/
```



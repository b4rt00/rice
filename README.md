## Basic terminal programs
```sh
sudo apt install neofetch htop cowsay cmatrix
```


## VIMRC
```sh
curl https://raw.githubusercontent.com/b4rt00/dotfiles/main/vimrc > .vimrc
```


## VIM PLUG
```sh
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
In VIM:
```
:PlugInstall
```

## ZSH shell
```sh
sudo apt install zsh
sudo chsh -s /usr/bin/zsh root
sudo chsh -s /usr/bin/zsh b4rt00
```

## Oh My ZSH
```sh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

Edit `.zshrc`
```
plugins=(zsh-autosuggestions)
```

Load new configuration
```sh
source .zshrc
```

## GUI Tools
```sh
sudo apt install gedit terminator pcmanfm qutebrowser rofi
```


## OpenBox and stuff
```sh
sudo apt install openbox obconf lightdm nitrogen lxappearance tint2
```

## Openbox autostart
In `~/.config/openbox/autostart`
```
tint2 &
nitrogen --restore
```

## Remove unnecessary directories
```sh
rm -rf Public Templates Videos Music
```

## Wallpaper
```sh
wget https://wallpapercave.com/wp/3vZjpA5.jpg -O ~/Pictures/plain.jpg
wget https://wallpapercave.com/wp/wp5480654.jpg -O ~/Pictures/circle.jpg
wget https://wallpapercave.com/wp/wp5187908.jpg -O ~/Pictures/wave.jpg
```
Change the wallpaper using `nitrogen`.


## Arrow Snap
In file `~/.config/openbox/rc.xml`
Insert before `<keybind key="C-A-Left">`
```xml
<keybind key="W-Left">
  <action name="UnmaximizeFull"/>
  <action name="MaximizeVert"/>
  <action name="MoveResizeTo">
    <width>50%</width>
  </action>
  <action name="MoveToEdgeWest"/>
</keybind>
<keybind key="W-Right">
  <action name="UnmaximizeFull"/>
  <action name="MaximizeVert"/>
  <action name="MoveResizeTo">
    <width>50%</width>
  </action>
  <action name="MoveToEdgeEast"/>
</keybind>
```


## Terminator config
Create terminator folder in `.config`.
```sh
mkdir ~/.config/terminator
```
Insert the following content to `~/.config/terminator/config`
```sh
[global_config]
[keybindings]
  go_next = <Super>bracketright
  go_prev = <Super>bracketleft
  split_horiz = <Shift><Super>d
  split_vert = <Super>d
[profiles]
  [[default]]
    background_color = "#282828"
    background_darkness = 0.85
    background_type = transparent
    cursor_color = "#aaaaaa"
    font = monospace 11
    foreground_color = "#ebdbb2"
    show_titlebar = False
    scrollbar_position = hidden
    scrollback_lines = 5000
    palette = "#282828:#cc241d:#98971a:#d79921:#458588:#b16286:#689d6a:#a89984:#928374:#fb4934:#b8bb26:#fabd2f:#83a598:#d3869b:#8ec07c:#ebdbb2"
[layouts]
  [[default]]
    [[[window0]]]
      type = Window
      parent = ""
    [[[child1]]]
      type = Terminal
      parent = window0
[plugins]
```


## OpenBox Themes
```sh
git clone https://github.com/addy-dclxvi/openbox-theme-collections ~/.themes
```
Change the theme using `obconf`.


## Tint2 Themes
```sh
rm -rf ~/.config/tint2
git clone https://github.com/addy-dclxvi/tint2-theme-collections ~/.config/tint2 --depth 1
cp ~/.config/tint2/minima/minima.tint2rc ~/.config/tint2/tint2rc
```


## GTK Adwaita-Dark
```sh
sudo apt-get install gnome-themes-extra
```
Change GTK theme using `lxappearance`.


## Numix Icon Theme
```sh
sudo apt install numix-icon-theme
```
Change icon theme using `lxappearance`.


## ROFI
Bind rofi to the key combination of your choosing by inserting this in `~/.config/openbox/rc.xml`.
```
<keybind key="W-space">
    <action name="Execute">
        <command>rofi -show drun</command>
    </action>
</keybind>
```
To use `alt` instead of `super` change `W-space` to `A-space`.

Change Rofi theme 
```sh
rofi-theme-selector
```


## Obmenu config
Paste the following file in `/etc/xdg/openbox/menu.xml`
```xml
<?xml version="1.0" encoding="UTF-8"?>

<openbox_menu xmlns="http://openbox.org/"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://openbox.org/
                file:///usr/share/openbox/menu.xsd">

<menu id="root-menu" label="Openbox 3">
  <item label="Terminal">
    <action name="Execute"><execute>terminator</execute></action>
  </item>
  <item label="Web browser">
    <action name="Execute"><execute>qutebrowser</execute></action>
  </item>
  <item label="File Manager">
    <action name="Execute"><execute>pcmanfm</execute></action>
  </item>
  <item label="Text Editor">
    <action name="Execute"><execute>gedit</execute></action>
  </item>
  <item label="Exit">
    <action name="Exit" />
  </item>
</menu>

</openbox_menu>
```



















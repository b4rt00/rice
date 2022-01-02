## Basic terminal programs
```
$ sudo apt install neofetch htop cowsay cmatrix
```


## VIMRC
```
$ curl https://raw.githubusercontent.com/b4rt00/dotfiles/main/vimrc > .vimrc
```


## VIM PLUG
```
$ curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
In VIM:
```
:PlugInstall
```

## ZSH shell
```
$ sudo apt install zsh
$ sudo chsh -s /usr/bin/zsh root
$ sudo chsh -s /usr/bin/zsh b4rt00
```

## Oh My ZSH
```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
$ git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

Edit .zshrc
```
73 plugins=(zsh-autosuggestions)
```

```
$ source .zshrc
```

## GUI Tools
```
sudo apt install gedit terminator pcmanfm qutebrowser rofi
```


## OpenBox and stuff
```
sudo apt install openbox obconf lightdm nitrogen lxappearance tint2
```

## Openbox autostart
In `~/.config/openbox/autostart`
```
tint2 &
nitrogen --restore
```


## Wallpaper
```
wget https://wallpapercave.com/wp/3vZjpA5.jpg -O ~/Pictures/plain.jpg
wget https://wallpapercave.com/wp/wp5480654.jpg -O ~/Pictures/circle.jpg
wget https://wallpapercave.com/wp/wp5187908.jpg -O ~/Pictures/wave.jpg
```


## Arrow Snap
In file ~/.config/openbox/rc.xml
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


## OpenBox Themes
```
git clone https://github.com/addy-dclxvi/openbox-theme-collections ~/.themes
```


## Tint2 Themes
```
rm -rf ~/.config/tint2
git clone https://github.com/addy-dclxvi/tint2-theme-collections ~/.config/tint2 --depth 1
cp ~/.config/tint2/minima/minima.tint2rc ~/.config/tint2/tint2rc
```


## GTK Adwaita-Dark
Run the following script
```sh
# default theme broken and not available after upgrade from ubuntu 18.04
# running these two commands seems to fix it
sudo apt-get --reinstall install ubuntu-session
sudo apt-get --reinstall install yaru-*
# optionally reset everything
dconf reset -f /org/gnome/
# tweak tool to select theme
sudo apt-get install gnome-tweak
# add adwaita-dark theme variant
sudo apt-get install gnome-themes-extra
# open tweaks and go to Appearance and select Adwaita-dark
gnome-tweaks
# also set gtk default
vim ~/.config/gtk-3.0/settings.ini
# set: gtk-application-prefer-dark-theme=1
```


## Numix Icon Theme
```
sudo apt install numix-icon-theme
```

### Bash Config

add to `$HOME/.bash_profile` to use bash config in `$HOME/.bashrc`
```sh
if [ -n "$BASH_VERSION" ]; then
    # include .bashrc if it exists
    if [ -f "$HOME/.bashrc" ]; then
        . "$HOME/.bashrc"
    fi
fi
```

### Autostart X at Login

add to `$HOME/.bash_profile`
```sh
if systemctl -q is-active graphical.target && [[ ! $DISPLAY && $XDG_VTNR -eq 1 ]]; then
  exec startx
fi
```

### i3wm Config

Display

`exec_always --no-startup-id xrandr --output Virtual-l --mode 1920*1080`

Wallpaper

`exec_always --no-startup-id feh --bg-fill <path to wallpaper>`


### Load .Xresources

add to .xinitrc before any exec line

`[[ -f ~/.Xresources ]] && xrdb -merge -I$HOME ~/.Xresources`

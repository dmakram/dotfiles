# dotfiles README
![dotfiles](https://github.com/dmakram/dotfiles/blob/main/assets/preview.png)

This is my dotfiles, it contains the configuration files for hyprland, waybar, kitty, mako. I try to keep it simple and change it slightly over time when I find things need to change. As Design is very important to me.

Required packages:
- hyprland
- waybar
- kitty
- mako
- swww

# TODO:
- Copy the files in the .config/ to your home directory.
- install the required packages.
- restart the computer and login to the hyprland session.

Editable/ Customizable files:
- ~/.config/hypr/hyprland.conf
- ~/.config/waybar/config
- ~/.config/kitty/kitty.conf
- ~/.config/mako/config

## hyprland.conf:

This file contains the configuration for hyprland. It is a configuration file for hyprland.

Here you can edit what opens on startup.
```hyprland.conf
#################
### AUTOSTART ###
#################

# Autostart necessary processes (like notifications daemons, status bars, etc.)
# Or execute your favorite apps at launch like this:

exec-once = $terminal
exec-once = nm-applet # this is the network manager applet
exec-once = waybar & hyprpaper # this is the waybar at the top and the hyprpaper is the wallpaper system
```
These are examples of how to user the shortcuts.
```hyprland.conf
# Example binds, SUPER is the windows key
SUPER + R = Application launcher
SUPER + T = terminal
SUPER + SHIFT + T = nvim
SUPER + C = browser
SUPER + G = Gemini AI
SUPER + O = obsidian
SUPER + SHIFT + O = obsidian quicknotes
SUPER + SHIFT + G = Gemini AI
SUPER + Q = kill active window
SUPER + L = logout
SUPER + E = file manager
SUPER + V = toggle floating
SUPER + P = dwindle pseudo
SUPER + J = dwindle split
SUPER + K = dwindle split
SUPER + F = fullscreen
SUPER + SHIFT + F = complete fullscreen
# Switch workspaces
SUPER + 1-9 = workspace 1-9
# Move active window to workspace
SUPER + SHIFT + 1-9 = movetoworkspace 1-9
# Move focus with mainMod + arrow keys
SUPER + left = movefocus left
SUPER + right = movefocus right
SUPER + up = movefocus up
SUPER + down = movefocus down

# Screenshot a window
PRINT = hyprshot -m window
# Screenshot a monitor
PRINT + SHIFT = hyprshot -m output
```
Here is where you set the programs you use and their bindings(shortcuts).
``` hyprland.conf
# Set programs that you use
$terminal = kitty
$fileManager = nautilus
$menu = wofi --show drun
$browser = /usr/bin/google-chrome-stable
$editor = $terminal -e nvim ~/Code/workspace/
$ai = $terminal -e gemini
$obsidian = obsidian
$quicknotes = $terminal -e nvim ~/Vaults/Personal/

# You can change the main modifier key
$mainMod = SUPER # Sets "Windows" key as main modifier

# Bindings
bind = $mainMod, T, exec, $terminal
bind = $mainMod SHIFT, T, exec, $editor
bind = $mainMod, O, exec, $obsidian
bind = $mainMod SHIFT, O, exec, $quicknotes
bind = $mainMod SHIFT, G, exec, $ai
bind = $mainMod, Q, killactive,
bind = $mainMod, L, exit,
bind = $mainMod, E, exec, $fileManager
bind = $mainMod, V, togglefloating,
bind = $mainMod, R, exec, $menu
bind = $mainMod, P, pseudo, # dwindle
bind = $mainMod, J, togglesplit, # dwindle
bind = $mainMod, K, togglesplit, # dwindle
bind = $mainMod, C, exec, $browser # Browser
bind = $mainMod, G, exec, $ai # Gemini AI
bind = $mainMod, F, fullscreen, 1
bind = $mainMod SHIFT, F, fullscreen, 0
# Screenshot a window
bind = SHIFT, PRINT, exec, hyprshot -m window
# Screenshot a monitor
bind = , PRINT, exec, hyprshot -m output
# Move focus with mainMod + arrow keys
bind = $mainMod, left, movefocus, l
bind = $mainMod, right, movefocus, r
bind = $mainMod, up, movefocus, u
bind = $mainMod, down, movefocus, d

# Switch workspaces with mainMod + [0-9]
bind = $mainMod, 1, workspace, 1
bind = $mainMod, 2, workspace, 2
bind = $mainMod, 3, workspace, 3
bind = $mainMod, 4, workspace, 4
bind = $mainMod, 5, workspace, 5
bind = $mainMod, 6, workspace, 6
bind = $mainMod, 7, workspace, 7
bind = $mainMod, 8, workspace, 8
bind = $mainMod, 9, workspace, 9
bind = $mainMod, 0, workspace, 10

# Move active window to a workspace with mainMod + SHIFT + [0-9]
bind = $mainMod SHIFT, 1, movetoworkspace, 1
bind = $mainMod SHIFT, 2, movetoworkspace, 2
bind = $mainMod SHIFT, 3, movetoworkspace, 3
bind = $mainMod SHIFT, 4, movetoworkspace, 4
bind = $mainMod SHIFT, 5, movetoworkspace, 5
bind = $mainMod SHIFT, 6, movetoworkspace, 6
bind = $mainMod SHIFT, 7, movetoworkspace, 7
bind = $mainMod SHIFT, 8, movetoworkspace, 8
bind = $mainMod SHIFT, 9, movetoworkspace, 9
bind = $mainMod SHIFT, 0, movetoworkspace, 10

# Example special workspace (scratchpad)
bind = $mainMod, S, togglespecialworkspace, magic
bind = $mainMod SHIFT, S, movetoworkspace, special:magic

# Scroll through existing workspaces with mainMod + scroll
bind = $mainMod, mouse_down, workspace, e+1
bind = $mainMod, mouse_up, workspace, e-1
```


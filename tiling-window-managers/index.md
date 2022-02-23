## Florian Begusch's tiling window managers config

### Darwin / Mac OS

#### Window manager

[Yabai](https://github.com/koekeishiya/yabai/) manages the Mac OS native Window manager:   
main config: [.yabairc](https://github.com/florianbegusch/dot-files/blob/1680d10bd9ccfe2071410cc933a6388715cafcb5/.yabairc)

#### Hotkeys | Key bindings

#### skhd hotkey daemon
I used to use [skhd](https://github.com/koekeishiya/skhd) (same developer as yabai), [.skhdrc keybindings](https://github.com/florianbegusch/dot-files/blob/cf154296e50119e8d06a1f2b8f45ebb4d6c594fd/.skhdrc).
But I prefer to do keybinding rewrites in one place and one place only.
Thus I wrote [custom keybindings](#karabiner-elements-keyboard-customizer-for-macos) for yabai in `Karabiner-Elements`.

**Hint**: If `skhd` stops working -> check if `Input Monitoring` is allowed for the `skhd` executable in `Security & Privacy` Settings

#### Karabiner-Elements
[Karabiner-Elements](https://github.com/pqrs-org/Karabiner-Elements) a keyboard customizer for macOS

`skhd` replacement:  
> Custom written [yabai bindings](https://github.com/florianbegusch/dot-files/blob/4aac67e7e445274004db207451b0f39fe0b8a0ad/.config/karabiner/assets/complex_modifications/skhd-replacement-for-yabai.json)

### Linux

I use i3-gaps. Config can be found in the following locations:

#### Main config

Hotkeys and workspace (virtual desktops) config; sets statusbar helper to `i3cat`

* [main i3 config](https://github.com/florianbegusch/dot-files/blob/79ab2e985900f60888de119171d02056c4f29231/.config/i3/config)
* [i3 startup via .xinitrc](https://github.com/florianbegusch/dot-files/blob/61fc984f9b7f332503755766a46bc5a84a58ff04/.xinitrc)

#### Statusbar config

[i3cat config](https://github.com/florianbegusch/dot-files/blob/011fa649ff02a2e470b3e495a903e65fc891c72f/.config/i3cat/config)

My `i3cat` config incorporates two `i3status` configs, among other things:  
  [i3 status configs](https://github.com/florianbegusch/dot-files/tree/b45e108a685225bdecd0dd2bd89f5beaf0ca45b9/.config/i3status)


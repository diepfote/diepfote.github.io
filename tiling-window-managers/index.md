## Florian Begusch's tiling window managers config

### Darwin / Mac OS

#### Window manager

[Yabai](https://github.com/koekeishiya/yabai/) manages the Mac OS native Window manager:   
[yabai config]()

#### Hotkeys

I tried to use [skhd](https://github.com/koekeishiya/skhd) (same developer) for several months now (hotkey daemon for yabai).  
Sadly it breaks on a regular basis (stops working after a few hours of running mac os) -> requires restarts

`skhd` replacement:  
[karabiner-elements](https://github.com/pqrs-org/Karabiner-Elements), [my yabai bindings](https://github.com/florianbegusch/dot-files/blob/4aac67e7e445274004db207451b0f39fe0b8a0ad/.config/karabiner/assets/complex_modifications/skhd-replacement-for-yabai.json)

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


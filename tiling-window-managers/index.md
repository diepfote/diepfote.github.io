Florian Sorko's tiling window managers config

#### Table of contents

1. [Darwin / Mac OS](#darwin--mac-os)
    - [Window manager](#window-manager)
    - [Hotkeys / Key bindings](#hotkeys--key-bindings)
    - [skhd hotkey daemon](#skhd-hotkey-daemon)
    - [Karabiner-Elements](#karabiner-elements)
2. [Linux](#linux)
    - [Main config](#main-config)
    - [Statusbar config](#statusbar-config)


# Darwin / Mac OS

## Window manager

[Yabai](https://github.com/koekeishiya/yabai/) manages the Mac OS native Window manager:   
main config: [.yabairc](https://github.com/diepfote/dot-files/blob/1680d10bd9ccfe2071410cc933a6388715cafcb5/.yabairc)

## Hotkeys / Key bindings

## skhd hotkey daemon
I used to use [skhd](https://github.com/koekeishiya/skhd) (same developer as yabai), [.skhdrc keybindings](https://github.com/diepfote/dot-files/blob/cf154296e50119e8d06a1f2b8f45ebb4d6c594fd/.skhdrc).
But I prefer to do keybinding rewrites in one place and one place only.
Thus I wrote [custom keybindings](#karabiner-elements) for yabai in `Karabiner-Elements`.

**Hint**: If `skhd` stops working -> check if `Input Monitoring` is allowed for the `skhd` executable in `Security & Privacy` Settings

## Karabiner-Elements
[Karabiner-Elements](https://github.com/pqrs-org/Karabiner-Elements) a keyboard customizer for macOS

`skhd` replacement:  
> Custom written [yabai bindings](https://github.com/diepfote/dot-files/blob/4aac67e7e445274004db207451b0f39fe0b8a0ad/.config/karabiner/assets/complex_modifications/skhd-replacement-for-yabai.json)

# Linux

I use [i3](https://github.com/Airblader/i3).
Config can be found in the sections below 

--

What it looks like

<img src="./i3-example.png" width="600" />

## Main config

This config sets hotkeys and workspace (virtual desktops) config.
It also sets a statusbar helper, [`i3cat`](https://vincent-petithory.github.io/i3cat/).
The main config can be found [here](https://github.com/diepfote/dot-files/blob/79ab2e985900f60888de119171d02056c4f29231/.config/i3/config).

i3 startup is handled via `.xinitrc`. This config lives [here](https://github.com/diepfote/dot-files/blob/61fc984f9b7f332503755766a46bc5a84a58ff04/.xinitrc).

## Statusbar config

* Uses [`i3cat`](https://vincent-petithory.github.io/i3cat/)
* Find `i3cat` config [here](https://github.com/diepfote/dot-files/blob/011fa649ff02a2e470b3e495a903e65fc891c72f/.config/i3cat/config)
* ^ this config uses two [i3status](https://i3wm.org/i3status/manpage.html) processes and a [separate script](https://github.com/diepfote/scripts/blob/91f7ac81f969e8158aedb6dea6662eefeead2a8c/i3cat-audio-device-helper.sh) to display audio levels.
Those `i3status` configs can be found [here](https://github.com/diepfote/dot-files/tree/b45e108a685225bdecd0dd2bd89f5beaf0ca45b9/.config/i3status).



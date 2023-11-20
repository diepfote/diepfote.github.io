Projects by Florian Sorko

#### Table of contents

- [Youtube video-syncer](#youtube-video-syncer)
- [Sync MPV watch-later files](#sync-mpv-watch-later-files)
- [Local podcast publisher](#local-podcast-publisher)
- [Arch Linux VM like at HOME on Mac OS](#arch-linux-vm-like-at-home-on-mac-os)
- [Arch Linux Docker Container like at HOME on Mac OS](#arch-linux-docker-container-like-at-home-on-mac-os)
- [Mini projects](#mini-projects)


## Youtube video-syncer

[video-syncer](https://github.com/diepfote/golang-tools/tree/32d62f7cad6f27d7c0503ba92907fee74f0a25b1/video-syncer)  
Syncs youtube videos between 2 computers via text files.

## Sync MPV watch-later files

[sync-mpv-watch-later-files](https://github.com/diepfote/golang-tools/tree/32d62f7cad6f27d7c0503ba92907fee74f0a25b1/sync-video-syncer-mpv-watch-later-files)  
Syncs `~/.config/mpv/watch_later` or `~/.local/state/mpv/watch_later` directories between 2 computers.
Uses functionality found in [video-syncer](#youtube-video-syncer) and [report-videos.sh](https://github.com/diepfote/scripts/blob/fc09c10453e8527e3fb53a3c379b128310c60b69/normal-privileges_systemd_scripts/report-videos.sh)

## Local podcast publisher  

[local podcast publisher](https://github.com/diepfote/local-podcast-publisher)  
Makes Podcasts available/downloadable on the local network.  
Particularly useful if no-one officially published it to a podcasting platform.

Note: it uses the following `ffprobe` and `ffmpeg` helpers:

* [ffprobe](https://github.com/search?q=repo%3Adiepfote%2Fscripts+ffprobe&type=code)
* [ffmpeg](https://github.com/search?q=repo%3Adiepfote%2Fscripts%20ffmpeg&type=code)

## Arch Linux VM like at HOME on Mac OS

Installs all packages I have on my physical Arch Linux install.  
The docker container approach is slow and some environment variables are
messed up, thus I switched to this approach.  
[full-fledged Arch Linux Lima VM config](https://github.com/diepfote/dot-files/tree/60b4c1559ae2221a076e5f9ec286f1c99f36e695/.lima/default)  
How I template the [jinja config](https://github.com/diepfote/scripts/blob/532c65847dc4e1181c1fd4da71aadbdad092b7a7/bin/darwin/limactl#L20) before starting the vm


## Arch Linux Docker Container like at HOME on Mac OS

Installs all packages I have on my physical Arch Linux install.  
[check here](./archlinux-container-like-full-arch.html)

## Vim plugins

* [Primitive yaml sort](https://github.com/diepfote/vim-primitive-yamlsort)

## Mini projects

[github gists](https://gist.github.com/search?q=user%3Adiepfote+%22mini-project%22&ref=searchresults)


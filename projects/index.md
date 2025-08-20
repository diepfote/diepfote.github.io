Projects by Florian Sorko

#### Table of contents

- [Youtube video-syncer](#youtube-video-syncer)
- [Sync MPV watch-later files](#sync-mpv-watch-later-files)
- [Local podcast publisher](#local-podcast-publisher)
- [Mini projects](#mini-projects)
- [Kubectl completion patching](#kubectl-completion-patching)
- [Execute-on-files](#execute-on-files)
- [Execute-in-repos](#execute-in-repos)

## Youtube video-syncer

[video-syncer](https://github.com/diepfote/golang-tools/tree/32d62f7cad6f27d7c0503ba92907fee74f0a25b1/video-syncer)  
Syncs youtube videos between 2 computers via text files.

## Sync MPV watch-later files

[sync-mpv-watch-later-files](https://github.com/diepfote/golang-tools/tree/7f86a2e32d83d6f09f6af758ed267eee826ddef6/sync-video-syncer-mpv-watch-later-files)  
Syncs `~/.config/mpv/watch_later` or `~/.local/state/mpv/watch_later` directories between 2 computers.
Uses functionality found in [video-syncer](#youtube-video-syncer) and [report-videos.sh](https://github.com/diepfote/scripts/blob/fc09c10453e8527e3fb53a3c379b128310c60b69/normal-privileges_systemd_scripts/report-videos.sh)

## Local podcast publisher  

[local podcast publisher](https://github.com/diepfote/local-podcast-publisher)  
Makes Podcasts available/downloadable on the local network.  
Particularly useful if no-one officially published it to a podcasting platform.

Note: it uses the following `ffprobe` and `ffmpeg` helpers:

* [ffprobe](https://github.com/search?q=repo%3Adiepfote%2Fscripts+ffprobe&type=code)
* [ffmpeg](https://github.com/search?q=repo%3Adiepfote%2Fscripts%20ffmpeg&type=code)

### Dynamic range compression

As I do not like to have my ears blown out or not be able to hear
what is being said on a video/podcast I always run dynamic range 
compression before I add them to the podcast feed.


## Vim plugins

* [Primitive yaml sort](https://github.com/diepfote/vim-primitive-yamlsort)


## Mini projects

[github gists](https://gist.github.com/search?q=user%3Adiepfote+%22mini-project%22&ref=searchresults)


## Kubectl Completion Patching

What does it do?

It allows you to add completions for custom written `kubectl`
plugins, `krew` plugins and you can even modify how things like `namespaces`
are completed.  
Lattermost I use to cache `namespaces` if the `$KUBECONFIG` is unmodified.
This way if I hit `<TAB>` after `-n` I receive suggestions without delay.

For more details [click](../terminal-config/kubectl-bash-completion-patching/index.html)

## Execute-on-files

Run arbitrary commands on files simultaneously/concurrently.

For more details [click](https://github.com/diepfote/golang-tools/tree/621f347afe3196753d8df22daa120fa024d0fdf7/execute-on-files)

## Execute-in-repos

Run arbitrary commands in git repos or plain old directories simultaneously/concurrently.

For more details [click](https://github.com/diepfote/golang-tools/tree/621f347afe3196753d8df22daa120fa024d0fdf7/execute-in-repos)


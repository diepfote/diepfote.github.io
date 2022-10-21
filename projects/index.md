## Projects by Florian Begusch

### Full archlinux on Mac OS (docker container)

Tries to resemble my personal archlinux system at home as close as possible.  
VM and container runtime set up via `limactl` -> [limactl config](https://github.com/diepfote/dot-files/blob/master/.lima/default/lima.yaml).

Commands below explicitly require these [Mac OS host mounts](https://github.com/diepfote/dot-files/blob/25f80250cfdd92b2a04c374915c9c0e5628a009f/.lima/default/lima.yaml#L34).

* build process:  
  
  ```
  build-container-image arch-all
  ```

  The command makes strong assumptions about 2 git repo
  folder locations:

  ```
  $ (cd ~/Documents/scripts/ && git remote -v)
  origin  git@github.com:florianbegusch/scripts (fetch)
  origin  git@github.com:florianbegusch/scripts (push)
  ~/
  $ (cd ~/Documents/dockerfiles/ && git remote -v)
  origin  git@github.com:florianbegusch/dockerfiles (fetch)
  origin  git@github.com:florianbegusch/dockerfiles (push)
  ```

  [command](https://github.com/diepfote/scripts/blob/master/bin/build-container-image)  
  [Dockerfile etc.](https://github.com/diepfote/dockerfiles/tree/master/arch-all)

* running the container

  ```
  run_arch-all
  ```

  Hint: see build process for required git repos

  [command](https://github.com/diepfote/scripts/blob/master/bin/run_arch-all)

### Mini projects

[github gists](https://gist.github.com/search?q=user%3Aflorianbegusch+%22mini-project%22&ref=searchresults)


### Youtube video-syncer

[video-syncer](https://github.com/diepfote/golang-tools/tree/master/video-syncer)  
Syncs youtube videos between 2 computers via text files.

### Local podcast publisher  

[local podcast publisher](https://github.com/diepfote/local-podcast-publisher)  
Makes Podcasts available/downloadable on the local network.  
Particularly useful if no-one officially published it to a podcasting platform.

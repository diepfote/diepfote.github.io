# Projects and Configs by Florian Begusch

### archlinux system on Mac OS (docker container)  
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

  [command](https://github.com/florianbegusch/scripts/blob/master/bin/build-container-image)  
  [Dockerfile etc.](https://github.com/florianbegusch/dockerfiles/tree/master/arch-all)

* running the container

  ```
  run_arch-all
  ```

  Hint: see build process for required git repos

  [command](https://github.com/florianbegusch/scripts/blob/master/bin/run_arch-all)

### Mini projects

[github gists](https://gist.github.com/search?q=user%3Aflorianbegusch+%22mini-project%22&ref=searchresults)


### Youtube video-syncer

[video-syncer](https://github.com/florianbegusch/golang-tools/tree/master/video-syncer)  
Syncs youtube videos between 2 computers via text files.

### Local podcast publisher  

[local podcast publisher](https://github.com/florianbegusch/local-podcast-publisher)  
Makes Podcasts available/downloadable on the local network.  
Particularly useful if no-one officially published it to a podcasting platform.

### Misc

* [cheatsheet collection](https://github.com/florianbegusch/cheatsheets)

## Personal terminal config

* [dot-files](https://github.com/florianbegusch/dot-files)
  * [tmux config](https://github.com/florianbegusch/dot-files/blob/master/.tmux.conf)
  * ... and anything else not in my bash script collection
* [bash script & source-me collection](https://github.com/florianbegusch/scripts)
  * [helpers in go](https://github.com/florianbegusch/golang-tools)
  * [helpers in python](https://github.com/florianbegusch/python-tools)
    * kubectl bash completion patching  
      [how to use](https://github.com/florianbegusch/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L124)  
      where to find the [patch script](https://github.com/florianbegusch/python-tools/tree/master/kubectl-client)
    * oc bash completion patching  
      [how to use](https://github.com/florianbegusch/dot-files/blob/4e18b3dce989972213431b57d096b3b6ca10d3d0/.bashrc#L137)  
      where to find the [patch script](https://github.com/florianbegusch/python-tools/tree/master/oc-client)
* git
  * [aliases](https://github.com/florianbegusch/dot-files/blob/a2e4b1cc6bfe470d1c75760cb59665fec2b5c1ca/.gitconfig#L13)
  * bash helpers
    * [general](https://github.com/florianbegusch/scripts/blob/3ac0081bbf178b4f9e630513e51c87bd8eee7527/source-me/posix-compliant-shells.sh#L589)
    * [linux only](https://github.com/florianbegusch/scripts/blob/703963f7ace80a5b61e182b09cb0884e547be436/source-me/linux/posix-compliant-shells.sh#L179)
* [vim config](https://github.com/florianbegusch/vim-config)
